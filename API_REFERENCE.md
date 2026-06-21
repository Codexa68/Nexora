# Codexa - API Reference

Complete API documentation for integrating with Codexa.

## Table of Contents

1. [OpenAI Integration](#openai-integration)
2. [File Management API](#file-management-api)
3. [Storage API](#storage-api)
4. [Editor API](#editor-api)
5. [Webhooks](#webhooks) (Enterprise)
6. [Rate Limiting](#rate-limiting)
7. [Error Handling](#error-handling)

---

## OpenAI Integration

### Configuration

```javascript
// In Codexa Settings → API Configuration
const apiKey = "sk-..."; // Your OpenAI API key
const model = "gpt-4o-mini"; // Default model
```

### Send Chat Message

```javascript
const response = await fetch('https://api.openai.com/v1/chat/completions', {
  method: 'POST',
  headers: {
    'Authorization': `Bearer ${apiKey}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    model: 'gpt-4o-mini',
    messages: [
      {
        role: 'user',
        content: 'Explain this function: ' + codeSnippet
      }
    ],
    temperature: 0.7,
    max_tokens: 1024
  })
});
```

### Available Models

| Model | Speed | Cost | Best For |
|-------|-------|------|----------|
| gpt-4o-mini | ⚡ Fast | 💰 Cheap | Most tasks |
| gpt-4-turbo | 🚀 Very Fast | 💵 Medium | Complex code |
| gpt-4 | 🐢 Slow | 💸 Expensive | Advanced analysis |

---

## File Management API

### LocalStorage Structure

Files are stored in browser localStorage under the `codexa_files` key:

```javascript
// Get all files
const files = JSON.parse(localStorage.getItem('codexa_files') || '{}');

// Structure
{
  'filename.js': {
    name: 'filename.js',
    language: 'javascript',
    content: 'console.log("hello");',
    createdAt: 1234567890,
    modifiedAt: 1234567890,
    size: 256
  }
}
```

### Create File

```javascript
const newFile = {
  name: 'script.py',
  language: 'python',
  content: '# Python code here',
  createdAt: Date.now(),
  modifiedAt: Date.now()
};

const files = JSON.parse(localStorage.getItem('codexa_files') || '{}');
files['script.py'] = newFile;
localStorage.setItem('codexa_files', JSON.stringify(files));
```

### Read File

```javascript
const files = JSON.parse(localStorage.getItem('codexa_files') || '{}');
const file = files['script.py'];
console.log(file.content);
```

### Update File

```javascript
const files = JSON.parse(localStorage.getItem('codexa_files') || '{}');
if (files['script.py']) {
  files['script.py'].content = 'new code here';
  files['script.py'].modifiedAt = Date.now();
  localStorage.setItem('codexa_files', JSON.stringify(files));
}
```

### Delete File

```javascript
const files = JSON.parse(localStorage.getItem('codexa_files') || '{}');
delete files['script.py'];
localStorage.setItem('codexa_files', JSON.stringify(files));
```

### List All Files

```javascript
const files = JSON.parse(localStorage.getItem('codexa_files') || '{}');
const fileList = Object.keys(files);
console.log(fileList); // ['file1.js', 'file2.py', ...]
```

---

## Storage API

### Get Storage Info

```javascript
const storage = {
  used: calculateStorageUsed(), // bytes
  limit: 52428800, // 50 MB for Free, 10 GB for Pro
  remaining: limit - used,
  files: Object.keys(files).length
};
```

### Calculate Storage Used

```javascript
function calculateStorageUsed() {
  const files = JSON.parse(localStorage.getItem('codexa_files') || '{}');
  let total = 0;
  
  for (let filename in files) {
    total += new Blob([files[filename].content]).size;
  }
  
  return total;
}
```

### Storage Limits by Plan

| Plan | Storage | Files |
|------|---------|-------|
| Free | 50 MB | 10 |
| Pro | 10 GB | 100 |
| Enterprise | 1 TB | Unlimited |

---

## Editor API

### Editor State

Access the current editor state:

```javascript
// Get active file
const activeFile = localStorage.getItem('codexa_active_file');

// Get editor position
const position = {
  line: 10,      // 0-indexed
  column: 5
};

// Get selected text
const selection = editor.getSelectedText(); // Pro feature
```

### Get Code Content

```javascript
function getActiveCode() {
  const activeFile = localStorage.getItem('codexa_active_file');
  const files = JSON.parse(localStorage.getItem('codexa_files') || '{}');
  return files[activeFile]?.content || '';
}
```

### Set Code Content

```javascript
function setCode(content) {
  const activeFile = localStorage.getItem('codexa_active_file');
  const files = JSON.parse(localStorage.getItem('codexa_files') || '{}');
  
  if (activeFile && files[activeFile]) {
    files[activeFile].content = content;
    files[activeFile].modifiedAt = Date.now();
    localStorage.setItem('codexa_files', JSON.stringify(files));
  }
}
```

### Detect Language

```javascript
function getLanguage(filename) {
  const ext = filename.split('.').pop();
  const languageMap = {
    'js': 'javascript',
    'ts': 'typescript',
    'py': 'python',
    'java': 'java',
    'go': 'go',
    'rs': 'rust',
    'cpp': 'cpp',
    'cs': 'csharp',
    'html': 'html',
    'css': 'css',
    'json': 'json',
    'md': 'markdown'
    // ... and 40+ more
  };
  return languageMap[ext] || 'plaintext';
}
```

---

## Webhooks (Enterprise Only)

### Configure Webhooks

In Enterprise Dashboard → Webhooks:

```json
{
  "url": "https://your-server.com/webhooks/codexa",
  "events": [
    "file.created",
    "file.updated",
    "file.deleted",
    "chat.message",
    "user.login"
  ],
  "secret": "whsec_your_secret_key"
}
```

### Webhook Events

#### file.created
```json
{
  "event": "file.created",
  "timestamp": 1234567890,
  "data": {
    "filename": "script.py",
    "language": "python",
    "size": 256
  }
}
```

#### file.updated
```json
{
  "event": "file.updated",
  "timestamp": 1234567890,
  "data": {
    "filename": "script.py",
    "changes": {
      "lines_added": 5,
      "lines_removed": 2
    }
  }
}
```

#### chat.message
```json
{
  "event": "chat.message",
  "timestamp": 1234567890,
  "data": {
    "user_id": "user_123",
    "message": "Explain this code",
    "response_tokens": 150
  }
}
```

### Verify Webhooks

Verify the signature using HMAC:

```javascript
const crypto = require('crypto');

function verifyWebhook(payload, signature, secret) {
  const hash = crypto
    .createHmac('sha256', secret)
    .update(payload)
    .digest('base64');
  
  return hash === signature;
}
```

---

## Rate Limiting

### OpenAI API Limits

| Tier | RPM | TPM |
|------|-----|-----|
| Free | 3 | 90,000 |
| Pro | 60 | 1,000,000 |
| Enterprise | Custom | Custom |

**RPM** = Requests Per Minute
**TPM** = Tokens Per Minute

### Handling Rate Limits

```javascript
async function callAI(messages) {
  try {
    return await openai.chat.completions.create({
      model: 'gpt-4o-mini',
      messages
    });
  } catch (error) {
    if (error.status === 429) {
      // Rate limited - wait and retry
      await sleep(5000);
      return callAI(messages);
    }
    throw error;
  }
}

function sleep(ms) {
  return new Promise(resolve => setTimeout(resolve, ms));
}
```

---

## Error Handling

### Common Errors

#### Invalid API Key
```
Error 401 Unauthorized
"Invalid authentication credentials"
```

**Solution**: Re-enter API key in Settings

#### Rate Limited
```
Error 429 Too Many Requests
"Rate limit exceeded"
```

**Solution**: Wait and retry, or upgrade plan

#### Storage Full
```
Error 507 Insufficient Storage
"Storage quota exceeded"
```

**Solution**: Delete files or upgrade plan

#### File Not Found
```
Error 404 Not Found
"File does not exist"
```

**Solution**: Verify file exists before accessing

### Error Response Format

```json
{
  "error": {
    "code": "INVALID_REQUEST",
    "message": "Description of the error",
    "details": {
      "field": "api_key",
      "reason": "API key is invalid or expired"
    }
  }
}
```

### Error Codes

| Code | Status | Description |
|------|--------|-------------|
| INVALID_KEY | 401 | API key is invalid or expired |
| RATE_LIMITED | 429 | Too many requests, wait before retrying |
| STORAGE_FULL | 507 | Storage quota exceeded |
| FILE_NOT_FOUND | 404 | Requested file does not exist |
| INVALID_REQUEST | 400 | Request parameters are invalid |
| INTERNAL_ERROR | 500 | Server error, retry later |

---

## Examples

### Complete Example: AI Code Review

```javascript
async function requestCodeReview(code, language) {
  const apiKey = localStorage.getItem('codexa_api_key');
  
  if (!apiKey) {
    alert('Please add your OpenAI API key in Settings');
    return;
  }
  
  const prompt = `Please review this ${language} code and suggest improvements:

\`\`\`${language}
${code}
\`\`\``;
  
  try {
    const response = await fetch('https://api.openai.com/v1/chat/completions', {
      method: 'POST',
      headers: {
        'Authorization': `Bearer ${apiKey}`,
        'Content-Type': 'application/json'
      },
      body: JSON.stringify({
        model: 'gpt-4o-mini',
        messages: [{
          role: 'user',
          content: prompt
        }],
        temperature: 0.7,
        max_tokens: 1500
      })
    });
    
    if (!response.ok) {
      throw new Error(`API Error: ${response.status}`);
    }
    
    const data = await response.json();
    return data.choices[0].message.content;
    
  } catch (error) {
    console.error('Code review failed:', error);
    return 'Error requesting code review. Check your API key.';
  }
}
```

### Complete Example: Auto-Save to GitHub

```javascript
async function saveToGitHub(filename, content, token) {
  const owner = 'your-username';
  const repo = 'your-repo';
  const branch = 'main';
  
  // Encode content to base64
  const encodedContent = btoa(content);
  
  try {
    const response = await fetch(
      `https://api.github.com/repos/${owner}/${repo}/contents/${filename}`,
      {
        method: 'PUT',
        headers: {
          'Authorization': `Bearer ${token}`,
          'Content-Type': 'application/json'
        },
        body: JSON.stringify({
          message: `Update ${filename}`,
          content: encodedContent,
          branch: branch
        })
      }
    );
    
    return response.ok;
    
  } catch (error) {
    console.error('GitHub save failed:', error);
    return false;
  }
}
```

---

## Support

- 📧 **API Support**: api-support@codexa.ai
- 📚 **Documentation**: [api.codexa.ai/docs](https://api.codexa.ai/docs)
- 🐛 **Report Issues**: [GitHub Issues](https://github.com/codexa/issues)
- 💬 **Community**: [Discord](https://discord.gg/codexa)

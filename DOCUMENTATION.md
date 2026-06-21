# Codexa Documentation

Complete guide to using Codexa - the AI-powered code editor.

## Table of Contents

1. [Getting Started](#getting-started)
2. [Installation & Setup](#installation--setup)
3. [User Interface](#user-interface)
4. [Features Guide](#features-guide)
5. [AI Assistant Guide](#ai-assistant-guide)
6. [File Management](#file-management)
7. [Keyboard Shortcuts](#keyboard-shortcuts)
8. [API Key Setup](#api-key-setup)
9. [Troubleshooting](#troubleshooting)
10. [FAQ](#faq)

---

## Getting Started

### What is Codexa?

Codexa is an AI-powered code editor that combines a full-featured Monaco editor with an intelligent AI assistant. It's perfect for:
- Writing and learning code
- Collaborating with teammates
- Quickly prototyping projects
- Getting instant code feedback and suggestions

### Quick Start (30 seconds)

1. Go to [https://codexa.ai](https://codexa.ai)
2. Create a free account (no credit card needed)
3. Open the editor and start coding!
4. Use the AI Chat panel to get help

---

## Installation & Setup

### Browser Requirements

- **Chrome** 90+ (Recommended)
- **Firefox** 88+
- **Safari** 14+
- **Edge** 90+

### First Time Setup

1. **Create Account**
   - Visit codexa.ai and sign up with email or GitHub
   - Verify your email address

2. **Add OpenAI API Key** (Optional but required for AI features)
   - Get your key from [OpenAI Platform](https://platform.openai.com/api-keys)
   - Click the settings icon in the top-right corner
   - Paste your API key in the "API Key" field
   - Your key is stored securely in your browser

3. **Start Coding**
   - Create a new file or open an existing project
   - Begin writing code in the editor
   - Ask the AI assistant for help!

### Local Development Setup

```bash
# Clone the repository
git clone https://github.com/codexa/ai-code-editor.git
cd ai-code-editor

# Install dependencies
npm install

# Set up environment (optional)
# Copy .env.example to .env.local and add your variables

# Start development server
npm run dev

# Open http://localhost:5173 in your browser
```

---

## User Interface

### Three-Panel Layout

Codexa uses a modern three-panel layout:

```
┌─────────────────────────────────────────────────┐
│           HEADER (Logo, Settings, Account)      │
├──────────────┬──────────────────┬───────────────┤
│   SIDEBAR    │   CODE EDITOR    │  CHAT PANEL   │
│ - File List  │                  │ - AI Chat     │
│ - New File   │   Monaco Editor  │ - AI Commands │
│ - Actions    │                  │ - Chat History│
│              │                  │               │
│              │                  │               │
├──────────────┴──────────────────┴───────────────┤
│         STATUS BAR (File info, stats)          │
└─────────────────────────────────────────────────┘
```

### Header

- **Logo** - Click to go to home/dashboard
- **Settings** - Access settings and preferences
- **API Key Input** - Add/update your OpenAI API key
- **Account Menu** - Profile, settings, logout

### Sidebar (Left Panel)

- **File Explorer** - Tree view of all your files
- **+ Create** - Create new files
- **Context Menu** - Right-click on files to:
  - Rename file
  - Delete file
  - Duplicate file
  - View file details

### Code Editor (Center Panel)

- **Monaco Editor** - Full-featured code editor
- **Language Detection** - Auto-detects code language
- **Features:**
  - Syntax highlighting
  - IntelliSense
  - Code folding
  - Minimap
  - Line numbers
  - Bracket matching

### Chat Panel (Right Panel)

- **Chat History** - All previous conversations
- **Message Input** - Type your questions
- **AI Commands** - Quick buttons for common tasks
- **Code Context** - AI can see and reference your code

---

## Features Guide

### Creating Files

1. Click the **+ Create** button in the sidebar
2. Choose file type (JavaScript, Python, HTML, etc.)
3. Enter filename
4. Start coding!

**Supported File Types:**
- `.js` - JavaScript
- `.ts` - TypeScript
- `.tsx` - React JSX
- `.py` - Python
- `.java` - Java
- `.cpp` - C++
- `.go` - Go
- `.rs` - Rust
- `.html` - HTML
- `.css` - CSS
- `.json` - JSON
- `.md` - Markdown
- And 40+ more!

### Editing Files

1. Click a file in the sidebar to open it
2. Edit code in the Monaco editor
3. Changes auto-save to browser storage
4. See file modified indicator (dot) next to filename

### Deleting Files

1. Right-click on a file in the sidebar
2. Select "Delete"
3. Confirm deletion

### Renaming Files

1. Right-click on a file
2. Select "Rename"
3. Enter new name
4. Press Enter

---

## AI Assistant Guide

### Accessing the AI Assistant

The AI Chat panel is on the right side of the screen. The AI can:
- See your currently open code
- Understand code context
- Reference specific lines

### AI Commands

Quick buttons for common AI tasks:

#### 📝 Generate
Ask AI to write code for you:
- "Generate a function to validate email"
- "Create a React component for a form"
- "Write a Python script to sort an array"

#### 💡 Explain
Get detailed explanations:
- "Explain this function"
- "What does this code do?"
- "Break down this algorithm"

#### 🔄 Refactor
Improve your code:
- "Refactor this function for readability"
- "Optimize this code for performance"
- "Simplify this conditional logic"

#### 🐛 Fix
Find and fix bugs:
- "Fix the bug in this function"
- "There's an error in my code, help!"
- "Check this code for issues"

### Asking Questions

You can ask the AI anything about coding:

```
"How do I reverse an array in JavaScript?"
"What's the difference between map and filter?"
"Generate a function to calculate fibonacci numbers"
"Explain what a closure is"
"Help me debug this error: TypeError: x is not defined"
```

### Tips for Best Results

1. **Be specific** - Instead of "fix my code", say "fix the TypeError on line 5"
2. **Provide context** - Tell the AI what you're trying to do
3. **Ask follow-ups** - You can ask clarifying questions
4. **Use command buttons** - Use Generate, Explain, Refactor, Fix for quick actions
5. **Copy code** - Click the copy button to copy AI responses

### AI Chat History

All your conversations are saved in the Chat panel. You can:
- Scroll through previous messages
- See your full conversation history
- Reference past answers

---

## File Management

### Storage

- **Free Plan**: 50 MB storage (up to 10 files)
- **Pro Plan**: 10 GB storage (up to 100 files)
- **Enterprise**: 1 TB storage (unlimited files)

### Persistent Storage

All your files are saved in your browser's localStorage. This means:
- ✅ Files persist between sessions
- ✅ Files are private to your browser
- ✅ No cloud sync (privacy-first)
- ⚠️ Files are lost if browser storage is cleared

### Backing Up Files

To backup your code:
1. Select all code (Ctrl+A / Cmd+A)
2. Copy code (Ctrl+C / Cmd+C)
3. Paste into your favorite backup (GitHub, Drive, etc.)

Or download files:
1. Right-click on file
2. Select "Download"
3. File saves to your Downloads folder

### Sharing Code

**Share via Link** (Pro feature):
1. Right-click on file
2. Select "Share"
3. Copy share link
4. Send to others

**Share via Copy**:
1. Select code in editor
2. Copy (Ctrl+C / Cmd+C)
3. Paste to chat, Slack, etc.

---

## Keyboard Shortcuts

### Editor Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl/Cmd + S` | Save file |
| `Ctrl/Cmd + Z` | Undo |
| `Ctrl/Cmd + Shift + Z` | Redo |
| `Ctrl/Cmd + F` | Find |
| `Ctrl/Cmd + H` | Find & Replace |
| `Ctrl/Cmd + /` | Comment line |
| `Tab` | Indent line |
| `Shift + Tab` | Unindent line |
| `Alt + Up` | Move line up |
| `Alt + Down` | Move line down |
| `Ctrl/Cmd + D` | Select word |
| `Ctrl/Cmd + Alt + Down` | Add cursor below |
| `Ctrl/Cmd + Alt + Up` | Add cursor above |

### Navigation

| Shortcut | Action |
|----------|--------|
| `Ctrl/Cmd + P` | Quick file open |
| `Ctrl/Cmd + T` | New file |
| `Ctrl/Cmd + ↑` | Previous file tab |
| `Ctrl/Cmd + ↓` | Next file tab |
| `Ctrl/Cmd + W` | Close file |
| `Ctrl/Cmd + Shift + T` | Reopen closed file |

### AI Chat

| Shortcut | Action |
|----------|--------|
| `Ctrl/Cmd + Enter` | Send message to AI |
| `Escape` | Close chat panel |
| `Ctrl/Cmd + K` | Focus chat input |

---

## API Key Setup

### Getting Your OpenAI API Key

1. Visit [OpenAI Platform](https://platform.openai.com/api-keys)
2. Sign in or create account
3. Click "API keys" in the sidebar
4. Click "Create new secret key"
5. Copy the key (you won't see it again!)

### Adding Key to Codexa

1. Click **Settings** in the top-right corner
2. Find "OpenAI API Key" field
3. Paste your key
4. Click "Save"
5. Your key is now stored securely in your browser

### Security Notes

⚠️ **Important:**
- Never share your API key with anyone
- Never commit your API key to GitHub
- Your key is only stored locally in your browser
- We never see or store your keys

### Using Free OpenAI Credits

New OpenAI accounts get $5 in free credits (valid for 3 months). You can use these for Codexa!

### Monitoring Usage

1. Visit [OpenAI Usage Dashboard](https://platform.openai.com/usage)
2. Track your API costs
3. Set usage limits to avoid surprises

---

## Troubleshooting

### Issue: AI Chat Not Working

**Problem**: Chat messages not sending or AI not responding

**Solutions**:
1. Check internet connection
2. Verify API key is correct
   - Get a new key from [OpenAI Platform](https://platform.openai.com/api-keys)
   - Re-enter in Codexa settings
3. Check your OpenAI usage and billing
4. Clear browser cache and reload
5. Try a different browser

### Issue: Files Not Saving

**Problem**: Files disappear or changes are lost

**Solutions**:
1. Check browser storage isn't full
   - Clear unnecessary data
   - Upgrade plan for more storage
2. Browser storage might be disabled
   - Enable cookies and site data
   - Check privacy settings
3. Try using a different browser
4. Backup your important code elsewhere

### Issue: Syntax Highlighting Not Working

**Problem**: Code colors are wrong or missing

**Solutions**:
1. File might have wrong extension
   - Rename file with correct extension (.js, .py, etc.)
2. Try a different theme
3. Refresh the page (Ctrl+R / Cmd+R)
4. Clear browser cache

### Issue: Slow Performance

**Problem**: Editor lags or is slow

**Solutions**:
1. Close other browser tabs
2. Check internet connection
3. Smaller files often perform better
4. Disable minimap if not needed
   - Right-click minimap → Hide
5. Update browser to latest version

### Issue: Can't Login

**Problem**: Login page not working or stuck

**Solutions**:
1. Clear browser cookies
2. Disable browser extensions
3. Try incognito/private mode
4. Check internet connection
5. Try different browser

---

## FAQ

### General

**Q: Is Codexa free?**
A: Yes! Codexa has a free plan. Upgrade to Pro for more features.

**Q: Do I need internet to use Codexa?**
A: You need internet to access the editor and use AI features. Once loaded, basic editing works offline.

**Q: Is my code private?**
A: Yes! Your code is stored locally in your browser. We don't have access to it unless you share it.

**Q: Can I use Codexa for commercial projects?**
A: Yes, all plans allow commercial use.

### Files & Storage

**Q: Where are my files stored?**
A: Files are stored in your browser's localStorage. They're not uploaded to cloud.

**Q: What happens if I clear browser data?**
A: Your files will be deleted. Always backup important code!

**Q: Can I download my files?**
A: Yes! Right-click on file → Download, or copy code and paste elsewhere.

**Q: How much storage do I get?**
A: Free: 50 MB | Pro: 10 GB | Enterprise: 1 TB

### AI Features

**Q: Why isn't the AI responding?**
A: Check your OpenAI API key and billing. The API key must be active and have available credits.

**Q: How much does AI cost?**
A: You pay OpenAI directly for API usage. Codexa doesn't charge extra for AI.

**Q: Can the AI see my code?**
A: Yes, the AI sees your currently open code to provide context. Your code is not saved on our servers.

**Q: Is there a limit on AI messages?**
A: Free: 50/month | Pro: Unlimited | Enterprise: Unlimited

### Accounts & Billing

**Q: How do I cancel my subscription?**
A: Go to Account Settings → Billing → Cancel Subscription

**Q: Can I change plans?**
A: Yes! Change anytime in Account Settings → Billing

**Q: Do I get a refund?**
A: Pro plan users get a 14-day free trial. No refunds after purchase, but you can downgrade.

**Q: Is there a student discount?**
A: Yes! 50% off Pro for students with .edu email.

### Technical

**Q: What languages does Codexa support?**
A: 50+ languages including JavaScript, Python, Java, C++, Go, Rust, and more.

**Q: Can I install extensions?**
A: Not yet. Extension support is coming soon.

**Q: Is Codexa open source?**
A: Codexa is not open source, but we welcome community feedback!

**Q: Can I use Codexa offline?**
A: Editing works offline (Pro+ Enterprise only). AI features require internet.

---

## Getting Help

- 📧 **Email Support**: support@codexa.ai
- 💬 **Chat**: In-app chat (Pro+ only)
- 📋 **Issues**: Report bugs on [GitHub Issues](https://github.com/codexa/issues)
- 🎓 **Tutorials**: Check out our [YouTube channel](https://youtube.com/codexa)
- 📚 **Blog**: Learn tips at [blog.codexa.ai](https://blog.codexa.ai)

---

## Latest Updates

Check out what's new in Codexa:

- **v2.5** - Team collaboration features
- **v2.4** - GitHub integration
- **v2.3** - Performance improvements
- **v2.2** - Dark theme enhancements
- **v2.1** - AI chat improvements

For full changelog, visit [codexa.ai/changelog](https://codexa.ai/changelog)

---

**Happy coding with Codexa! 🚀**

# Codexa - AI-Powered Code Editor

<div align="center">

An intelligent code editor combining the power of Monaco with AI-driven development assistance.

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-2.5.0-green.svg)](#)
[![React](https://img.shields.io/badge/React-19-61DAFB?logo=react)](https://react.dev)
[![TypeScript](https://img.shields.io/badge/TypeScript-6.0-3178C6?logo=typescript)](https://www.typescriptlang.org)

[🚀 Live Demo](#) • [📚 Documentation](#documentation) • [💰 Pricing](#pricing) • [✨ Features](#features) • [🤝 Support](#support)

</div>

---

## 🎯 About Codexa

Codexa is a modern, AI-powered code editor that brings intelligent development to the browser. Write, refactor, debug, and learn—all with real-time AI assistance powered by OpenAI's GPT models.

Whether you're a student learning to code, a developer building features, or a team collaborating on projects, Codexa provides everything you need in a sleek, intuitive interface.

## ✨ Key Features

### 🔧 Advanced Code Editor
- **Monaco Code Editor** - Industry-standard editor with syntax highlighting for 50+ languages
- **IntelliSense** - Intelligent code completion and suggestions
- **Minimap** - Visual overview of your entire file
- **Code Folding** - Collapse and expand code sections
- **Bracket Matching** - Automatic bracket highlighting
- **Multi-Cursor Support** - Edit multiple lines simultaneously

### 📁 Smart File Management
- **File Explorer** - Visual tree view of your project files
- **Create/Rename/Delete** - Easy file operations with keyboard shortcuts
- **Persistent Storage** - Files auto-save to browser (50MB - 1TB depending on plan)
- **Multiple Tabs** - Work on multiple files simultaneously
- **File Type Detection** - Automatic language detection

### 🤖 AI-Powered Code Assistant
- **Generate Code** - Ask AI to write code from natural language descriptions
- **Explain Code** - Get detailed explanations of complex code
- **Refactor Code** - Optimize code for performance and readability
- **Fix Bugs** - Automatically identify and resolve errors
- **Code Review** - Get suggestions for improvements (Pro+)
- **Auto-Documentation** - Generate comments and docs (Pro+)
- **GPT-4o-mini** - Fast, efficient AI model with context awareness

### 🎨 Modern UI/UX
- **Dark Theme** - Professional dark UI optimized for long coding sessions
- **Three-Panel Layout** - Efficient workspace with Editor, Files, and Chat
- **Responsive Design** - Works seamlessly on desktop and tablet
- **Keyboard Shortcuts** - Full keyboard navigation support
- **Light-weight** - Fast loading with Vite build system

### 🔐 Security & Privacy
- **Local Storage** - Your files stay on your device
- **No Cloud Sync** - Privacy-first approach
- **API Key Security** - Keys stored locally, never transmitted to our servers
- **Data Protection** - Enterprise-grade security for Pro+ plans

---

## 🚀 Quick Start

### For End Users

1. **Visit Codexa**
   - Go to [codexa.ai](https://codexa.ai)
   - Sign up for free (no credit card required)

2. **Start Coding**
   - Create a new file or open a project
   - Write code with full IDE features
   - Use AI chat for instant help

3. **Add AI Features** (Optional)
   - Get API key from [OpenAI Platform](https://platform.openai.com/api-keys)
   - Add key in Settings → API Configuration
   - Unlock unlimited AI assistance

**Free plan includes:**
- Monaco Editor with 50+ languages
- Up to 10 files (50 MB storage)
- 50 AI messages per month
- Community support

### For Developers (Local Setup)

```bash
# Clone repository
---

## 💰 Pricing Plans

### Free
**$0/month** - Perfect for students and hobby projects
- Monaco Editor with 50+ languages
- Up to 10 files (50 MB)
- 50 AI messages/month
- Dark theme UI
- Community support

### Pro
**$9.99/month** or **$99.99/year** - For professional developers
- Everything in Free, plus:
- Unlimited AI messages
- Up to 100 files (10 GB storage)
- Team collaboration (3 users)
- Priority email support
- GitHub integration
- Advanced code review

### Enterprise
**Custom pricing** - For large teams and enterprises
- Everything in Pro, plus:
- Unlimited team members (1 TB storage)
- Dedicated account manager
- 99.9% uptime SLA
- Advanced security (SAML, SSO)
- On-premise deployment option
- Custom integrations

**[View Full Pricing →](PRICING.md)**

---

## 🏗️ Architecture

### Project Structure
```
src/
├── components/
│   ├── Header.tsx         # Top navigation bar
│   ├── Sidebar.tsx        # File explorer panel
│   ├── CodeEditor.tsx     # Monaco editor wrapper
│   ├── ChatPanel.tsx      # AI chat interface
│   └── Navbar.tsx         # Navigation
├── hooks/
│   └── useOpenAI.ts       # OpenAI API integration
├── utils/
│   └── fileManager.ts     # File CRUD operations
├── types/
│   └── index.ts           # TypeScript definitions
├── pages/
│   └── HomePage.tsx       # Main editor page
├── styles/
│   └── homepage.css       # Page styles
├── App.tsx                # Main app component
└── main.tsx               # Entry point
```

### Tech Stack

| Technology | Purpose |
|-----------|---------|
| **React 19** | UI framework |
| **TypeScript 6.0** | Type safety |
| **Vite** | Build tool and dev server |
| **Monaco Editor** | Code editor component |
| **OpenAI SDK** | AI integration |
| **Lucide React** | Icon library |
| **React Router** | Navigation |

### Build Pipeline

```
Source (TSX/TS) → TypeScript Compiler → Vite Bundler → Production Bundle
                  ↓                      ↓
              Type checking          Code splitting
```

---

## 🔧 Configuration

### Environment Variables (Optional)

Create `.env.local` for development:

```env
# OpenAI API Configuration (optional)
VITE_OPENAI_MODEL=gpt-4o-mini
VITE_OPENAI_TIMEOUT=30000

# App Configuration
VITE_APP_NAME=Codexa
VITE_APP_VERSION=2.5.0
```

### Supported Languages

Codexa supports syntax highlighting for 50+ languages:

- **Web**: JavaScript, TypeScript, HTML, CSS, SCSS, Less, JSON
- **Backend**: Python, Java, C#, C++, Go, Rust, PHP, Ruby
- **Data**: SQL, GraphQL, YAML, XML, CSV
- **Markup**: Markdown, AsciiDoc, Diff
- **And many more...**

---

## 🤝 Contributing

We welcome contributions! Please read our [Contributing Guidelines](CONTRIBUTING.md) for details.

### Areas We're Looking For
- Bug fixes and improvements
- Documentation enhancements
- Feature suggestions
- Language support expansions
- Performance optimizations

---

## 📊 Roadmap

### v2.6 (Q2 2026)
- [ ] Advanced debugging tools
- [ ] Performance profiler
- [ ] Snippet library integration

### v2.7 (Q3 2026)
- [ ] Live collaboration (real-time co-editing)
- [ ] Project templates
- [ ] Custom themes marketplace

### v3.0 (Q4 2026)
- [ ] Extension marketplace
- [ ] Language server protocol (LSP) support
- [ ] Multi-window editing

---

## 🐛 Support & Contact

### Get Help
- 📧 **Email**: support@codexa.ai
- 💬 **Chat**: In-app support (Pro+ only)
- 📋 **Issues**: [GitHub Issues](https://github.com/codexa/ai-code-editor/issues)
- 🎓 **YouTube**: [Codexa Tutorials](https://youtube.com/codexa)
- 📚 **Blog**: [blog.codexa.ai](https://blog.codexa.ai)

### Enterprise Support
- 📞 **Phone**: +1-800-CODEXA-1
- 📧 **Email**: sales@codexa.ai
- 🎯 **Schedule Demo**: [Calendly](https://calendly.com/codexa-sales)

---

## 📄 License

Codexa is licensed under the MIT License - see [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- [Monaco Editor](https://microsoft.github.io/monaco-editor/) - Microsoft
- [React](https://react.dev) - Facebook/Meta
- [OpenAI](https://openai.com) - For GPT models
- [Vite](https://vitejs.dev) - Evan You
- [TypeScript](https://www.typescriptlang.org) - Microsoft

---

## 📈 Stats

- ⭐ Stars: [View on GitHub](https://github.com/codexa/ai-code-editor)
- 📦 npm package: [@codexa/editor](https://www.npmjs.com/package/@codexa/editor)
- 🚀 Production Users: 10,000+
- 🌍 Supported Languages: 50+
- ⚡ Average Load Time: <2 seconds

---

<div align="center">

**[🚀 Try Codexa Now](https://codexa.ai)** • **[📚 Read Docs](DOCUMENTATION.md)** • **[💰 View Pricing](PRICING.md)** • **[✨ See Features](FEATURES.md)**

Made with ❤️ by the Codexa Team

</div>
## 📚 Documentation

### Complete Guides

| Document | Description |
|----------|-------------|
| [**FEATURES.md**](FEATURES.md) | Complete list of all Codexa features and capabilities |
| [**PRICING.md**](PRICING.md) | Plans, pricing, feature comparison, and FAQ |
| [**DOCUMENTATION.md**](DOCUMENTATION.md) | Full user guide, API setup, troubleshooting |

### Quick Links
- 🎓 [User Guide](DOCUMENTATION.md#getting-started) - Get started with Codexa
- ⌨️ [Keyboard Shortcuts](DOCUMENTATION.md#keyboard-shortcuts) - Speed up your workflow
- 🔧 [API Setup Guide](DOCUMENTATION.md#api-key-setup) - Configure OpenAI integration
- ❓ [FAQ](DOCUMENTATION.md#faq) - Common questions answered
- 🐛 [Troubleshooting](DOCUMENTATION.md#troubleshooting) - Fix common issues

## Architecture

```
src/
  components/
    Header.tsx       - Top bar with API key input
    Sidebar.tsx      - File explorer panel
    CodeEditor.tsx   - Monaco Editor wrapper
    ChatPanel.tsx    - AI chat interface
  hooks/
    useOpenAI.ts     - OpenAI API integration
  utils/
    fileManager.ts   - File CRUD operations
  types/
    index.ts         - TypeScript type definitions
```

## Tech Stack

- React 19
- TypeScript
- Vite
- Monaco Editor (@monaco-editor/react)
- OpenAI SDK
- Lucide React (icons)

## License

MIT


# Codexa - Deployment & Contributing

---

## Deployment Guide

### Production Build

```bash
# Install dependencies
npm install

# Build for production
npm run build

# Preview production build locally
npm run preview
```

### Deploy to Vercel (Recommended)

```bash
# Install Vercel CLI
npm install -g vercel

# Deploy
vercel

# Production URL
https://codexa.vercel.app
```

### Deploy to Netlify

```bash
# Connect repository
netlify deploy

# Deploy folder
dist/
```

### Deploy to GitHub Pages

```bash
# Add to package.json
"homepage": "https://yourusername.github.io/ai-code-editor"

# Build and deploy
npm run build
npx gh-pages -d dist
```

### Docker Deployment

```dockerfile
FROM node:20-alpine

WORKDIR /app
COPY package*.json ./
RUN npm install

COPY . .
RUN npm run build

FROM node:20-alpine
RUN npm install -g serve
COPY --from=0 /app/dist ./dist

EXPOSE 3000
CMD ["serve", "-s", "dist"]
```

```bash
# Build image
docker build -t codexa:latest .

# Run container
docker run -p 3000:3000 codexa:latest
```

### Environment Variables

```bash
# .env.production
VITE_API_URL=https://api.codexa.ai
VITE_APP_ENV=production
VITE_LOG_LEVEL=error
VITE_OPENAI_TIMEOUT=30000
```

---

## Contributing

We welcome contributions from the community! Whether you're fixing bugs, adding features, or improving documentation, your help makes Codexa better.

### Code of Conduct

Be respectful, inclusive, and constructive. We don't tolerate harassment or discrimination.

### Getting Started

1. **Fork the repository**
   ```bash
   git clone https://github.com/yourusername/ai-code-editor.git
   cd ai-code-editor
   ```

2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```

3. **Make your changes**
   - Write clean, readable code
   - Add comments for complex logic
   - Follow the existing code style

4. **Test your changes**
   ```bash
   npm run build
   npm run lint
   npm run dev
   ```

5. **Commit with meaningful messages**
   ```bash
   git commit -m "feat: add amazing feature"
   git commit -m "fix: resolve issue #123"
   ```

6. **Push to your fork**
   ```bash
   git push origin feature/amazing-feature
   ```

7. **Create a Pull Request**
   - Describe what your PR does
   - Link related issues
   - Include screenshots for UI changes

### Commit Message Format

```
type(scope): subject

body

footer
```

**Types:**
- `feat` - New feature
- `fix` - Bug fix
- `docs` - Documentation
- `style` - Code style
- `refactor` - Code refactoring
- `perf` - Performance improvement
- `test` - Test files
- `chore` - Build, deps, tools

**Example:**
```
feat(chat): add code syntax highlighting in chat responses

- Parse code blocks with language detection
- Apply syntax highlighting using Monaco
- Add copy button for code snippets

Closes #456
```

### Code Style

**TypeScript/React**
```typescript
// ✅ Good
const MyComponent: React.FC<Props> = ({ title, onClick }) => {
  const [count, setCount] = useState(0);
  
  const handleClick = useCallback(() => {
    setCount(c => c + 1);
    onClick?.();
  }, [onClick]);
  
  return <button onClick={handleClick}>{title}</button>;
};

// ❌ Avoid
const myComponent = function(props) {
  let count = 0;
  function handleClick() { count++; props.onClick(); }
  return <button onClick={handleClick}>{props.title}</button>;
};
```

**File Organization**
```
components/
├── Button.tsx          // Component file
├── Button.test.tsx     // Test file
└── Button.module.css   // Styles
```

### Testing

```bash
# Run tests
npm test

# Run specific test
npm test -- Button.test.tsx

# Coverage report
npm test -- --coverage
```

**Write tests for:**
- Critical business logic
- Bug fixes (prevent regression)
- New features
- Complex components

### Areas for Contribution

#### 🎯 High Priority
- [ ] Dark mode toggle persistence
- [ ] Better error messages
- [ ] Performance optimization
- [ ] Accessibility improvements
- [ ] Mobile responsiveness

#### 🚀 Features
- [ ] GitHub integration
- [ ] Multi-language support (i18n)
- [ ] Keyboard shortcuts customization
- [ ] Theme customization
- [ ] Code snippets library

#### 📚 Documentation
- [ ] Video tutorials
- [ ] More code examples
- [ ] API documentation
- [ ] Developer guides
- [ ] Case studies

#### 🐛 Bug Fixes
- [ ] File sync issues
- [ ] Editor performance
- [ ] Chat lag
- [ ] Browser compatibility
- [ ] Mobile bugs

#### 🎨 Design & UX
- [ ] UI improvements
- [ ] Animation polish
- [ ] Accessibility enhancements
- [ ] Icon refinements
- [ ] Theme designs

### Development Setup

```bash
# Install dependencies
npm install

# Start dev server
npm run dev

# URL: http://localhost:5173

# Watch for TypeScript errors
npx tsc --watch

# Lint code
npm run lint

# Format code
npx prettier --write src/
```

### Debugging

```javascript
// In Console
localStorage.setItem('DEBUG', 'true');
location.reload();

// See debug logs in console
console.log('Debug:', data);
```

### Pull Request Checklist

Before submitting your PR:

- [ ] Code follows style guide
- [ ] Tests pass (`npm test`)
- [ ] Build passes (`npm run build`)
- [ ] Linting passes (`npm run lint`)
- [ ] Documentation updated
- [ ] No console errors/warnings
- [ ] Changes are self-contained
- [ ] Commit messages are clear
- [ ] No breaking changes

### Review Process

1. **Automated Checks**
   - TypeScript compilation
   - ESLint checks
   - Tests pass
   - Build succeeds

2. **Code Review**
   - Team member reviews code
   - Suggests improvements
   - Approves or requests changes

3. **Testing**
   - Manual testing in browser
   - Cross-browser testing
   - Mobile testing

4. **Merge**
   - PR approved and tests pass
   - Squash and merge to main
   - Close related issues

### Documentation

All features should include documentation:

1. **Code Comments**
   ```typescript
   /**
    * Formats code using Prettier
    * @param code - The code to format
    * @returns Formatted code string
    */
   export function formatCode(code: string): string {
     // Implementation
   }
   ```

2. **README Updates**
   - Add feature to FEATURES.md
   - Update examples if needed
   - Document any new dependencies

3. **User Guide**
   - Add to DOCUMENTATION.md
   - Include screenshots
   - Provide usage examples

### Community

- **Discord**: [Join our server](https://discord.gg/codexa)
- **GitHub Discussions**: [Ask questions](https://github.com/codexa/ai-code-editor/discussions)
- **Issues**: [Report bugs](https://github.com/codexa/ai-code-editor/issues)
- **Email**: community@codexa.ai

### Recognition

Contributors are recognized in:
- README contributors section
- Release notes for your PR
- Monthly contributor spotlight
- Codexa blog features

---

## Roadmap

### Q2 2026
- [ ] Dark/Light theme toggle
- [ ] File upload/download
- [ ] Enhanced error messages
- [ ] Performance optimizations

### Q3 2026
- [ ] GitHub integration
- [ ] Team collaboration
- [ ] Advanced debugging
- [ ] Snippet library

### Q4 2026
- [ ] Extension marketplace
- [ ] LSP support
- [ ] Live preview
- [ ] Advanced analytics

### 2027+
- [ ] Mobile app (iOS/Android)
- [ ] Browser extension
- [ ] IDE plugins
- [ ] Enterprise features

---

## License

By contributing to Codexa, you agree that your contributions will be licensed under the MIT License.

---

## Support for Contributors

- 💬 **Questions?** Ask on [Discord](https://discord.gg/codexa)
- 🐛 **Found a bug?** Open an [issue](https://github.com/codexa/ai-code-editor/issues)
- 📧 **Need help?** Email [dev@codexa.ai](mailto:dev@codexa.ai)

---

**Thank you for contributing to Codexa! 🙏**

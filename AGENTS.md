# AGENTS.md

This file contains guidelines and commands for agentic coding agents working in this repository.

## Project Overview

This is a simple HTML/CSS/JavaScript game repository containing three browser-based games:
- **2048** (game1.html) - Classic sliding tile puzzle game
- **Forest Hunting** (game2.html) - Shooting game with forest theme  
- **AR Whack-a-Mole** (game3.html) - Hand-tracking version using MediaPipe

The project uses vanilla HTML, CSS, and JavaScript with no build tools or frameworks.

## Build/Test Commands

Since this is a static HTML project with no build system:

### Running Games
```bash
# Open any game in browser (replace with specific game file)
start game1.html
# or
open game1.html
# or simply double-click the HTML file
```

### Validation
```bash
# No automated tests - manual testing required
# Test each game by opening in browser and verifying functionality
```

### Linting (if available)
```bash
# No formal linting configured
# Use browser developer tools for JavaScript debugging
# Validate HTML with online validators if needed
```

## Code Style Guidelines

### HTML Structure
- Use semantic HTML5 elements (`header`, `main`, `section`, etc.)
- Include proper DOCTYPE and meta tags
- Use `lang="zh-TW"` or `lang="zh-HK"` for Chinese content
- Structure: `<!DOCTYPE html> <html> <head> <body>`

### CSS Conventions
- Use internal `<style>` tags in HTML files (no external CSS)
- Mobile-first responsive design with `@media` queries
- CSS custom properties for colors when appropriate
- Grid and Flexbox for layouts
- Smooth transitions and animations (0.15s - 0.3s)

### JavaScript Standards
- Use modern ES6+ syntax (arrow functions, const/let, template literals)
- Event delegation for dynamic elements
- `DOMContentLoaded` event listener for initialization
- Modular functions with clear single responsibilities
- Proper error handling with try-catch when needed
- LocalStorage for game state persistence

### Naming Conventions
- **Files**: kebab-case (game1.html, game2.html)
- **CSS Classes**: kebab-case (.game-container, .score-display)
- **JavaScript Variables**: camelCase (gameState, bestScore)
- **Functions**: camelCase with descriptive verbs (initGame, updateScore)
- **Constants**: UPPER_SNAKE_CASE (GRID_SIZE, CELL_COUNT)

### File Organization
- Single HTML file per game (self-contained)
- CSS in `<style>` tag in `<head>`
- JavaScript in `<script>` tag at end of `<body>`
- Comments in Chinese for user-facing text, English for code comments

### Game Development Patterns
- State management with global variables
- Render loop pattern for animations
- Event-driven architecture (keyboard, touch, click)
- Responsive design for mobile and desktop
- Accessibility considerations (ARIA labels, keyboard navigation)

### Error Handling
- Graceful degradation for older browsers
- User-friendly error messages in Chinese
- Console logging for debugging (remove in production)
- Fallback functionality for unsupported features

### Performance Guidelines
- Optimize images and assets
- Use CSS transforms instead of JavaScript animations when possible
- Debounce rapid events (keyboard input, touch events)
- Lazy load external resources (CDN scripts)

### Security Considerations
- No eval() or dangerous dynamic code execution
- Sanitize user input if handling forms
- Use HTTPS CDN links for external resources
- No sensitive data in client-side code

### Localization
- Primary language: Traditional Chinese (zh-TW)
- UI text in Chinese characters
- Code comments in English
- Cultural considerations in game design

## Testing Guidelines

### Manual Testing Checklist
- [ ] Game loads without errors
- [ ] All controls work (keyboard, mouse, touch)
- [ ] Responsive design on mobile devices
- [ ] Game state saves/loads correctly
- [ ] No console errors or warnings
- [ ] Cross-browser compatibility (Chrome, Firefox, Safari)

### Browser Testing
- Test on latest Chrome, Firefox, Safari
- Test on mobile browsers (iOS Safari, Chrome Mobile)
- Test with different screen sizes
- Test touch gestures on mobile devices

## Git Guidelines

### Commit Messages
- Use Chinese for commit messages (matching existing commits)
- Format: `type: description` (e.g., `feat: 新增遊戲功能`)
- Types: `feat`, `fix`, `style`, `refactor`, `docs`, `test`

### Branch Strategy
- Main branch for stable releases
- Feature branches for new games or major changes
- No complex branching needed for simple HTML games

## External Dependencies

### CDN Libraries
- MediaPipe Hands (game3.html only)
- Use HTTPS CDN links only
- Include version numbers for stability

### Browser Compatibility
- Target modern browsers (ES6+ support)
- Graceful fallbacks for older browsers
- No polyfills needed for current feature set
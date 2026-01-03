# Contributing to Puzzle Game

Thank you for your interest in contributing! This document will guide you through the contribution process.

## Code of Conduct

We are committed to providing a welcoming and inspiring community for all. Please read and adhere to our principles:

- Be respectful and inclusive
- Welcome diverse perspectives and backgrounds
- Focus on constructive feedback
- Help create a positive environment

## Getting Started

### Prerequisites

- Basic knowledge of HTML, CSS, JavaScript
- Git and GitHub account
- A text editor or IDE
- A modern web browser for testing

### Setup for Development

1. **Fork the repository**
   ```bash
   Click "Fork" on GitHub
   ```

2. **Clone your fork**
   ```bash
   git clone https://github.com/YOUR-USERNAME/puzzle-game.git
   cd puzzle-game
   ```

3. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

4. **Open `index.html` in your browser** and test as you make changes

## Types of Contributions

### 🐛 Bug Fixes

Found a bug? We appreciate bug fixes!

**Steps:**
1. Create an issue describing the bug (if one doesn't exist)
2. Create a branch: `git checkout -b fix/bug-description`
3. Fix the bug in the code
4. Test thoroughly in multiple browsers
5. Submit a pull request with a clear description

**Example:**
```javascript
// Before: Button click handler doesn't clear error highlighting
.btn--secondary:hover {
    background: var(--color-gray-200);
}

// After: Clear error states on new game
changeDifficulty(difficulty) {
    document.querySelectorAll('.sudoku-cell').forEach(cell => {
        cell.classList.remove('error');
    });
    // ... rest of code
}
```

### ✨ New Features

Have a great idea? Submit a feature request or implement it!

**Process:**
1. Check [GitHub Issues](../../issues) - don't duplicate requests
2. Open a Discussion if unsure about the feature
3. Create a branch: `git checkout -b feature/feature-name`
4. Implement the feature
5. Add comments explaining complex logic
6. Test thoroughly
7. Submit pull request with clear description

**Popular Feature Ideas:**
- Dark mode theme
- Additional puzzle types (Jigsaw, Killer Sudoku)
- Sound effects
- Undo/replay functionality
- More seed puzzles

### 📚 Documentation

Help improve docs and guides!

**What to document:**
- Code comments for complex algorithms
- Puzzle generation process
- Game logic and validation
- Setup instructions
- API references

**How to contribute:**
1. Create a branch: `git checkout -b docs/improvement`
2. Add or improve documentation
3. Submit pull request

### 🎨 Design & UX

Help make the game look better!

**Areas:**
- Visual improvements
- Responsive design enhancements
- Accessibility improvements
- Better user feedback

### 🔍 Testing

Test across platforms and report issues!

**Test Coverage:**
- Different browsers (Chrome, Firefox, Safari, Edge)
- Different devices (Desktop, Tablet, Mobile)
- Different screen sizes (small phone to 4K monitor)
- Keyboard-only navigation
- Touch interactions on mobile

## Coding Standards

### JavaScript

```javascript
// Use descriptive variable names
const currentDifficulty = 'medium';  // Good
const cd = 'medium';                 // Avoid

// Use const by default, let when needed, avoid var
const fixedValue = 100;
let changingValue = 0;

// Use arrow functions for callbacks
cells.forEach(cell => {
    cell.addEventListener('click', () => handleClick(cell));
});

// Add comments for complex logic
// Backtracking algorithm to solve sudoku
solvePuzzleCompletely(grid) {
    for (let row = 0; row < 9; row++) {
        for (let col = 0; col < 9; col++) {
            if (grid[row][col] === 0) {
                for (let num = 1; num <= 9; num++) {
                    if (this.isValidPlacement(grid, row, col, num)) {
                        grid[row][col] = num;
                        if (this.solvePuzzleCompletely(grid)) return grid;
                        grid[row][col] = 0;
                    }
                }
                return false;
            }
        }
    }
    return true;
}
```

### CSS

```css
/* Use CSS variables for colors and spacing */
:root {
    --color-primary: rgba(33, 128, 141, 1);
    --space-16: 16px;
}

/* Keep class names descriptive */
.sudoku-cell {           /* Good - specific element */
.btn--primary {          /* Good - BEM notation */
.active {                /* Avoid - too generic */

/* Comment complex selectors */
/* Thick borders for 3x3 sudoku boxes */
.sudoku-cell:nth-child(3n) {
    border-right: 2px solid var(--color-text);
}
```

### HTML

```html
<!-- Use semantic HTML elements -->
<button class="btn btn--primary" id="solveBtn">Solve</button>
<div class="status-message" id="statusMessage"></div>

<!-- Add data attributes for logic -->
<button class="btn" data-difficulty="easy">Easy</button>
<input class="sudoku-cell" data-row="0" data-col="0">

<!-- Include comments for sections -->
<!-- Action buttons for game controls -->
<div class="action-buttons">
    ...
</div>
```

## Testing Your Changes

### Before Submitting

1. **Test in multiple browsers**
   ```
   Chrome, Firefox, Safari, Edge
   Mobile Safari (iPhone), Chrome Mobile (Android)
   ```

2. **Test different screen sizes**
   ```
   Mobile: 320px - 480px
   Tablet: 768px - 1024px
   Desktop: 1200px - 2560px
   ```

3. **Test functionality**
   - All difficulty levels work
   - Puzzles generate correctly
   - Validation works properly
   - Timer functions correctly
   - Stats save and display
   - Export feature works

4. **Test keyboard navigation**
   - Arrow keys move between cells
   - Backspace/Delete clear cells
   - Tab focuses on buttons
   - Enter activates buttons

5. **Test on real devices**
   - iPhone (Safari)
   - Android phone (Chrome)
   - Tablet
   - Desktop

## Submitting Changes

### Before You Submit

1. **Verify your code**
   ```bash
   # Check for syntax errors
   # Open in browser and test thoroughly
   # Test on multiple devices if possible
   ```

2. **Make clean commits**
   ```bash
   git add index.html
   git commit -m "Fix: Clear error highlighting on new game"
   ```

3. **Update your branch**
   ```bash
   git fetch upstream
   git rebase upstream/main
   git push origin feature/your-feature
   ```

### Opening a Pull Request

1. **Go to GitHub** and click "New Pull Request"

2. **Fill out the PR template**
   ```markdown
   ## Description
   Brief description of changes

   ## Type of Change
   - [ ] Bug fix
   - [ ] New feature
   - [ ] Documentation update

   ## Changes Made
   - Changed X to do Y
   - Added Z functionality

   ## Testing Done
   - Tested on Chrome/Firefox/Safari
   - Tested on mobile
   - Tested keyboard navigation

   ## Screenshots (if applicable)
   [Add before/after screenshots]

   ## Checklist
   - [ ] Code follows style guidelines
   - [ ] Self-review completed
   - [ ] Comments added for complex logic
   - [ ] Tested in multiple browsers
   - [ ] Tested on mobile
   ```

3. **Wait for review**
   - Maintainers will review your code
   - Respond to feedback professionally
   - Make requested changes in follow-up commits

## Pull Request Reviews

### What We Look For

✅ **Code Quality**
- Follows coding standards
- No unnecessary complexity
- Clear variable names
- Comments for complex logic

✅ **Functionality**
- Works as intended
- Doesn't break existing features
- Handles edge cases
- Good error handling

✅ **Testing**
- Tested in multiple browsers
- Works on mobile
- Works on desktop
- Keyboard navigation works

✅ **Documentation**
- Code is well commented
- PR description is clear
- Related issues are referenced

### Responding to Feedback

- Be professional and respectful
- Don't take feedback personally
- Ask for clarification if needed
- Make requested changes promptly
- Thank reviewers for their time

## Release Process

Maintainers will handle versioning and releases.

**Version Format:** `MAJOR.MINOR.PATCH` (e.g., 1.2.3)

- **MAJOR:** Breaking changes
- **MINOR:** New features
- **PATCH:** Bug fixes

## Questions?

- Open a [Discussion](../../discussions)
- Comment on relevant [Issue](../../issues)
- Check existing documentation

## Recognition

Contributors will be added to:
- [CONTRIBUTORS.md](CONTRIBUTORS.md)
- GitHub contributor graph
- Release notes (for significant contributions)

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

## Resources

- **GitHub Guides:** [How to Contribute to Open Source](https://opensource.guide/how-to-contribute/)
- **Git Basics:** [Pro Git Book](https://git-scm.com/book/en/v2)
- **JavaScript Best Practices:** [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

---

Thank you for contributing to Puzzle Game! Your effort makes this project better for everyone. 🎉

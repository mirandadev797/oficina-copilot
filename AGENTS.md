---
name: Bingo Mixer Agent Lab
description: A GitHub Copilot Agent Lab project for building a social bingo game with design-first and multi-agent workflows
---

# 🎮 Bingo Mixer: Agent Development Guide

**Bingo Mixer** is an interactive social bingo game where players find people matching questions and get 5 in a row! This repo serves as a **GitHub Copilot Agent Lab** for teaching design-first development, context engineering, and multi-agent workflows.

## ✅ Development Checklist

Before starting tasks, ensure this is complete:
- [ ] Dependencies installed: `npm install`
- [ ] Lint passing: `npm run lint`
- [ ] Tests passing: `npm test`
- [ ] Build succeeding: `npm run build`
- [ ] Dev server running: `npm run dev` (on http://localhost:5173/)

## 🏗️ Project Structure

```
src/
├── components/          # React components (BingoBoard, GameScreen, StartScreen, etc.)
├── data/               # Game data (questions.ts - 24 icebreaker prompts)
├── hooks/              # Custom React hooks (useBingoGame - main game logic)
├── utils/              # Core game logic (bingoLogic.ts - board generation, bingo detection)
├── types/              # TypeScript interfaces
└── test/               # Test setup (Jest DOM matchers)

.github/
├── agents/             # Specialized agent workflows (quiz-master, tdd, ui-review, etc.)
├── instructions/       # Context-specific skills (frontend-design, tailwind-4)
├── prompts/            # Prompt templates (setup, cloud-explore)
└── workflows/          # GitHub Actions CI/CD

workshop/               # 5-part learning lab (EN, PT-BR, ES)
```

## 🎯 Key Architecture

### Game Logic (`src/utils/bingoLogic.ts`)
- **generateBoard()** - Shuffles 24 questions + free space into 5×5 grid
- **toggleSquare()** - Marks/unmarks individual squares
- **checkBingo()** - Detects 5-in-a-row patterns (horizontal, vertical, diagonal)
- **getWinningSquareIds()** - Returns IDs of squares forming the win pattern

### State Management (`src/hooks/useBingoGame.ts`)
- Manages gameState: `'start'` → `'playing'` → `'bingo'`
- Handles board generation, square toggles, and reset logic

### UI Components
- **StartScreen** - Game entry with theming
- **GameScreen** - Main 5×5 grid with confetti on bingo
- **BingoBoard** - Grid renderer
- **BingoSquare** - Individual clickable squares
- **BingoModal** - Victory celebration display

## 🛠️ Tech Stack

| Layer | Technology | Notes |
|-------|-----------|-------|
| **Framework** | React 19 + TypeScript | Modern with strict typing |
| **Build** | Vite 8 | Lightning-fast dev server |
| **Styling** | Tailwind CSS v4 | CSS-first with `@theme` directive |
| **Testing** | Vitest + React Testing Library | Fast unit tests with DOM matchers |
| **Linting** | ESLint + TypeScript ESLint | Enforces consistency |
| **Deployment** | GitHub Pages (GitHub Actions) | Auto-deploys on push to `main` |

## 🤖 Built-in Agent Workflows

These specialized agents are ready to use:

### `quiz-master`
Creates thematic icebreaker bingo questions. Invoke with a theme description.
- Balances difficulty (easy/medium/bold)
- Ensures variety (personal, work, fun, action-based)
- See [Quiz Master Part 03](workshop/03-quiz-master.md)

### `tdd` (TDD Supervisor)
Orchestrates Test-Driven Development cycle:
1. `tdd-red` - Writes failing tests
2. `tdd-green` - Implements minimal passing code
3. `tdd-refactor` - Cleans up implementation
- See [Multi-Agent Part 04](workshop/04-multi-agent.md)

### `ui-review`
Provides design and UX feedback on the current game UI.

### `pixel-jam`
Creates stylized, visually distinctive interfaces (theme variations).

## 📋 Commands & Tasks

```bash
# Development
npm run dev           # Start Vite dev server (localhost:5173)
npm run build         # Build for production

# Code Quality
npm run lint          # Run ESLint on src/ (with --fix for auto-fix)
npm test              # Run Vitest (unit tests)

# Integration
npm run build && npm test  # Full validation before commit
```

## 🎨 Frontend Design Conventions

See [frontend-design.instructions.md](.github/instructions/frontend-design.instructions.md) for detailed guidelines:
- **Typography:** Use distinctive fonts (avoid Inter, Roboto, Arial)
- **Color & Theme:** Commit to cohesive aesthetics with CSS variables
- **Motion:** High-impact animations at page load, CSS-only when possible
- **Backgrounds:** Layer gradients and patterns for depth
- **Avoid:** Generic "AI slop" (purple gradients, clichéd layouts)

## 🎨 Tailwind CSS v4 Notes

See [tailwind-4.instructions.md](.github/instructions/tailwind-4.instructions.md):
- Use `@theme` directive in CSS (no `tailwind.config.js`)
- Define custom tokens: `--color-brand`, `--font-display`, etc.
- Native opacity: `bg-black/50`, `text-brand/75`
- Automatic content detection

## 📚 Documentation

- **[Lab Guide](workshop/GUIDE.md)** - Quick reference
- **[README](README.md)** (multilingual: [PT-BR](README.pt_BR.md), [ES](README.es.md))
- **[Part 01: Setup & Context Engineering](workshop/01-setup.md)** - Initial configuration
- **[Part 02: Design-First Frontend](workshop/02-design.md)** - Theme redesign with planning
- **[Part 03: Custom Quiz Master](workshop/03-quiz-master.md)** - Question curation agent
- **[Part 04: Multi-Agent Development](workshop/04-multi-agent.md)** - TDD workflows

## ⚠️ Common Pitfalls & Solutions

| Issue | Solution |
|-------|----------|
| **Tests fail after changes** | Run `npm test` before committing; use TDD agent to guide changes |
| **Bingo detection not working** | Check `getWinningSquareIds()` logic in `bingoLogic.ts`; test with all 8 patterns (rows, cols, diagonals) |
| **Styling broken** | Ensure `@tailwindcss/vite` plugin is loaded; check Tailwind v4 `@theme` syntax |
| **HMR not updating** | Restart dev server; check `vite.config.ts` includes React plugin |
| **Build size too large** | Run `npm run build` and check output; Tailwind should tree-shake unused styles |
| **GitHub Pages deploy fails** | Verify `base:` path in `vite.config.ts` matches repo name via `VITE_REPO_NAME` env var |

## 🔄 Workflow Tips

1. **Use Checkpoints:** Save working states in chat before making large changes
2. **Commit Often:** Small, focused commits make debugging easier
3. **Hot Module Reload:** The dev server watches files; changes appear instantly
4. **Questions Data:** Edit `src/data/questions.ts` to customize bingo prompts
5. **Testing First:** Use the TDD agent for new features to maintain quality

## 🌍 Multilingual Support

The workshop guides and docs are available in:
- **English** (default): `workshop/` and `/README.md`
- **Português (BR)**: `workshop/pt_BR/` and `README.pt_BR.md`
- **Español**: `workshop/es/` and `README.es.md`

Deploy previews use locale detection in `docs/` folder.

## 📞 Getting Help

- Review the [workshop GUIDE](workshop/GUIDE.md) for quick reference
- Check [CONTRIBUTING.md](CONTRIBUTING.md) for conventions
- Run `/create-skill` to save custom agent workflows
- Use Checkpoints in chat to track and revert changes

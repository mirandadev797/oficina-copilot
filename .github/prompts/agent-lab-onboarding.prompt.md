---
name: Agent Lab Onboarding
description: Quick reference for understanding this GitHub Copilot Agent Lab project
---

# 🚀 Quick Start for AI Agents

Welcome to the **Bingo Mixer Agent Lab**! This workspace teaches design-first development and multi-agent workflows using a social bingo game.

## 🎯 What Is This?

A **5-part lab** (~1 hour total) where you'll practice:
1. **Setup & Context Engineering** - Teaching AI about the project
2. **Design-First Frontend** - Redesigning the UI with Copilot
3. **Custom Quiz Master** - Building thematic question generators
4. **Multi-Agent Development** - Using TDD and specialized agents
5. **Completion** - Polishing and reviewing

## ⚡ Get Started in 30 Seconds

```bash
cd /workspaces/oficina-copilot
npm install        # Install dependencies
npm run dev        # Start dev server at http://localhost:5173/
npm test           # Verify tests pass
npm run lint       # Check code quality
```

✅ All done! Check [AGENTS.md](AGENTS.md) for the full development guide.

## 🎮 Play the Game First

Before coding, **play Bingo Mixer** to understand what you're building:
- Open http://localhost:5173/ in your browser
- Click "Start Game" and mark 5 squares in a row
- Watch the confetti celebration! 🎉

## 🤖 Key Agents Ready to Use

```
/quiz-master      → Create themed icebreaker questions
/tdd              → Test-Driven Development workflow
/ui-review        → Get design feedback
/pixel-jam        → Create stylized UI variations
```

## 📚 Where to Find Things

- **Game Logic** → `src/utils/bingoLogic.ts` (board generation, bingo detection)
- **Components** → `src/components/` (UI building blocks)
- **Styling** → Uses Tailwind CSS v4 with `@theme` directive
- **Tests** → `src/utils/bingoLogic.test.ts` (Vitest + React Testing Library)
- **Guides** → `workshop/` folder (5 parts in EN/PT-BR/ES)

## ✅ Pre-Work Checklist

Before you start a coding task, verify:
- [ ] Dev server running (`npm run dev`)
- [ ] Tests pass (`npm test`)
- [ ] Lint clean (`npm run lint`)
- [ ] No uncommitted changes (or saved in a checkpoint)

## 💡 Tips

1. **Use Checkpoints** - Save state before big changes, revert if needed
2. **Read the Workshop** - `workshop/GUIDE.md` has quick reference
3. **Inspect Tests** - `bingoLogic.test.ts` shows expected behavior
4. **Design First** - Use planning mode to discuss UI changes before coding
5. **Commit Often** - Small focused commits = easier debugging

## 🎯 Example Tasks

- "Design a dark theme for Bingo Mixer" → Use **design agent** with Plan Mode
- "Add a 'Four Corners' win pattern" → Use **/tdd** agent for test-driven approach
- "Create questions for a tech conference" → Use **/quiz-master** agent
- "Review the current UI and suggest improvements" → Use **/ui-review** agent

## 📖 Full Docs

See [AGENTS.md](AGENTS.md) for complete architecture, conventions, and troubleshooting.

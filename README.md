# Gurukul AI

**AI-powered personalized tutor for Indian students following NCERT/CBSE curriculum (Grade 7-8)**

🎓 **Subjects:** Math, Physics, Chemistry, Biology
📚 **Curriculum:** NCERT/CBSE-aligned
🧠 **Method:** Socratic teaching with adaptive difficulty
🇮🇳 **Context:** Indian examples (rupees, cricket, geography)
🔒 **Privacy:** All student data stays on your machine

---

## What is Gurukul AI?

Gurukul AI is an open-source, AI-powered study tool that acts like a personal tutor. It uses **Socratic questioning** to help you discover answers instead of just giving them away. The tool adapts to your learning style, tracks your mastery of topics, and uses examples from everyday Indian life to make concepts clear.

**Gurukul** means traditional Indian school where guru (teacher) and shishya (student) learn together. That's our philosophy—AI as your patient, encouraging guide.

---

## Features (Phase 0 - Initial Release)

✅ **Socratic Teaching** — Guides you to answers through thoughtful questions
✅ **NCERT-Aligned** — Follows NCERT Grade 7-8 textbooks
✅ **Indian Context** — Examples using rupees, cricket, Indian geography
✅ **Personalized** — Adapts to your learning style (visual, verbal, logical)
✅ **Multi-Skill Architecture** — Subject specialist "teachers" for depth
✅ **Privacy-First** — Your data never leaves your computer

### Currently Available

- **Math (Grade 7):** Integers (addition, subtraction, multiplication)
- **Command:** `/learn math integers`

### Coming Soon (Phase 1-2)

- All Grade 7 Math & Physics chapters
- `/practice`, `/quiz`, `/solve`, `/hint` commands
- Gamification (XP, streaks, badges)
- Spaced repetition for review
- Chemistry & Biology

---

## Quick Start

### Prerequisites

- [Claude Code CLI](https://claude.com/code) installed
- Git
- Anthropic API key (for Claude)

### Installation

```bash
# Clone the repository
git clone https://github.com/your-org/gurukul-ai.git
cd gurukul-ai

# Open in Claude Code
# The skills will auto-discover and load
```

### First Use

1. Open the project in Claude Code
2. Try your first command:
   ```
   /learn math integers
   ```
3. Claude will ask you Socratic questions to teach integers step-by-step

---

## How It Works

### Multi-Skill Architecture

Gurukul AI uses multiple skills that work together:

```
gurukul-ai (Core)           → "Class Teacher"
  ├─ Commands & orchestration
  ├─ Student profile management
  └─ Cross-subject progress tracking

gurukul-ai-math             → "Math Teacher"
  ├─ Math-specific pedagogy
  ├─ Number lines, visual aids
  └─ Common misconception detection

gurukul-ai-physics          → "Physics Teacher" (Coming in Phase 1)
gurukul-ai-chemistry        → "Chemistry Teacher" (Coming in Phase 1)
gurukul-ai-biology          → "Biology Teacher" (Coming in Phase 1)
```

When you ask about math, **both skills co-activate** — core provides the command structure, math provides specialized teaching.

### Your Data is Private

All your learning data stays in the `tracking/` folder on YOUR computer:
- `student-profile.json` — Your grade, learning style, preferences
- `mastery-state.json` — Which topics you've mastered (coming in Phase 2)
- `session-history.json` — Your study sessions (coming in Phase 2)

This folder is in `.gitignore` — it **never gets committed** to git. Your data never leaves your machine.

---

## Project Structure

```
gurukul-ai/
├── .claude/skills/          # Claude Code skills (auto-discovered)
│   ├── gurukul-ai/          # Core orchestrator
│   ├── gurukul-ai-math/     # Math specialist
│   └── ...                  # More subject skills
├── curriculum/              # NCERT-aligned curriculum YAMLs
│   └── cbse/grade-7/
│       └── math.yaml        # Math chapters with answer keys
├── tracking/                # Your personal data (.gitignored)
│   └── student-profile.json
├── resources/               # Formulas, reference tables
│   ├── formulas/
│   └── shared/
└── README.md
```

---

## Commands (Phase 0)

| Command | Description | Example |
|---------|-------------|---------|
| `/learn <subject> <topic>` | Learn a concept with Socratic questioning | `/learn math integers` |

**Coming in Phase 1:**
- `/practice <subject> <topic>` — Practice problems
- `/quiz <subject>` — Timed assessment
- `/solve <problem>` — Step-by-step solution
- `/hint` — Get a hint
- `/progress` — See your mastery dashboard
- `/formulas <subject>` — View formula sheet

---

## For Contributors

Gurukul AI is community-driven! We welcome contributions:

### How to Contribute

1. **Add curriculum content** — Create YAML files for new chapters
2. **Add subject skills** — Create new subject specialist skills
3. **Translate content** — Add Hindi/regional language translations
4. **Report errors** — Found a wrong answer? Use `/report-error`
5. **Code improvements** — Python generators, MCP tools (Phase 4)

See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines (coming soon).

### Why Multi-Skill Architecture?

Each subject has its own skill file:
- **Subject experts own their subject** — Math teachers review math PRs only
- **Zero merge conflicts** — Editing math skill doesn't affect physics skill
- **Easy to add subjects** — New subject = new skill directory, zero changes to existing code
- **Scales to 100+ skills** — Proven by K-Dense-AI's 140+ scientific skills

---

## Roadmap

### ✅ Phase 0 (Current) — Architecture Validation
- [x] Multi-skill architecture
- [x] Core + Math skills
- [x] Grade 7 Math Integers curriculum
- [x] `/learn` command
- [ ] Quality validation with real Grade 7 student

### 🚧 Phase 1a (1-2 weeks) — Math & Physics
- [ ] All Grade 7 Math chapters
- [ ] All Grade 7 Physics chapters
- [ ] Full command suite
- [ ] Physics subject skill

### 📅 Phase 1b (1-2 weeks) — Chemistry & Biology
- [ ] Chemistry & Biology subject skills
- [ ] Grade 7 Chemistry & Biology curricula

### 📅 Phase 2 (2 weeks) — Personalization & Gamification
- [ ] Mastery tracking (BKT algorithm)
- [ ] Gamification (XP, streaks, badges)
- [ ] Spaced repetition
- [ ] Progress reports for parents

### 📅 Phase 3 (2 weeks) — Open Source Release
- [ ] Test with real Grade 7 students
- [ ] Community infrastructure (CONTRIBUTING, CODE_OF_CONDUCT, CI)
- [ ] README with screenshots/GIFs

### 📅 Phase 4 — MCP & Grade 8
- [ ] MCP server for structured tools
- [ ] Grade 8 curriculum
- [ ] PDF worksheet generation

### 📅 Phase 5 — Web Platform
- [ ] Browser-based access
- [ ] Multi-language support (Hindi, Tamil, Telugu)
- [ ] Open-weight model backends (Llama, Gemma)

---

## Philosophy & Principles

1. **Socratic over Didactic** — Guide, don't tell
2. **NCERT-Aligned** — Follow official curriculum
3. **Misconception-Aware** — Proactively detect and fix student errors
4. **Privacy-First** — Student data never leaves their machine
5. **Open Source** — Any student can benefit
6. **Indian Context** — Examples from daily Indian life
7. **Community-Driven** — Built by educators and students together

---

## Tech Stack

- **Skills:** Claude Code's SKILL.md format
- **LLM:** Claude Opus/Sonnet via Anthropic API
- **Data:** Local JSON files (privacy-by-design)
- **Curriculum:** YAML (human-readable, git-friendly)
- **Future:** MCP server, Python generators, Web platform

---

## License

MIT License — use freely, contribute openly, share widely.

---

## Acknowledgments

Inspired by:
- [Mr. Ranedeer AI Tutor](https://github.com/JushBJJ/Mr.-Ranedeer-AI-Tutor) — Prompt engineering patterns
- [K-Dense-AI Scientific Skills](https://github.com/K-Dense-AI/claude-scientific-skills) — Multi-skill architecture
- [Tutor-GPT](https://github.com/plastic-labs/tutor-gpt) — Dual-chain pedagogical pattern
- [OATutor](https://github.com/CAHLR/OATutor) — Bayesian knowledge tracing
- NCERT — Curriculum and terminology

---

## Support

- 📖 **Docs:** See [session-context.md](session-context.md) for full project context
- 🐛 **Bugs:** [Open an issue](https://github.com/your-org/gurukul-ai/issues)
- 💬 **Discuss:** [GitHub Discussions](https://github.com/your-org/gurukul-ai/discussions)

---

**Made with ❤️ for Indian students. Built by the community, for the community.**

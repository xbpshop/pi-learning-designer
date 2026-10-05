# pi-learning-designer

A [Pi](https://pi.dev) skill that turns Pi into a senior learning experience designer for Revenue Enablement / LnD work.

What it does:
- Explains frameworks and concepts visually first (Mermaid diagrams, tables, HTML one-pagers)
- Designs programs and sessions with backward design: behavior change -> needs analysis -> program map -> measurement
- Critiques decks and content against a design checklist
- Builds immersive, animated HTML explainers (no "boxy card dashboard" look)
- Carries a playbook of proven instructional taste: one real merchant example, evidence-traced content, game mechanics for sellers, top-3 not exhaustive

## Install

```bash
# from git
pi install git:github.com/xbpshop/pi-learning-designer

# try once without installing
pi -e git:github.com/xbpshop/pi-learning-designer

# or copy just the skill folder
cp -R skills/learning-designer ~/.pi/skills/
```

Then run `/reload` in Pi (or restart) and use `/skill:learning-designer <your ask>`.

## Usage

```
/skill:learning-designer explain Kirkpatrick levels
/skill:learning-designer design a 3-stage program for SEs on retail POS
/skill:learning-designer critique this deck: ./onboarding.pdf
```

## Layout

```
skills/learning-designer/
├── SKILL.md                          # core rules and workflows
└── references/
    ├── design-method.md              # methodology + critique checklist
    ├── instructional-playbook.md     # taste rules from real programs
    └── visual-language.md            # HTML explainer craft bar + design log
```

The design log (anti-repetition for HTML builds) defaults to `~/.learning-designer/design-log.md`.

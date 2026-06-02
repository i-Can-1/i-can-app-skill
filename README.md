# App Skill

`app` is a Codex controller skill for turning product ideas into runnable websites, web apps, software tools, CLI utilities, automation projects, or SaaS prototypes.

It guides Codex through:

- idea clarification and MVP definition
- stack selection for new or existing projects
- visual design exploration with multiple options
- animation and motion direction
- implementation
- testing and debugging
- browser verification and screenshots
- README or usage documentation

## Defaults

- Substantial web apps: Next.js, React, and Tailwind
- Backend persistence: Node/Express and SQLite
- Simple prototypes: local state or localStorage when appropriate
- Real web animation: CSS/Tailwind transitions, Framer Motion, or GSAP
- Motion previews and product demos: HyperFrames

## Installation

Copy the `app` folder into your Codex skills directory:

```text
$CODEX_HOME/skills/app
```

If `CODEX_HOME` is not set, use your Codex skills directory, commonly:

```text
~/.codex/skills/app
```

Restart Codex after installing.

## Usage

Example prompt:

```text
Use app to turn this idea into a runnable web app. Generate visual and animation options first, then implement the selected direction.
```

## Included Files

```text
app/
  SKILL.md
  agents/
    openai.yaml
```


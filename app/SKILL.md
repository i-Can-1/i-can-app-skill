---
name: app
description: Use when the user provides a product idea, website idea, app concept, software project brief, tool request, or asks Codex to turn an idea into a runnable website, web app, desktop-style app, CLI tool, SaaS prototype, or software product.
---

# App

## Overview

Turn a product or software idea into a runnable project. Support websites, web apps, desktop-style apps, CLI tools, automation tools, SaaS prototypes, and small full-stack products.

Favor working software over long proposals. When details are missing, make practical assumptions and implement, stopping only for choices that materially affect product direction, cost, security, or irreversible work.

## Operating Defaults

- **Project type**: infer from the idea; support web, desktop-style web apps, CLI tools, and automation scripts.
- **Existing code**: if a repo exists, inspect it first and follow its stack, style, scripts, and conventions.
- **Greenfield default**: use Next.js + React + Tailwind for substantial web apps and SaaS-style products.
- **Simple static default**: use plain HTML/CSS/JS only when the idea is clearly a simple static page or tiny demo.
- **Backend default**: use Node/Express + SQLite when persistence or APIs are needed.
- **No backend default**: use local state or localStorage for small prototypes that do not need server persistence.
- **UI style**: for websites and visual software, ask targeted design questions and generate 2-3 visual options before final implementation when visual direction matters.
- **Motion design**: for animated websites or software, ask about animation intensity and generate motion prototypes before final implementation when motion affects the experience.
- **Automation**: proceed as far as possible autonomously, including implementation and verification.
- **Dependencies**: common dependencies may be installed or attempted; if install fails due to network/sandbox, request approval rather than silently degrading the product.
- **Verification**: completion requires a running app, tests or smoke checks, browser inspection for UI apps, screenshot/visual verification when relevant, and a README or usage note.
- **Plugins/connectors**: if product work needs an unavailable plugin or connector, explain the exact capability needed and ask the user before installing or enabling it.

## Required Sub-Skills

Use these skills when available and relevant:

- `writing-plans` for multi-step project implementation plans.
- `executing-plans` for carrying out an approved or inferred implementation plan.
- `test-driven-development` for new features, bug fixes, and core logic.
- `systematic-debugging` for test failures, runtime errors, or unexpected behavior.
- `verification-before-completion` before claiming the app is done.
- `requesting-code-review` for substantial or risky projects.
- `finishing-a-development-branch` when committing, merging, or preparing a branch for handoff.
- `browser:control-in-app-browser` for local UI verification, interaction checks, and screenshots.
- `figma:figma-generate-design` or `figma:figma-use` only when the user asks for Figma/design artifacts or provides a Figma URL.
- `hyperframes:gsap` only when the project needs complex GSAP-style timelines, scroll-driven effects, or video-like web motion references.
- `hyperframes:hyperframes` for HTML-based motion previews, product demo videos, launch videos, animated explainers, title cards, overlays, captions, narration, and scene transitions.
- `hyperframes:hyperframes-cli` for scaffolding, linting, inspecting, previewing, and rendering HyperFrames projects.
- `hyperframes:website-to-hyperframes` when the user provides a website URL or asks to turn an existing website/app into a product tour, promo, or social video.
- `imagegen` only for bitmap moodboards, hero imagery, marketing visuals, or non-UI concept art. Prefer coded UI mockups plus browser screenshots for actual app screens.

## Plugin And Connector Needs

During the product workflow, check whether a plugin or connector would materially improve the task, such as Browser for local UI inspection, Figma for collaborative design, GitHub for issues/PRs, Documents/Presentations/Spreadsheets for deliverables, or hosting/cloud tools for deployment.

If the needed capability is not currently available:

- name the exact plugin or connector
- explain the product task it unlocks
- state whether it needs account access, network access, paid resources, or external files
- ask the user for confirmation before installation
- install only the specific approved plugin/connector

Do not request broad or speculative plugin installs. Continue with a local fallback when the plugin is optional or the user declines.

## Workflow

### 1. Understand The Idea

Extract:

- target user
- core job to be done
- primary workflow
- required screens or commands
- data model
- integrations
- privacy or security concerns
- deployment or runtime expectations
- must-have vs nice-to-have features

Ask at most one concise question only when the answer changes the product category, UI direction, persistence model, or security posture. Otherwise, state assumptions briefly and proceed.

### 2. Choose Project Path

If an existing repo is present:

- read package/config files first
- identify build, test, lint, and dev commands
- follow the existing framework and design system
- avoid broad rewrites
- preserve unrelated user changes

If no repo exists:

- create a focused project in the current workspace unless the user specifies another location
- choose the smallest stack that can deliver the idea well
- prefer Next.js + React + Tailwind for rich web apps
- use Node/Express + SQLite only when server persistence or API boundaries are useful
- use CLI/script structure for automation tools rather than forcing a web UI

### 3. Define The MVP

Create a concise implementation target before coding:

- user-facing outcome
- feature list
- screens or commands
- data entities
- success criteria
- verification commands

Do not create a marketing landing page when the user asked for an app, tool, game, dashboard, or workflow product. Build the usable experience as the first screen.

### 4. Visual Design Selection Gate

For websites, dashboards, visual tools, desktop-style apps, games, and any UI-heavy product, run this gate before final implementation unless the user says to skip design exploration.

Ask concise design questions covering the decisions that matter:

- target audience and product category
- preferred mood, e.g. professional, playful, futuristic, editorial, minimal, premium, technical
- color preferences or colors to avoid
- light, dark, or adaptive theme
- information density, e.g. compact tool, balanced dashboard, spacious presentation
- device priority, e.g. desktop-first, mobile-first, responsive equal priority
- animation preference, e.g. none, subtle, polished, expressive, playful, cinematic, data-driven
- motion sensitivity constraints, including reduced-motion support
- reference products or screenshots, if the user has any
- brand name/logo/assets, if relevant

If the user already provided enough direction, do not ask again; summarize assumptions and proceed.

Generate 2-3 distinct visual directions:

- give each option a short name
- state palette, layout structure, typography feel, density, and interaction style
- create lightweight coded mockups for the most important screen or flow
- include short motion prototypes for transitions, hover states, loading states, page changes, or hero interactions when animation matters
- use the browser to capture screenshots/effect images for each option
- when static screenshots cannot communicate the effect, describe the motion precisely and, if available, capture a short browser/video preview
- present the screenshots and ask the user to choose, combine, or revise

Prefer real HTML/CSS/React mockups over AI-generated UI images because they are closer to implementable software. Use Figma only when the user explicitly wants Figma artifacts or collaboration. Use image generation for moodboards, hero backgrounds, illustrations, or marketing imagery, not as the source of truth for app UI.

After the user chooses, implement the selected direction and record it in the README or project notes.

### 5. HyperFrames Motion And Video Gate

Use this gate when the user wants animated visual options, a motion preview, product demo video, launch/promo video, social ad, narrated walkthrough, or a video generated from an existing website.

Choose the right path:

- **Interactive web animation**: implement in the app with CSS, Framer Motion, or GSAP. Use HyperFrames only as a motion reference or preview artifact.
- **Motion concept preview**: create 1-3 short HyperFrames concepts to help the user choose pacing, transitions, rhythm, and visual energy.
- **Product demo or launch video**: create a HyperFrames storyboard and composition from the app screens, product story, or website capture.
- **Existing website to video**: use `hyperframes:website-to-hyperframes` when the user provides a URL or asks to turn a site into a video.

For HyperFrames work:

- define visual identity first: mood, theme, palette, fonts, brand references, and what to avoid
- write or summarize a short storyboard before composition work
- use `hyperframes:hyperframes` for composition and timing rules
- use `hyperframes:hyperframes-cli` for `npx hyperframes lint`, `inspect`, and `preview`
- provide the Studio URL after preview
- render MP4/WebM only when the user explicitly asks for a rendered video

Do not confuse HyperFrames video artifacts with the real app UI. The shipped app must still implement its own interactive animations when the user wants animated software.

### 6. Design The Experience And Motion

For UI projects:

- match the domain and audience
- build dense, ergonomic tools for SaaS, CRM, admin, and operational products
- use expressive visuals only when the product type benefits from them
- use icons for common commands when available
- avoid decorative clutter, nested cards, overlapping text, and one-note palettes
- make responsive layouts with stable dimensions for boards, grids, toolbars, counters, and fixed-format controls
- ensure mobile and desktop text fits its container

For animated UI:

- use animation to clarify state changes, hierarchy, feedback, and flow
- keep operational tools subtle and fast; reserve expressive motion for games, creative sites, product launches, and immersive demos
- prefer CSS transitions/animations for simple interaction polish
- prefer Framer Motion for React component transitions, layout motion, and interaction states when already suitable for the stack
- use GSAP only for complex timelines, scroll-driven sequences, chained choreography, or canvas/SVG-heavy motion
- respect `prefers-reduced-motion`
- avoid animations that block workflows, hide information, cause layout shift, or make repeated use tiring
- define durations, easing, and trigger conditions consistently

The final UI must be based on the selected visual direction from the Visual Design Selection Gate when that gate was used.

### 7. Implement

Build complete workflows, not isolated mockups.

Requirements:

- wire screens to state and actions
- implement empty, loading, success, and error states where relevant
- add persistence when promised
- implement selected animation and interaction behavior when motion was part of the chosen direction
- validate user input
- make navigation usable
- keep components and files aligned with existing conventions
- add comments only for non-obvious logic
- avoid unrelated refactors

For full-stack apps:

- define clear API boundaries
- use SQLite for local durable storage unless the repo already has a database
- add minimal schema/migration setup when needed
- handle common API errors

### 8. Test And Debug

Run the relevant checks:

- install dependencies when needed
- run lint/typecheck/test scripts if available
- add focused tests for core logic and risky flows
- run smoke tests for CLI/API projects
- start the dev server for web apps
- use the browser to inspect local UI, interact with primary workflows, and capture screenshots when relevant
- verify animations in the browser for timing, smoothness, responsiveness, reduced-motion behavior, and absence of layout shift
- for HyperFrames artifacts, run lint and visual inspect before preview; render only when requested

If a check fails, use systematic debugging. Fix root causes rather than weakening tests or removing features.

### 9. Document

Create or update a concise README or usage note with:

- what the app does
- how to install dependencies
- how to run locally
- how to test
- important assumptions
- remaining limitations

Do not over-document obvious implementation details.

## Checkpoints

Pause and ask the user when:

- the idea can become two materially different products
- UI style is open and not implied by the domain
- the user needs to choose between generated visual directions before final implementation
- paid services, external accounts, or API keys are required
- a needed plugin or connector is unavailable and would require installation or account access
- destructive migration or cleanup is needed
- security-sensitive data handling is unclear
- the same root cause blocks progress three times

Otherwise, continue to the next concrete step.

## Completion Standard

Do not claim completion until:

- the app or tool exists on disk
- it can be run locally
- the main workflow has been exercised
- relevant tests or smoke checks have run
- browser verification and screenshot/visual inspection are done for UI apps
- selected visual direction and final UI screenshots are available for visual projects
- animation behavior has been browser-checked when motion is part of the project
- HyperFrames preview URL is available when a motion/video artifact was created
- README or usage instructions are present

Final response must include:

- what was built
- where the files are
- commands run
- verification results
- selected design option and screenshot paths for UI projects
- selected animation direction and verification notes for animated UI projects
- HyperFrames preview URL and render path, if video artifacts were created
- local URL if a dev server is running
- known limitations or follow-up work

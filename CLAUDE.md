# CLAUDE.md

## Mission

Build this Expo app in small, safe, reproducible steps.
Keep the app runnable at all times.

---

## Context Loading Rules (IMPORTANT)

Always assume the following files are part of the working context:

- docs/PROJECT.md
- docs/ARCHITECTURE.md
- docs/STACK.md

These files define:
- product vision
- architecture decisions
- technical constraints

Never ignore them, even if they are not explicitly mentioned.

---

## Task Resolution

Tasks are stored in:

tasks/<number>-<name>.md

When a task is referenced (e.g. "Task 002"):

- automatically resolve the matching file in /tasks
- load and follow its instructions
- treat it as the primary implementation source

Example:
Task 002 → tasks/002-home-screen.md

---

## Working Style

- make the smallest reasonable change
- prefer simple solutions
- do not refactor broadly unless required
- preserve existing structure
- explain when rebuild is required

---

## Boundaries

- do not upgrade Expo SDK unless explicitly asked
- do not add unnecessary dependencies
- prefer:
  npx expo install <package>
- do not use --force or --legacy-peer-deps

---

## App Safety Rules

- app must remain runnable
- no breaking boot flow
- no unnecessary architectural changes

---

## Validation Rules

After changes:

- ensure app starts
- no crash / no red screen

Recommended commands:

npm install  
npx expo start --clear  

Optional:

npx expo-doctor  

---

## Definition of Done

- task implemented
- app runs
- feature works
- no unintended changes

---

## Response Format

Always provide:

1. what changed
2. why
3. rebuild needed? (yes/no)
4. how to test
5. next step (optional)

---

## Short Rule

Keep it simple. Keep it running. Follow the task.
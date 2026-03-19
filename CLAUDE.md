# Project Overview
This repository contains:
- Expo / React Native app for Android and iOS
- Shared frontend code for mobile and web where feasible
- Supabase as backend (database, auth, storage, edge functions if used)
- Vercel for web deployment


# Architecture
- Use Expo-managed workflow unless a native module explicitly requires prebuild/eject.
- Keep business logic out of screens; use hooks/services/lib modules.
- Supabase access must be centralized in a small client layer.
- Do not mix server-only code into Expo client code.
- Web deployment targets Vercel.

# File Organization
- App routes/screens live in `src/screens/`
- Reusable UI components live in `src/components/`
- Supabase client/config lives in `src/supabase/`
- Business/domain logic lives in `src/domain/`
- Shared types live in `src/types/`

# Development Workflow
- Install dependencies with `npm install`
- Start Expo dev server with `npx expo start`
- Run web locally with `npx expo start --web`
- Run tests with `npm test`
- Run lint with `npm run lint`
- Before major changes, propose a short plan first.

# Platform Rules
- Prefer Expo-compatible libraries.
- Avoid native dependencies unless there is no Expo-first alternative.
- Any platform-specific code must be isolated clearly.
- Keep Android, iOS, and web parity in mind, but do not force identical UX when platform conventions differ.

# Supabase Rules
- Never hardcode keys or secrets.
- Use environment variables for Supabase URL and anon key.
- Do not put service-role secrets into client code.
- Prefer typed queries and central helper functions.
- Schema changes must be represented as migrations.

# Deployment
- Web deploys to Vercel.
- Mobile builds use Expo/EAS.
- Do not introduce deployment assumptions that require a custom server unless explicitly requested.

# Do / Don’t
Do:
- keep changes minimal and scoped
- reuse existing patterns before introducing new abstractions
- update types when API/data shapes change

Do not:
- add new state libraries without a clear reason
- duplicate Supabase access logic across screens
- store secrets in the repo
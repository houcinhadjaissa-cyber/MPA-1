# MPA TERMINAL — REPLIT BUILD INSTRUCTIONS

## ⚠️ CRITICAL: READ EVERY WORD BEFORE TOUCHING ANYTHING

You are building the **MPA Terminal** — a Next.js 14 prompt engineering platform. This is NOT a new project. The code already exists and is 100% complete. Your ONLY job is to:

1. **DELETE ALL EXISTING FILES** in this Replit project
2. **COPY ALL FILES** from this ZIP/package into the project root
3. **RUN `npm install`** then **`npm run build`** to verify it compiles
4. **PUSH to GitHub**

## STEP 1: NUCLEAR DELETE (MANDATORY — DO NOT SKIP)

```bash
# Delete EVERYTHING in the project root except .git and .replit
find . -maxdepth 1 ! -name '.' ! -name '.git' ! -name '.replit' -exec rm -rf {} +
```

## STEP 2: UPLOAD ALL FILES

Upload/copy ALL files from the package into the project root. The file structure MUST be:

```
/
├── .env.example
├── .gitignore
├── next.config.mjs
├── package.json
├── postcss.config.mjs
├── tailwind.config.ts
├── tsconfig.json
├── app/
│   ├── api/
│   │   ├── chat/route.ts
│   │   └── groq/route.ts
│   ├── globals.css
│   ├── layout.tsx
│   ├── not-found.tsx
│   └── page.tsx
├── components/
│   └── mpa/
│       ├── ChatPanel.tsx
│       ├── DynamicIsland.tsx
│       ├── LayerPanel.tsx
│       ├── MobileNav.tsx
│       ├── OutputViewer.tsx
│       ├── ProjectVault.tsx
│       ├── SettingsPanel.tsx
│       └── TemplateSelector.tsx
└── lib/
    ├── crypto.ts              ← CRITICAL — DO NOT DELETE
    ├── immutableCore.ts       ← CRITICAL — DO NOT DELETE
    ├── nextWaveCore.ts        ← CRITICAL — DO NOT DELETE
    ├── omegaCore.ts           ← CRITICAL — DO NOT DELETE
    ├── payloadGenerator.ts    ← CRITICAL — DO NOT DELETE
    ├── worker.ts              ← CRITICAL — DO NOT DELETE
    ├── utils.ts
    └── mpa/
        ├── layers.ts
        ├── storage.ts
        └── templates.ts
```

## STEP 3: VERIFY ALL 6 CRITICAL FILES EXIST

Before running npm install, verify these files exist. If ANY are missing, STOP and fix:

```bash
ls -la lib/crypto.ts lib/immutableCore.ts lib/nextWaveCore.ts lib/omegaCore.ts lib/payloadGenerator.ts lib/worker.ts
```

All 6 MUST show file details. If any says "No such file", the upload failed.

## STEP 4: INSTALL & BUILD

```bash
npm install
npm run build
```

If `npm install` fails, try:
```bash
rm -rf node_modules package-lock.json
npm install --legacy-peer-deps
npm run build
```

## STEP 5: PUSH TO GITHUB

```bash
git add -A
git commit -m "MPA Terminal v1.0 — Complete rebuild with all core engines"
git push origin main
```

## WHAT THIS APP DOES

- **MPA Terminal** is a prompt engineering platform with 17 intelligence layers
- The user types a target description → the app generates a comprehensive AI prompt via Groq/OpenAI
- **lib/payloadGenerator.ts** = The core prompt assembly engine (composable prompt blocks, Groq API calls, streaming)
- **lib/immutableCore.ts** = TypeScript interfaces for the 56-Pillar architecture (immutable boundary)
- **lib/nextWaveCore.ts** = Adversarial AI auditor + cohesion director + topological yield calculator + all singularity engines
- **lib/omegaCore.ts** = Self-healing matrix (schema-agnostic parser, mutex queue, resilience wrapper, resource governor)
- **lib/worker.ts** = Web Worker for Monte Carlo simulations and TDA Betti number computation
- **lib/crypto.ts** = Real WebCrypto PBKDF2 + AES-GCM encryption with base64 fallback

## DO NOT:
- ❌ Delete any of the 6 lib/*.ts files
- ❌ Add `output: "standalone"` to next.config.mjs
- ❌ Add Prisma, SQLite, or any database
- ❌ Add `z-ai-web-dev-sdk` (only works on one platform, not Vercel)
- ❌ Add `adm-zip` (causes npm install to crash on Vercel)
- ❌ Change the app/ directory structure
- ❌ Merge this with any old project files
- ❌ Add a /dashboard route — the app now lives at /
- ❌ Add a ?key=omega gate — the app loads directly
- ❌ Change package.json dependencies without explicit instruction

## VERCEL DEPLOYMENT CHECKLIST

After pushing to GitHub, in Vercel:
1. Import the GitHub repo
2. Framework Preset: **Next.js**
3. Build Command: `npm run build`
4. Output Directory: `.next`
5. Environment Variables: Add `GROQ_API_KEY` and/or `OPENAI_API_KEY`
6. Deploy

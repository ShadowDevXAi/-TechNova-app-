# TechNova OS — Genesis 0.1

Universal adaptive workspace for Windows, macOS, Linux, Android, iOS and web.

## Stack
- React + TypeScript + Vite
- Tauri 2 for desktop
- Capacitor for Android and iOS
- PWA for web
- FastAPI + MongoDB for shared services

This repository introduces the OS client separately. It does not migrate or duplicate existing TechNova portal data. Connect the portal only after auditing its API contracts and authorization rules.

## Requirements
Node.js 22+, Python 3.12+, Rust and Windows C++ Build Tools for Windows desktop builds, Android Studio for Android builds, and macOS/Xcode for iOS builds.

## Frontend
```powershell
cd apps/universal
npm install
npm run dev
```

## Desktop
```powershell
npm run tauri:init
npm run tauri:dev
npm run tauri:build
```

## Android
```powershell
npm run cap:add:android
npm run android:build
npm run android:open
```

## iOS (macOS + Xcode)
```bash
npm run cap:add:ios
npm run ios:build
npm run ios:open
```

## Backend
```powershell
cd services/api
python -m venv .venv
.venv\\Scripts\\activate
pip install -r requirements.txt
copy .env.example .env
uvicorn app.main:app --reload --port 8000
```

Copy `apps/universal/.env.example` to `.env.local`. Never commit secrets.

Genesis 0.1 is a foundation: adaptive shell, desktop window manager, mobile navigation, preferences, PWA/native packaging scaffold and health-checked API. Authentication is intentionally not enabled until existing TechNova authentication APIs are reviewed and integrated.

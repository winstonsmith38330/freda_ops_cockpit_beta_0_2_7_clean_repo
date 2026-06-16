# Beta 0.2.7 Render Hotfix

This hotfix removes the mandatory `import 'dotenv/config'` startup dependency from `server/server.js`.

Render environment variables are injected directly into `process.env`, so dotenv is not required for production startup. This avoids the Render startup error:

```
ERR_MODULE_NOT_FOUND: Cannot find module .../node_modules/dotenv/config imported from .../server.js
```

Also pins Node through `server/package.json` engines:

```json
"engines": { "node": "20.x" }
```

Recommended Render settings:

- Root Directory: `server`
- Build Command: `npm install --no-audit --no-fund`
- Start Command: `npm start`
- Environment: `NODE_VERSION=20.18.0`

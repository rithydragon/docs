
# Nuxt Docs and Guide
### Official Nuxt 4 Project Structure (as of v4.0.1)
#### Here is the formal and complete structure of a standard Nuxt 4 project after initialization (e.g. via nuxi init or npx nuxi@latest init):
```
project/
├── app/                  ← NEW default source directory (srcDir)
│   ├── app.vue           ← Root Vue app component (like layout + entry point)
│   ├── layouts/          ← Application layouts
│   │   └── default.vue
│   ├── pages/            ← File-based routing
│   │   └── index.vue
│   ├── components/       ← Auto-imported components
│   ├── composables/      ← Auto-imported composables
│   ├── middleware/       ← Route middleware
│   ├── plugins/          ← Nuxt plugins
│   ├── server/           ← Server routes, API endpoints
│   │   └── api/
│   ├── assets/           ← Raw assets (CSS, images, fonts, etc.)
│   ├── public/           ← Static files served as-is
│   └── error.vue         ← Custom error page
│
├── nuxt.config.ts        ← Nuxt config (TypeScript by default)
├── package.json
├── tsconfig.json
├── .nuxt/                ← Auto-generated Nuxt internals (ignored)
└── node_modules/
```
### 🔍 Key Structural Changes from Nuxt 3
``` list
| Feature/Directory   | Nuxt 3                   | Nuxt 4                   |
| ------------------- | ------------------------ | ------------------------ |
| `srcDir`            | `.` (root) or `/src`     | **`/app`** by default    |
| App entry           | `app.vue` in root        | **`app/app.vue`**        |
| Config              | `nuxt.config.ts`         | Same                     |
| Runtime APIs        | `server/api/`            | Still valid under `app/` |
| Layouts, pages etc. | Global or `src/` folders | Now live under `app/`    |
```

#### 🛠 Example nuxt.config.ts
```
// nuxt.config.ts
export default defineNuxtConfig({
  srcDir: 'app/',  // now default; optional unless overridden
  modules: [],
  app: {
    head: {
      title: 'My Nuxt 4 App',
      meta: [{ name: 'description', content: 'Awesome app built with Nuxt 4' }]
    }
  }
})
```

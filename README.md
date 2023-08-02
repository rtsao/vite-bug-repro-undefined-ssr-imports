# vite-bug-repro-undefined-ssr-imports

This app reproduces an edge case where SSR imports can be unexpectedly undefined.

Reproduction steps:
```bash
corepack enable
pnpm install
node app/server.mjs
open http://localhost:5173
```

Notice that SSR crashes with `TypeError: __vite_ssr_import_0__.getB is not a function`

This bug arises in some situations with files with a (perfectly valid) import cycle.

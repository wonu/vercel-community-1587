## Reproduction steps

### 1. Install (branch `main`)

```sh
$ npx create-remix
? Where would you like to create your app? ./vercel-community#1587
? What type of app do you want to create? Just the basics
? Where do you want to deploy? Choose Remix App Server if you're unsure; it's easy to change deployment targets. Vercel
? TypeScript or JavaScript? TypeScript
? Do you want me to run `npm install`? No
```

### 2. Add `__foo.tsx` and modify `index.tsx` (branch `__foo`)

- Works well on local
- Build fails on `VERCEL_CLI_VERSION=vercel@28.15.5` and above
- Build succeeds on `VERCEL_CLI_VERSION=vercel@28.15.4` but has server error due to missing `serverBuildTarget`

### 3. Add `serverBuildTarget: "vercel"` (branch `serverBuildTarget`)

- Works well on `VERCEL_CLI_VERSION=vercel@28.15.4`

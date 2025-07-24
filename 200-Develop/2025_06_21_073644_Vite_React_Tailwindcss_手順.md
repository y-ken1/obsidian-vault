---
aliases:
  - vite
  - Vite
  - react
  - React
  - Tailwind
  - tailwind
  - Tailwindcss
  - tailwindcss
tags:
  - vite
  - react
  - tailwindcss
created:
  - 2025-06-21 07:36:44
---

## ViteをReactで作成

```bash
npm create vite@latest my-app -- --template react-ts
cd my-app
```


## Tailwindcssインストール　V4からviteになった

```bash
npm install tailwindcss @tailwindcss/vite
```

## vite.config.tsの編集（なければファイルを作る）
		
vite.config.ts
```TypeScript
import { defineConfig } from "vite";
import react from "@vitejs/plugin-react";
import tailwindcss from '@tailwindcss/vite'

export default defineConfig({
  plugins: [react(), tailwindcss()],
});
```


## vite.config.tsの編集（サブフォルダの場合）
		
vite.config.ts
```TypeScript
import { defineConfig } from "vite";
import react from "@vitejs/plugin-react";
import tailwindcss from '@tailwindcss/vite'

export default defineConfig({
  base: "/hoge/", // ← サブフォルダを指定
  plugins: [react(), tailwindcss()],
});
```


## index.cssの編集

index.css
```css
@import "tailwindcss";
```

---
aliases:
  - vite,Vite,react,React,Tailwind,tailwind,Tailwindcss,tailwindcss
tags: 
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
import { defineConfig } from 'vite'
import tailwindcss from '@tailwindcss/vite'

export default defineConfig({ 
  plugins: [
    tailwindcss(), 
  ],
})
```

## index.cssの編集

index.css
```css
@import "tailwindcss";
```

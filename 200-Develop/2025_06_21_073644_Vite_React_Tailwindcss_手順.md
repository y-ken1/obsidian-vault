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

### ボイラーテンプレートから

```bash
git clone https://github.com/y-ken1/boilerplate-react.git <プロジェクト名>

# プロジェクトフォルダに移動
cd <プロジェクト名>

# ボイラーテンプレートのgitを削除
rm -rf .git

# git初期化
git init

# パッケージインストール
npm install

# ローカルサーバ実行
npm run dev
```


### 以下はボイラーテンプレートを使わない方法

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

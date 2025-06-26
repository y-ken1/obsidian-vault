---
aliases: 
tags:
  - netlify
created:
  - 2025-06-26 15:44:44
---

# Netlify_Funcitons_デプロイ

## 本番デプロイ

```bash
netlify deploy --prod --dir=empty
```


### 補足

dir=empty について(ChatGPT より)

> Functions だけデプロイしたいなら、publish = "empty" にして空のディレクトリを作るのがベスト
> Web ページ部分が不要でも、Netlify は何かしらの publish ディレクトリを要求するため、それを最小構成にする

  
## ファイル構成
- netlify は function/にフラットに各ファイルを置くこと
- つまり、src/functions/ に 各 function を置く（サブフォルダは作らない）
- 共通で使う関数も src/functions/ に置くこと
- 
らしい

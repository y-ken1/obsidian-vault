---
aliases:
  - netlify
  - Netlify
tags:
  - curl
  - netlify
created:
  - 2025-06-23 13:29:31
---


# curlでnetlify-functionsにGET

```bash
# エンドポイント hello

curl "http://localhost:8888/.netlify/functions/hello?name=XXXX"
```


# curlでnetlify-functionsにPOST

```bash
# エンドポイント hello
# リクエストデータ {"message": "World", "key": "my key"}

curl -X POST http://localhost:8888/.netlify/functions/hello \
  -H "Content-Type: application/json" \
  -d '{"message": "World", "key": "my key"}'
```

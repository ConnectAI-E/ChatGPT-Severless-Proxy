# ChatGPT-API-Proxy
![GitHub](https://img.shields.io/github/license/Heng-Bian/ChatGPT-API-Proxy)
![GitHub](https://img.shields.io/badge/build-pass-green)  
A reverse proxy of https://api.openai.com that supports token load-balance and avoids token leakage

openai api reference
`https://platform.openai.com/docs/api-reference`
## Feature

- simple, clean but efficent code
- providing an authorization without openai token leakage
- supproting token load-balance
- avoiding the limitation of single openai token
- removing invalid token automatically

## Quick start
```nashorn js
cd code
mv config.example.yaml config.yaml
```
```
OPENAI_KEY: sk-xxx,sk-xx
AUTH_TOKEN: xxxxxxx
PORT: 9000
TARGET: https://api.openai.com
```

```
go run main.go
```

部署阿里云函数计算
```
cd ..
s deploy
```


Use by cURL
```
curl --location 'http://localhost:8080/v1/chat/completions' \
--header 'Authorization: Bearer YOUR_AUTHORIZATION' \
--header 'Content-Type: application/json' \
--data '{
    "max_tokens": 250,
    "model": "gpt-3.5-turbo",
    "messages": [
        {
            "role": "user",
            "content": "Hello!"
        }
    ]
}'
```

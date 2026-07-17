<p align="center">
  <img src="https://sfapi.pythonanywhere.com/static/sixfinger-logo.jpg" width="100" />
</p>

<h1 align="center">Sixfinger API</h1>
<p align="center"><strong>Single API. 25+ models. Credit-based billing. Streaming built in.</strong></p>

<p align="center">
  <a href="https://discord.gg/AtwqzqpwR8"><img src="https://img.shields.io/badge/Discord-Join%20Server-5865F2?logo=discord&logoColor=white" alt="Discord"></a>
  <a href="https://api.sixfinger.live"><img src="https://img.shields.io/badge/API-Live-brightgreen" alt="API Live"></a>
  <a href="https://api.sixfinger.live/docs"><img src="https://img.shields.io/badge/Docs-OpenAI%20Compatible-blue" alt="Docs"></a>
  <a href="https://pypi.org/project/sixfinger/"><img src="https://img.shields.io/badge/PyPI-sixfinger-orange" alt="PyPI"></a>
</p>

Sixfinger is a production-ready AI gateway with 25+ models including Claude Opus 4.1, Haiku 4.5, DeepSeek, Qwen, Nemotron, GPT, GLM, Kimi, and more. Streaming, credit-based usage, and multilingual support — all behind a single OpenAI-compatible endpoint.

---

## Join Our Discord

**[https://discord.gg/AtwqzqpwR8](https://discord.gg/AtwqzqpwR8)**

- Test models with our **SixFinger API Test Bot**
- Request new models by opening issues
- Participate in giveaways
- Get support and share your projects

---

## OpenAI-Compatible API

Use the official OpenAI Python/Node.js SDK:

```python
from openai import OpenAI

client = OpenAI(
    base_url="https://api.sixfinger.live/v1",
    api_key="sixfinger_xxx"
)

response = client.chat.completions.create(
    model="gpt-5",
    messages=[{"role": "user", "content": "Hello!"}]
)
print(response.choices[0].message.content)
```

**Streaming:**

```python
from openai import OpenAI

client = OpenAI(base_url="https://api.sixfinger.live/v1", api_key="sixfinger_xxx")

for chunk in client.chat.completions.create(
    model="claude-haiku-4-5",
    messages=[{"role": "user", "content": "Tell me a story"}],
    stream=True
):
    content = chunk.choices[0].delta.content
    if content:
        print(content, end="", flush=True)
```

---

## Quick Start

```bash
curl -X POST https://api.sixfinger.live/v1/chat/completions \
  -H "X-API-Key: YOUR_KEY" \
  -H "Content-Type: application/json" \
  -d '{"model": "deepseek-v4-flash", "messages": [{"role": "user", "content": "Hello!"}]}'
```

```json
{
  "id": "chatcmpl-...",
  "object": "chat.completion",
  "model": "deepseek-v4-flash",
  "choices": [{
    "index": 0,
    "message": {"role": "assistant", "content": "Hello! How can I help you?"},
    "finish_reason": "stop"
  }],
  "usage": {"prompt_tokens": 10, "completion_tokens": 8, "total_tokens": 18}
}
```

**Python SDK:**

```bash
pip install sixfinger
```

```python
from sixfinger import API

client = API(api_key="YOUR_KEY")
response = client.chat("Hello!", model="deepseek-v4-flash")
print(response.content)
```

---

## Featured Models

All models available on every plan:

| Key | Model | Cost (input / output per 1M tokens) |
|-----|-------|--------------------------------------|
| `deepseek-v4-flash` | DeepSeek V4 Flash | 0 / 0 SF |
| `claude-haiku-4-5` | Claude Haiku 4.5 | 0 / 0 SF |
| `claude-opus-4.1` | Claude Opus 4.1 | 0 / 0 SF |
| `nemotron-3-ultra` | Nemotron 3 Ultra | 1 / 4 SF |
| `qwen3.7-max` | Qwen 3.7 Max | 2 / 8 SF |
| `gpt-5` | GPT-5 | 0 / 0 SF |
| `kimi-k2.7-code` | Kimi K2.7 Code | 0 / 0 SF |

---

## Plans

| Plan | Price | Monthly Credits | Streaming |
|------|------:|----------------:|:---------:|
| Free | $0 | 20 SF | ✓ |
| Starter | $5 | 100 SF | ✓ |
| Pro | $15 | 400 SF | ✓ |
| Plus | $39 | 1500 SF | ✓ |

Credits are consumed per request based on model pricing. Free models (0 SF per 1M tokens) cost nothing. Purchased credits never expire.

---

## Get Your API Key

1. Sign up at [api.sixfinger.live](https://api.sixfinger.live)
2. Verify your email
3. Grab your API key from the dashboard

---

## Documentation

Full API docs at [api.sixfinger.live/docs](https://api.sixfinger.live/docs)

**Endpoints:**

```
POST /v1/chat/completions    — OpenAI-compatible chat (stream or sync)
GET  /v1/models              — List available models
POST /api/v1/chat            — Legacy chat
GET  /api/v1/stats           — Usage stats
GET  /health                 — Health check
```

---

## Contact

**sixfingerdev@gmail.com** · Built by [@sixfingerdev](https://github.com/sixfingerdev)

---

 **If this saved you time, a star helps a lot!**
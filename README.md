# API Relay — Affordable AI API Proxy

OpenAI-compatible API proxy for DeepSeek and more. One endpoint, 5-20x cheaper than direct pricing.

## Quick Start

```python
from openai import OpenAI

client = OpenAI(
    api_key="sk-YOUR_KEY",
    base_url="https://airelay-pro.site/v1",
)

response = client.chat.completions.create(
    model="deepseek-chat",
    messages=[{"role": "user", "content": "Explain quantum computing"}],
)
print(response.choices[0].message.content)
```

```bash
curl https://airelay-pro.site/v1/chat/completions \
  -H "Authorization: Bearer sk-YOUR_KEY" \
  -H "Content-Type: application/json" \
  -d '{"model":"deepseek-chat","messages":[{"role":"user","content":"Hello"}]}'
```

## Available Models

| Model | Input / 1M | Output / 1M | Best For |
|---|---|---|---|
| deepseek-chat (V3) | $0.27 | $1.10 | General purpose, translation, summarization |
| deepseek-reasoner (R1) | $0.55 | $2.19 | Complex reasoning, code generation, math |

More models coming: Qwen, GLM, Moonshot.

## Features

- **Drop-in OpenAI SDK replacement** — just change `base_url`
- **Streaming support** — real-time SSE responses
- **No logging** — prompts and responses are never stored
- **$1 free credits** — test before you pay
- **PayPal top-up** — no subscription, prepaid balance

## Pricing Comparison

| Our Model | Our Price (Input/Output) | OpenAI Equivalent | OpenAI Price | Savings |
|---|---|---|---|---|
| deepseek-chat | $0.27 / $1.10 | GPT-4o | $2.50 / $10.00 | ~89% |
| deepseek-reasoner | $0.55 / $2.19 | o1 | $15.00 / $60.00 | ~96% |

## Tech Stack

- **Backend**: Python FastAPI (async, SSE streaming)
- **Database**: SQLite (migrating to Postgres)
- **Infra**: Docker Compose on $5/mo VPS
- **SSL**: Let's Encrypt auto-renewal

## Self-Host

Want to run your own relay? See [self-hosting guide](https://github.com/airelay/api-relay).

## Contact

- Website: https://airelay-pro.site
- Email: 1543115759@qq.com

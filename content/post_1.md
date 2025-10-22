---
layout: post
title: "Genera una clave API de Gemini"
date: 2025-10-23
---

En este tutorial vamos a generar una clave de acceso a la [API](glosario#-api-application-programming-interface) de Gemini. Una clave API es una **credencial que nos permite acceder a los productos o servicios de software que una empresa provee**. En algunos casos es gratuito y otras veces tiene algún costo. Para este ejemplo, solo aplicaremos a una clave API **gratuita**. Por último, recuerda anotar siempre tu clave API en algún lugar seguro ya que **solo se muestra una sola vez**.

# Requisitos

```Python Python theme={null}
import anthropic

client = anthropic.Anthropic(
    # defaults to os.environ.get("ANTHROPIC_API_KEY")
    api_key="my_api_key",
)
message = client.messages.create(
    model="claude-sonnet-4-5",
    max_tokens=1024,
    messages=[
        {"role": "user", "content": "Hello, Claude"}
    ]
)
print(message.content)
```

<Note>
  This compatibility layer is primarily intended to test and compare model capabilities, and is not considered a long-term or production-ready solution for most use cases. While we do intend to keep it fully functional and not make breaking changes, our priority is the reliability and effectiveness of the [Claude API](/en/api/overview).

  For more information on known compatibility limitations, see [Important OpenAI compatibility limitations](#important-openai-compatibility-limitations).

  If you encounter any issues with the OpenAI SDK compatibility feature, please let us know [here](https://forms.gle/oQV4McQNiuuNbz9n8).
</Note>

| Field                   | Support status                                                      |
| ----------------------- | ------------------------------------------------------------------- |
| `model`                 | Use Claude model names                                              |
| `max_tokens`            | Fully supported                                                     |
| `max_completion_tokens` | Fully supported                                                     |
| `stream`                | Fully supported                                                     |
| `stream_options`        | Fully supported                                                     |
| `top_p`                 | Fully supported                                                     |
| `parallel_tool_calls`   | Fully supported                                                     |
| `stop`                  | All non-whitespace stop sequences work                              |
| `temperature`           | Between 0 and 1 (inclusive). Values greater than 1 are capped at 1. |
| `n`                     | Must be exactly 1                                                   |
| `logprobs`              | Ignored                                                             |
| `metadata`              | Ignored                                                             |
| `response_format`       | Ignored                                                             |
| `prediction`            | Ignored                                                             |
| `presence_penalty`      | Ignored                                                             |
| `frequency_penalty`     | Ignored                                                             |
| `seed`                  | Ignored                                                             |
| `service_tier`          | Ignored                                                             |
| `audio`                 | Ignored                                                             |
| `logit_bias`            | Ignored                                                             |
| `store`                 | Ignored                                                             |
| `user`                  | Ignored                                                             |
| `modalities`            | Ignored                                                             |
| `top_logprobs`          | Ignored                                                             |
| `reasoning_effort`      | Ignored                                                             |


<details>
  <summary>Show fields</summary>

  #### Tools

  `tools[n].function` fields

  | Field         | Support status  |
  | -------------- | --------------- |
  | `name`         | Fully supported |
  | `description`  | Fully supported |
  | `parameters`   | Fully supported |
  | `strict`       | Ignored         |
</details>

# AI Models Skills

Unified model routing, Chinese LLM access, provider setup, and OpenAI-compatible model gateway workflows powered by AIsa.

This repository is part of the [AISA Skills](https://github.com/AISA-skills) collection. Each top-level directory is a self-contained agent skill with a `SKILL.md` file and optional supporting scripts, references, or assets.

## Skills

| Skill | Description |
|---|---|
| [aisa-provider](./aisa-provider/) | Configure AIsa as a first-class model provider for OpenClaw, enabling production access to major Chinese AI models (Qwen, DeepSeek, Kimi K2.5, Doubao) through official partnerships with Alibaba Cloud, BytePlus, and Moonshot. Use this skill when the user wants... |
| [cn-llm](./cn-llm/) | China LLM Gateway - Unified interface for Chinese LLMs including Qwen, DeepSeek, GLM, Baichuan. OpenAI compatible, one API Key for all models. Use when: the user needs model routing, provider setup, or Chinese LLM access guidance. |
| [llm-router](./llm-router/) | Unified LLM Gateway - One API for 70+ AI models. Route to GPT, Claude, Gemini, Qwen, Deepseek, Grok and more with a single API key. Use when: the user needs model routing, provider setup, or Chinese LLM access guidance. |

## Requirements

Most skills in this repository use AIsa APIs and expect one environment variable:

```bash
export AISA_API_KEY="your-aisa-api-key"
```

Get an API key at [aisa.one](https://aisa.one). Keep your key out of commits, screenshots, shared logs, and shell history exports.

## Install

Clone this repository:

```bash
git clone https://github.com/AISA-skills/ai-models.git
cd ai-models
```

Install one or more skills into your local agent runtime. For Codex:

```bash
mkdir -p ~/.codex/skills
cp -r aisa-provider ~/.codex/skills/
cp -r cn-llm ~/.codex/skills/
cp -r llm-router ~/.codex/skills/
```

For other Agent Skills compatible runtimes, copy the skill folder into that runtime's skills directory, then restart the agent so it can load the skill metadata.

## Usage

Ask your agent to use the relevant skill by name. Example:

```text
Use aisa-provider to help me with this task.
```

Each skill contains its own workflow, safety rules, required inputs, and API notes in `SKILL.md`.

## Repository Layout

```text
ai-models/
|-- README.md
|-- LICENSE
|-- .gitignore
`-- <skill-name>/
    |-- SKILL.md
    |-- scripts/       # optional
    |-- references/    # optional
    `-- assets/        # optional
```

## Contributing

1. Keep each skill self-contained in its own folder.
2. Keep `SKILL.md` focused on agent-facing instructions.
3. Put large endpoint docs, schemas, templates, or examples in `references/`.
4. Put deterministic helper code in `scripts/`.
5. Do not commit local outputs, credentials, caches, or API responses.

## License

MIT. See [LICENSE](./LICENSE).

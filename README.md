# OpenClaw Skill: Article Summarizer

📄 Summarize articles, web pages, PDFs, and Feishu docs from a shared link.

## Features

- Send a URL → auto-fetch content → 3 bullet-point summary
- Supports: web pages, PDFs, Feishu docs
- Option to save summary to notes and/or push to WeChat

## Install

```bash
# Clone to your OpenClaw plugin-skills directory
git clone https://github.com/lidongyangLeo/openclaw-skill-article-summarizer.git \
  ~/.openclaw/plugin-skills/article-summarizer

# Or via npm
npm install -g openclaw-skill-article-summarizer

# Restart OpenClaw gateway
openclaw gateway restart
```

## Usage

Just send a link:
```
https://example.com/article
```

The skill auto-detects and summarizes.

## License

MIT

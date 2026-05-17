# OpenClaw Skill: Article Summarizer

📄 把网页 / PDF / 飞书文档压成几条要点。

## 特性

- 发链接 + "帮我总结" → 自动抓取 → 按长度给 2/3/5 条要点
- 支持：网页、PDF、飞书文档、本地文件
- 总结后**询问**是否存笔记 / 推微信，默认不动

## 触发条件

发链接的同时要表达总结意图（"总结" / "讲了啥" / "三句话说说" 等）。
**只发链接不会触发**——避免误打扰。

## 安装

```bash
# 方式 1：克隆到 OpenClaw plugin-skills 目录
git clone https://github.com/lidongyangLeo/openclaw-skill-article-summarizer.git \
  ~/.openclaw/plugin-skills/article-summarizer

# 方式 2：npm 全局安装
npm install -g openclaw-skill-article-summarizer

# 重启 OpenClaw gateway
openclaw gateway restart
```

## 用法

```
帮我总结 https://example.com/article
这篇飞书文档讲了什么 <feishu-link>
三句话概括 <pdf-link>
```

## 长度策略

| 正文字数 | 输出 |
|---|---|
| < 800 | 2 条要点 |
| 800–3000 | 3 条要点 |
| > 3000 | 5 条要点 + 100 字概要 |

## License

MIT

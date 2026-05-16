---
name: article-summarizer
description: Summarize articles, web pages, PDFs, and Feishu docs. Send user a link → auto-fetch, summarize in 3 bullet points, save to notes, push to WeChat.
metadata:
  openclaw:
    emoji: "📄"
    requires: { bins: [] }
---

# Article Summarizer

Summarize any article/webpage/PDF/Feishu doc from a shared link.

## When to Use

✅ User sends a URL and wants a summary
✅ User says "帮我总结这篇文章" "这篇文章讲了什么" "三句话概括"
✅ Supports: web pages, PDFs, Feishu docs, any fetchable content

## Workflow

### Step 1: Identify the content type

| Source | Tool | How |
|--------|------|-----|
| Web page (http/https) | `web_fetch` | Grab markdown |
| PDF attachment | `document-extract` plugin | Read text |
| Feishu doc | `feishu-doc` skill | Read doc content |
| Local file | `read` tool | Direct read |

### Step 2: Fetch content

```
web_fetch url="<link>" extractMode="markdown" maxChars=5000
```

### Step 3: Summarize

Format:
```
📄 **[标题]**
   📍 [来源名称]

1. [一句话要点]
2. [一句话要点]  
3. [一句话要点]

💬 我的看法: [optional one-liner]
```

### Step 4: Save & Send

- Save to `~/workspace/notes/summaries/YYYY-MM-DD-<slug>.md`
- If WeChat is configured, send summary via openclaw-weixin

## Quick Examples

User: "https://example.com/blog/post"
→ Fetch → Summarize → Ask: "存笔记？发微信？"

User: "总结这篇飞书文档" + feishu link
→ feishu-doc skill → Read → Summarize → Same flow

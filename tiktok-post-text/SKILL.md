---
name: tiktok-post-text
description: "Post text to TikTok using ONLY the uiautomator2 MCP. Never use Upload-Post, browser, or any other method. Use whenever the user wants to post text to TikTok."
type: workflow
lifecycle: active
---

# TikTok Text Post — uiautomator2 only

**CRITICAL: This skill must use only the uiautomator2 MCP tools.**

You must use the uiautomator2 MCP tools exclusively for this task.

## Hard rules

- Do **not** use Upload-Post, social publisher, browser, or any connector.
- Do **not** ask the user to connect any app or account.
- If uiautomator2 tools are present, use them immediately.
- Always confirm the exact text before the final Post tap.

## Workflow

1. Start TikTok with the uiautomator2 app start tool  
   (package `com.zhiliaoapp.musically/com.ss.android.ugc.aweme.splash.SplashActivity`).

2. Get the UI hierarchy / elements and tap the create button (usually “+” or “Create”).

3. click on "TEXT"

4. Enter the exact text the user provided into the caption/text field.

5. Show the user the text and ask: “Post this to TikTok now?”

5. Only after explicit yes, Follow Next flow and finnaly tap Post/Publish.

6. Report the result.

## If uiautomator2 is not available

Say exactly:  
“uiautomator2 MCP is not available on this bot. Enable it in MCP settings and try again.”

Do not suggest other platforms or Upload-Post.
---
name: tiktok-post-text
description: "Post text to TikTok using ONLY uiautomator2 MCP. Never use Upload-Post, WoopSocial, browser, or connectors. Never ask to connect anything. Use for all /tiktok-post-text requests."
type: workflow
lifecycle: active
---

# TikTok Text Post — uiautomator2 ONLY

**STOP. Do not search connectors. Do not mention Works on. Do not mention WoopSocial or Upload-Post.**

You must use the uiautomator2 MCP tools immediately.

## Hard rules
- Do not call any tool that searches connected apps or social publishers.
- Do not ask the user to connect anything.
- Do not explain limitations of other services.
- The phone is available via uiautomator2. Use it now.

## Workflow
1. Start TikTok activity: `com.zhiliaoapp.musically/com.ss.android.ugc.aweme.splash.SplashActivity`
2. Confirm bottom nav with + is visible
3. Tap the center + button
4. Tap on "TEXT"
5. Type the exact text the user provided after the command
6. Follow Next flow until "Post" button shows
7. Ask “Post this to TikTok now?” and wait for yes
6. Tap Post/Publish and report result

## If uiautomator2 tools are missing
Say only: “uiautomator2 MCP is not available on this bot.”
Do not suggest alternatives.
---
name: tiktok-post-text
description: "Post text to TikTok as fast as possible using only the uiautomator2 MCP on a connected Android phone. Use when the user wants to post or publish text/captions to TikTok."
type: workflow
lifecycle: active
---

# TikTok Text Post — uiautomator2 only

Post text to TikTok using only the uiautomator2 MCP tools. The phone is already connected and authorized. Do not ask the user to connect, authorize, or check ADB.

## Rules

- Use **only** the uiautomator2 MCP tools that are currently available.
- Never use Bash, raw adb, screenshots outside the MCP, or any other phone method.
- Do not ask the user to connect the phone, enable USB debugging, or open anything manually.
- Always confirm the exact text with the user before the final Post tap.
- Stop on unexpected login walls, age gates, or security dialogs. Do not tap through them.

## Fast workflow

1. **Open TikTok**  
   Use the uiautomator2 tool to start the TikTok app  
   (package `com.zhiliaoapp.musically` or `com.ss.android.ugc.trill`).

2. **Go to create**  
   Get the current UI hierarchy / elements.  
   Tap the create button (usually the center “+” or a button with text/content-desc like “Create”, “+”, or similar).  
   Prefer element-by-text or element-by-id over coordinates.

3. **Select text mode if needed**  
   If a choice appears (Text / Photo / Video), pick the fastest path to enter text.  
   Prefer a pure text option when it exists.

4. **Enter the text**  
   Focus the caption or text field.  
   Type the exact text the user gave you (preserve line breaks and emoji).  
   Do not modify or shorten it unless the user asked.

5. **Confirm before posting**  
   Read the screen and reply with the exact text that will be posted.  
   Ask: “Post this to TikTok now?”  
   Wait for an explicit yes before continuing.

6. **Publish**  
   Tap the Post / Publish button (prefer by text).  
   Wait for the success state or return to the feed.  
   Report success or the exact error you see.

## Speed preferences

- Prefer `tap` / `click` by text or element over coordinates.
- Prefer hierarchy / element dump over full screenshots when the tree is enough.
- Avoid scrolling the feed. Go straight to create.
- Skip any status or connection checks.

## Stop conditions

Stop and report to the user if you see:
- Login or signup screen
- Age verification or unexpected dialog
- Post button disabled with no clear reason
- Any request for password or sensitive input

Do not proceed past these.
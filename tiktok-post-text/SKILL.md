---
name: tiktok-post-text
description: "Post text (or short captions) to TikTok on a connected Android phone as fast as possible using phone/ADB/uiautomator tools. Use when the user wants to post, publish, or upload text content to TikTok quickly."
type: workflow
lifecycle: active
---

# TikTok Text Post — Fast

Post text content to TikTok on a USB-connected Android phone with minimal steps and maximum speed.

## Prerequisites

- Phone is connected and authorized (`adb devices` shows it).
- TikTok is already installed and the user is logged in.
- Phone tools (uiautomator2 MCP, phone MCP, or equivalent) are available and working.

## Safety (mandatory)

1. **Never post without explicit confirmation** of the exact text.
2. Show the final text and ask “Post this to TikTok now?” before the final publish tap.
3. Stop immediately if any login wall, age gate, or unexpected dialog appears.
4. Do not enter passwords, payment info, or accept unexpected legal prompts.

## Fast workflow

1. **Status check**  
   Call phone status / list devices. Abort with a clear message if the device is missing or unauthorized.

2. **Open TikTok**  
   Launch the TikTok app (package usually `com.zhiliaoapp.musically` or `com.ss.android.ugc.trill`).

3. **Go to create**  
   - Prefer tapping the center “+” / create button by text or resource-id.  
   - If not visible, use a short swipe or press the known create button coordinates only as fallback.

4. **Choose text / photo mode**  
   - Look for “Text”, “Photo”, or “Upload” options.  
   - Prefer text mode if available; otherwise create a simple photo/text overlay.

5. **Enter the text**  
   - Focus the caption / text field.  
   - Type the exact text the user provided (preserve emojis and line breaks).  
   - Keep it under TikTok’s limit (typically ~2200 characters; warn if longer).

6. **Confirm with user**  
   Read the screen and reply with the exact text that will be posted.  
   Ask for explicit “yes / post it” before continuing.

7. **Publish**  
   - Tap the “Post” / “Publish” button (prefer `tap_text("Post")`).  
   - Wait for the success indicator or return to the feed.  
   - Report success or the exact error.

## Speed tips

- Prefer `tap_text` over coordinates whenever possible.
- Cache the create button location after the first successful post in the session.
- Skip unnecessary screenshots if the accessibility tree already gives clear targets.
- Avoid scrolling the feed; go straight to create.

## Common issues

| Problem | Fix |
|---------|-----|
| TikTok not logged in | Stop and tell the user to log in manually |
| Create button not found | Ask user to open TikTok create screen once, then retry |
| Text field not focused | Tap the caption area by text or bounds, then type |
| Post button grayed out | Check if text is empty or network is offline; report it |
| Unexpected dialog | Stop and describe the dialog; do not tap through blindly |

## Tool preference order

1. `tap_text` / element by text or content-desc  
2. Resource-id based tap  
3. Coordinate tap (only after reading screen)  
4. Raw ADB input as last resort

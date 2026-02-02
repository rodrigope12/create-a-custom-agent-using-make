# Facebook Smart Processing Loop - Setup Guide

This package contains the automated workflow for processing Facebook Page comments. Follow the instructions below to import and configure the system in Make.com.

## Files Included
- `facebook_ai_reply_blueprint.json` (The Scenario Blueprint)
- `SETUP_GUIDE.md` (This document)

---

## 1. Import the Blueprint
1. Log in to your Make.com account.
2. Create a new Scenario.
3. Select **More** (three dots) > **Import Blueprint**.
4. Upload the provided `facebook_ai_reply_blueprint.json`.

## 2. Configuration

### Module 1: Facebook Page Trigger
- Click on the first module ("Watch Comments").
- Connect your Facebook account (Business Manager).
- Select the target Facebook Page.
- **Note**: This uses a real-time webhook. No additional URL configuration is usually required if you authorize the connection properly.

### Module 2: AI Processor
- Click the middle module ("Generate Response").
- Add your OpenAI API Key.
- (Optional) Edit the "System Message" to customize the tone of voice or add specific brand rules.

### Module 3: Facebook Reply
- Click the last module ("Post Threaded Reply").
- Ensure the connection matches the one used in Module 1.
- Confirm that `Comment ID` is mapped correctly (already pre-set in the blueprint).

## 3. Deployment Safety (CRITICAL)
To prevent the system from replying to its own comments (infinite loops):

1. **Get your Facebook Page ID** (found in Page Settings > About or URL).
2. Click the **Filter Icon** (wrench) between Module 1 and Module 2.
3. Locate the condition: `1.Sender ID` `Not equal to`.
4. Replace the placeholder content with your actual **Numeric Page ID**.
5. Save the scenario.

## 4. Activation
- Click **Save** (floppy disk icon).
- Turn the scenario **ON**.

The system is now live and will process incoming comments immediately.

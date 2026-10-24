# Closed Testing Guide Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Add a clear Google Play closed-testing installation guide to the existing GekGoods SIM Manager site.

**Architecture:** Keep the static site structure. Expand the existing Compatibility page with the tester flow and supplied guide image, then point the home and support pages at that guide.

**Tech Stack:** Static HTML, shared CSS, GitHub Pages, one supplied JPEG asset.

**Spec:** `docs/superpowers/specs/2026-10-25-closed-testing-guide-design.md`

## Global Constraints

- Preserve the existing GekGoods visual system and navigation.
- Keep the Play Store package link `https://play.google.com/store/apps/details?id=com.gekgoods.simmanager`.
- State that testers must use the same Google account and may need to wait 15–30 minutes before the listing appears.
- Do not add dependencies, forms, backend behavior, or Play Console configuration.

## Review Focus

- A visitor who has not joined the test must see that Google Group membership comes first; verify the numbered steps state that order.
- A visitor using a different Google account must be warned; verify the guide includes the same-account requirement.
- A newly enrolled tester may see “not found” temporarily; verify the 15–30 minute retry guidance is present.
- A mobile visitor must be able to read the guide image; verify the image is responsive and has useful alternative text.
- Existing visitors must still reach compatibility and support; verify the shared navigation and all changed links remain valid.

### Task 1: Add the closed-testing guide and update entry points

**Files:**
- Create: `assets/closed-testing-guide.jpg`
- Modify: `compatibility.html`
- Modify: `index.html`
- Modify: `support.html`
- Modify: `styles.css`

**Interfaces:**
- Consumes: the existing static page layout, shared `.content`, `.notice`, `.button`, and `.section` styles.
- Produces: a visible `#closed-testing` section on `compatibility.html` and links from the home/support pages.

- [ ] **Step 1: Add the supplied guide image**

Copy the user-provided `1-Photo-1.jpg` to `assets/closed-testing-guide.jpg` without changing its pixels.

- [ ] **Step 2: Update the Compatibility page**

Add a closed-testing section before the existing compatibility checklist. Include the Google Group → Join Group → Become a tester → wait 15–30 minutes → install from Google Play order, the same-Google-account warning, the exact Play Store link, and a responsive figure containing `assets/closed-testing-guide.jpg`. Keep the existing compatibility cards below it.

- [ ] **Step 3: Update the homepage and support copy**

Point the homepage’s primary getting-started action and relevant microcopy at the closed-testing guide, and replace support’s stale “listing is being prepared” paragraph with a link to the live closed-testing instructions.

- [ ] **Step 4: Add only the required image presentation styles**

Add a bordered, rounded, centered guide-image treatment that caps the image width and preserves mobile readability without changing unrelated layout rules.

- [ ] **Step 5: Verify the static site**

Run targeted text/link checks for the package URL, `#closed-testing`, image path, same-account warning, and 15–30 minute guidance. Confirm `git diff --check`, inspect the changed diff, and verify no unrelated Android files are included.

- [ ] **Step 6: Commit the site change**

Use the existing site history identity `Jun Xu <63337934+gekjunxu@users.noreply.github.com>` and commit with a focused message such as `Add Play closed testing guide`.

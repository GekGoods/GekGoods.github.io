# Closed Testing Guide Design

## Intent

Help prospective GekGoods SIM Manager testers join the Google Group, opt into
the Google Play closed test, and install the app.

## Goals

- Make the closed-testing flow easy to find from the existing getting-started page.
- Explain the seven steps in plain language, including the 15–30 minute Play Store delay.
- Include the supplied visual guide for people who prefer screenshots and QR codes.
- Keep the official Play Store package link and the site’s existing visual system.

## Non-goals

- No signup form, tester database, or account handling.
- No change to the Android package, Play Console configuration, or release process.
- No new standalone site section unless the existing Compatibility page cannot carry the guide clearly.

## Constraints and risks

- The site is static HTML and CSS; reuse its current page and component patterns.
- Closed-test access depends on the tester’s Google account and external Play/Group availability.
- The QR codes and invitation flow remain external to the site and may change independently.

## Approaches

1. Expand `compatibility.html` with the closed-testing guide, supplied image, and updated calls to action. This is the recommended smallest change because the page is already the site’s “Get started” destination.
2. Create a dedicated `testing.html` page and add a new navigation item. This separates tester onboarding but adds another page and repeated navigation.
3. Put the full guide on `index.html`. This is highly visible but makes the landing page longer and mixes marketing with onboarding.

The implementation uses approach 1.

## Implementation

Add a closed-testing section before the existing compatibility checklist. It will
provide numbered text steps, a direct Google Play link, the supplied guide image,
and an accessible note that testers must use the same Google account. Update the
home page and support page to point to the guide and remove the stale “listing is
being prepared” wording. Add only the CSS needed to present the image responsively.

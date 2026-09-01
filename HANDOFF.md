# Next Chat Handoff

**Date:** 2026-09-01

## Read first

Before continuing this project, read:

1. `README.md`
2. `PROJECT_STATE.md`
3. `docs/03-real-estate-miniature-service.md`
4. `docs/05-market-and-competition.md`
5. `docs/07-validation-plan.md`

If something seems missing, check:

`archive/chats/2026-09-01-initial-concept-session.md`

## Where the project stands

The project has moved from a general "AI miniature videos might get views" idea to a more focused thesis:

> **Test AI-native real-estate listing media, with realistic miniature/unboxing treatments as the first signature format.**

The strongest business model currently appears to be direct B2B service revenue from realtors/teams/builders rather than relying on YouTube ads.

A second concept remains viable: miniature product unboxings/demos tied to affiliate offers.

## What has already been decided

- Do not build a full automation system yet.
- Do not assume "miniature" itself is a moat.
- Do not rely on generic faceless AI-video volume.
- Preserve real property/product identity; avoid hallucinating material facts.
- Start with a small technical + market validation budget (~$100-$200).
- Human hands/physical manipulation are an important creative device because they establish scale.
- The personalized watermarked-preview outreach model is worth testing with realtors.

## Best next task

The next chat should focus on **production feasibility and test design**.

Recommended sequence:

### 1. Identify current best tools/models

Research the strongest current options for:

- image-to-image miniature transformation
- product/property fidelity
- image-to-video
- hand/object interaction
- multi-shot consistency
- cost per generation
- API availability
- commercial-use terms

Build a comparison table.

### 2. Design six prototypes

Three real-estate and three product tests.

For each, specify:

- source asset requirements
- exact visual concept
- shot list
- model/tool
- prompt structure
- expected generation count
- target cost
- fidelity checklist

### 3. Prioritize one hero real-estate format

Current favorite candidate:

**Miniature Listing Unboxing**

Concept:

A package arrives -> hand opens it -> realistic miniature of the actual listing is removed -> roof/interior reveal -> transition into real listing footage -> property/agent CTA.

Compare this against simpler formats such as house-in-hand and real-to-mini transition, because the simpler format may be cheaper and more reliable.

### 4. Define pass/fail criteria before generating

Track:

- realism
- property fidelity
- consistency
- hand quality
- cost
- retries
- editing minutes
- visual hook strength

Do not call a test successful merely because a model produced a video.

## Important research follow-up

The first market scan found evidence that miniature product and real-estate effects already exist, but no clearly dominant operator was identified around the exact personalized realtor-service model.

A future research pass should build a real swipe file from TikTok, Instagram, YouTube Shorts, creative studios, Fiverr/Upwork, and real-estate agencies.

Capture actual view counts, repeated formats, service offers, and pricing where visible.

## Repository maintenance instruction

At the end of the next substantial chat:

1. update `PROJECT_STATE.md`
2. update relevant `docs/` files
3. rewrite this `HANDOFF.md`
4. create a dated summary in `archive/chats/`

Do not rely on chat history alone.

# Production Feasibility Research Session

**Date:** 2026-09-02
**Project:** AI Miniature Video Biz Concepts

## Session objective

Determine whether current September 2026 image/video systems can turn permissioned real-estate listing assets into premium miniature/scale-model videos while preserving the recognizable identity and material architectural facts of the property.

This was a technical feasibility study, not a website, automation, mass-market offer, or demand-validation exercise.

## Repository-first procedure

Before researching, the session read:

- `README.md`
- `PROJECT_STATE.md`
- `HANDOFF.md`
- `docs/03-real-estate-miniature-service.md`
- `docs/05-market-and-competition.md`
- `docs/07-validation-plan.md`
- `docs/08-ideas-backlog.md`
- `docs/09-chat-handoff-protocol.md`

A repo search did not uncover prior detailed production-stack research that would make this assignment redundant.

## Core conclusion

**Current tools are good enough to justify controlled production tests, but not good enough to treat a listing as a loose prompt and trust a single video model to preserve the property.**

The strongest production principle is:

> Treat the actual property as a locked product asset. Establish and approve its miniature representation first, then ask the video model mainly to create motion rather than redesign the building.

Recommended architecture:

`permissioned listing assets -> property reference/geometry packet -> approved miniature still or geometry-locked maquette -> constrained animation/editing -> real performance plate for difficult hand/occlusion shots when useful -> conventional compositing/editing -> factual property QC`

## Important change from prior belief

### Prior belief

The earlier validation plan treated roughly **$100-$200 total** as a useful technical-proof budget and emphasized keeping generation costs low.

### New evidence

Premium output may require multiple still models, multiple video-model A/B tests, first/last-frame generations, video-to-video passes, geometry anchors, hand-performance plates, and conventional post-production. Individual generations are often inexpensive, but retries and specialist passes accumulate.

### Revised conclusion — 2026-09-02

Do **not** use the old $100-$200 figure as a hard ceiling while establishing the quality ceiling. Allow approximately **$150-$300 total generation spend across the first three controlled real-estate prototypes if needed**, while separately tracking actual spend per approved clip. Cost optimization comes after the best workflow is known.

## Current tool findings that matter most

### Image / property-lock stage

- **Gemini 3 Pro Image** is the leading premium still candidate because of multi-reference support and low enough per-image cost to permit aggressive iteration and QC.
- **Gemini 3.1 Flash Image** is the leading cost-efficient still candidate and may be especially useful where many property references are needed.
- **FLUX.2 Max/Pro**, **Seedream 5 Pro**, and **GPT Image 2** are valuable A/B or correction models rather than necessarily replacing the primary workflow.
- A beautiful still is not automatically a valid listing still; windows, roof geometry, pool, hardscape, materials, balconies, garage doors, and other material facts must be checked explicitly.

### Video / motion stage

- **Gemini Omni Flash 1.1** emerged as a top general control/iteration candidate because it supports image/video references, reference-to-video, iterative editing, first/last-frame workflows, extensions, and low 720p pricing.
- **Wan 3.0**, released through Runway Dev on 2026-08-26, is a new high-priority A/B candidate because of strong reference/editing features, first/last keyframes, long duration, 1080p support, and competitive pricing. Its extreme recency means real-estate reliability remains unproven.
- **Seedance 2.5** is the premium reference-heavy specialist for difficult shots involving many references, clay/white 3D models, real performance plates, or complex editing.
- **Veo 3.1** remains a strong premium-finish option but has a smaller reference allowance, which is a meaningful limitation for complex architecture.
- **MiniMax H3 / Hailuo 3** is a strong cost-quality animation candidate when the miniature still is already locked.
- **Sora is not a recommended forward-looking foundation** because OpenAI’s current materials indicate the Sora API is scheduled to shut down on 2026-09-24.

## Geometry-anchor insight

When a listing has a Matterport/digital twin or equivalent 3D capture, the premium workflow should consider a geometry-anchor branch. Matterport can expose meshes, textures, images, and floorplan/OBJ-type deliverables depending on product/access level. Even a simple clay/white maquette render can give an image/video model a stronger geometric constraint than asking it to infer unseen sides of the house.

This is especially relevant for:

- unusual roof forms
- complex pools/hardscape
- multi-wing luxury homes
- courtyards
- dramatic rear elevations
- shots that rotate the miniature far from the original listing-camera viewpoint

## Three prototype conclusions

### Test 1 — House in Hand

High hook value and viable as a second test. Best chance of success comes from locking the miniature first and limiting hand motion. A real hand plate plus compositing/editing may outperform unconstrained full generation when fingers occlude important architecture.

### Test 2 — Real -> Miniature -> Real

**Recommended first experiment.** Best current balance of impact, property fidelity, repeatability, and production complexity. The authentic listing imagery anchors the property; the miniature section can be short; first/last-frame or controlled transition workflows reduce hallucination exposure.

### Test 3 — Premium Miniature Listing Unboxing

Highest theatrical upside but highest technical risk. Pure full-scene generation is not the recommended first method. The stronger hypothesis is a real box/hand performance plate plus a property miniature replacement/edit/composite workflow, with object removal/rotation kept simple until proven.

## Property-fidelity standard preserved

The project should stylize:

- scale
- environment
- miniature materials/presentation
- camera treatment
- atmospheric/cinematic treatment

It should **not intentionally fabricate material property facts**.

High-risk features requiring explicit QC include:

- window count, spacing, and proportions
- roof shape, pitches, ridges, dormers, chimneys
- doors and garage bays
- exterior cladding/material/color relationships
- balconies, rails, decks, terraces
- driveway/walkway geometry
- pool/spa location and outline
- mature landscaping and major retaining/hardscape elements
- significant views/context when shown
- important interior layout/finishes when interior miniature shots are attempted

## Cinematic terminology research intentionally deferred

The user separately identified professional cinematic terminology—lighting, atmosphere, lensing, camera angles and camera motion—as important to realism. This session did **not** expand into a full cinematography/prompt-language study because doing so would dilute the production-feasibility objective. That topic deserves its own focused research chat after the first production workflow is locked.

## Recommended next action

Do **one permissioned Real -> Miniature -> Real prototype first** using a visually distinctive listing with strong front/rear/drone coverage.

Suggested first A/B workflow:

1. Build a 6-12 image property reference packet.
2. Create 6-12 miniature still candidates, primarily in Gemini 3 Pro Image, with Gemini 3.1 Flash Image / FLUX.2 / Seedream as correction or comparison models.
3. Select one still only after a formal property-fidelity review.
4. Animate the approved miniature with short, controlled motion using Gemini Omni Flash 1.1 and Wan 3.0 as the first A/B pair.
5. Test a first/last-frame or matched-cut transition from authentic listing footage into the miniature and back.
6. Finish conventionally in an editor: timing, sound design, color, upscale if needed, cleanup, branding only after the image itself passes.
7. Score property fidelity, realism, miniature illusion, motion quality, retries, spend, and edit time.

If this passes, move to **House in Hand**. Test **Premium Miniature Listing Unboxing** third.

## Durable files created/updated by this session

- `research/2026-09-production-stack-feasibility.md` — detailed research, model comparisons, pricing/licensing/API notes, prototype designs, economics, risks, sources.
- `PROJECT_STATE.md` — concise strategy-changing conclusions and next actions.
- `HANDOFF.md` — rewritten continuation instructions for the next chat.
- `archive/chats/2026-09-02-production-feasibility-research.md` — this historical record.

## What remains uncertain

- Our own measured property-fidelity pass rate by model.
- Actual retries per approved 4-10 second property clip.
- Whether Omni Flash 1.1 or Wan 3.0 performs better on this exact real-estate reference workload.
- Whether a geometry anchor materially improves results enough to justify the extra production step for normal listings.
- Whether hand interaction is acceptable through pure generation or should default to compositing/performance plates.
- The production economics after human correction/editing time is included.
- Realtor willingness to pay for the resulting quality; technical feasibility does not establish demand.

## Decision discipline

No business-model conclusion was promoted from hypothesis to fact. The premium/exclusive positioning remains a hypothesis to revisit only after technical quality has been demonstrated on real listing assets.

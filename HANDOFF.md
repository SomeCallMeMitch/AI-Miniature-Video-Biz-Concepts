# Next Chat Handoff

**Date:** 2026-09-02

## Read first

Before continuing this project, read:

1. `README.md`
2. `PROJECT_STATE.md`
3. `research/2026-09-production-stack-feasibility.md`
4. `docs/03-real-estate-miniature-service.md`
5. `docs/07-validation-plan.md`
6. `docs/08-ideas-backlog.md`
7. `docs/09-chat-handoff-protocol.md`

For historical reasoning from the production-feasibility session, read:

- `archive/chats/2026-09-02-production-feasibility-research.md`

## What was completed

A current September 2026 production-feasibility study was completed for creating premium miniature real-estate video from actual listing assets.

It researched and compared current image/video systems, including:

- Gemini 3 Pro Image / Gemini 3.1 Flash Image
- FLUX.2
- Seedream 5.0 Pro
- GPT Image 2
- Gemini Omni Flash 1.1
- Wan 3.0
- Seedance 2.5
- Veo 3.1
- MiniMax H3 / Hailuo 3
- Runway Gen-4.5
- Runway Aleph 2
- Luma Ray3.14 / Modify
- Sora status
- Matterport/digital-twin geometry as a possible fidelity anchor

The detailed sources, pricing snapshots, API/licensing notes, comparison matrix, workflows, and experiment designs are in:

`research/2026-09-production-stack-feasibility.md`

## Main conclusion

**Conditional technical green light.**

Current systems appear capable of producing client-worthy miniature listing creative **if the property is locked and approved before motion and the video stage is tightly constrained**.

They are not reliable exact architectural reconstruction systems.

The production rule is:

> **Lock facts first. Animate second. Stylize scale and presentation, not the property itself.**

Do not let one video model freely generate a house from listing photos and assume the result is factually safe.

## Current preferred production architecture

**permissioned listing assets -> Property Identity Pack / geometry -> approved miniature master -> constrained animation/editing -> real hand/performance plate where needed -> conventional finishing -> property-fidelity QC**

### Premium still candidates

1. Gemini 3 Pro Image
2. FLUX.2 Max as A/B/correction
3. Seedream 5.0 Pro when a sketch/clay/geometry reference helps
4. GPT Image 2 as correction fallback

### Cost-efficient still candidate

- Gemini 3.1 Flash Image

### Default video A/B

1. **Gemini Omni Flash 1.1** — GA as of 2026-08-27; strong reference/edit/iteration workflow
2. **Wan 3.0** — added 2026-08-26; strong new reference/edit candidate with first/last keyframes and low cost

### Other important video roles

- **MiniMax H3 / Hailuo 3** — very strong low-cost I2V candidate
- **Seedance 2.5** — premium specialist for many references, white/clay-model guidance, V2V, and difficult hand/unboxing work
- **Veo 3.1** — high-finish option where three references are enough
- **Gen-4.5** — camera/motion specialist; provider documents object-permanence limitations
- **Aleph 2** — useful for real hand/proxy performance-plate editing

### Do not build around Sora

OpenAI’s Sora API is scheduled to shut down on **2026-09-24**.

## Geometry insight to test

If a listing has Matterport, CAD, floorplans, or another digital twin, use it as a geometry anchor.

Matterport can provide mesh/texture/photo/floorplan assets, and MatterPak can include OBJ geometry. A possible premium workflow is:

**real geometry -> simplified clay/white maquette render -> premium image transformation -> animation**

This could materially reduce hallucinated unseen architecture, but we have not tested it yet.

## Hand-interaction insight to test

For House in Hand and Unboxing, avoid pure generation first.

**Production hypothesis:** Film a real hand performing the desired move with a neutral proxy/rough maquette, then use Wan 3.0 / Seedance 2.5 / Gemini Omni edit / Aleph 2 to transform the proxy into the approved property miniature.

This should reduce the simultaneous burden of hand anatomy + physics + occlusion + property geometry.

## Prototype priority

### First — Real -> Miniature -> Real

This currently offers the best ratio of:

**visual impact × property fidelity × repeatability × production complexity**

Recommended first A/B:

- miniature master: Gemini 3 Pro Image vs FLUX.2 Max or Seedream 5.0 Pro
- transition/video: Gemini Omni Flash 1.1 vs Wan 3.0
- inexpensive miniature-motion control: H3/Hailuo 3

Do not animate until the miniature still passes side-by-side property QC.

### Second — House in Hand

Use a real hand/proxy performance plate. Keep initial rotation small (roughly 5-10°) rather than asking the model to invent unseen sides.

### Third — Premium Miniature Listing Unboxing

Use a real box/hand/proxy performance plate and split into controllable shots. First prototype should reveal/lift the model but **not open the house/roof**. Interior/roof-off requires documented floorplan/3D information.

## Property-fidelity rule

Critical visible features must be correct:

- story count
- roof silhouette
- garage count/position
- front entry
- major windows/doors and placement
- balcony/deck
- driveway
- pool shape/location
- major landscaping/terraces
- exterior materials
- prominent architectural features

A cinematic result with a material property error is a **failed generation**.

## Economics from research

Planning ranges for the first polished prototypes:

- Real -> Miniature -> Real: premium ~$12-$40 generation; 2-4 human hours
- House in Hand: premium ~$20-$70; 3-6 hours
- Premium Unboxing: premium ~$50-$150+; 6-12 hours

These are not measured project costs yet.

The prior $100-$200 Stage 1 budget is no longer a hard cap. Allow roughly **$150-$300 if required for the full three-prototype quality-ceiling test**, then optimize after we know what actually works.

## Exactly what the next chat should do

The next task is **execution, not more broad tool research**.

1. Select one **permissioned real listing** with strong exterior media. Prefer a listing with drone and/or Matterport if available.
2. Get original-resolution assets.
3. Build the first **Property Identity Pack** and Class A invariants ledger.
4. Choose the canonical real hero frame.
5. Generate and QC the miniature master before video.
6. Build **Real -> Miniature -> Real** in separate stages.
7. A/B Omni Flash 1.1 and Wan 3.0; use H3 as a cheap control.
8. Record every generation, rejection reason, generation spend, editing minutes, and total human time.
9. Decide pass/fail before starting House in Hand.

If no permissioned real listing assets are available yet, the next chat should define the exact asset-request package and QC worksheet, not drift into website/business building.

## Important work to keep separate

A future dedicated chat should research and systematize **professional cinematic terminology, lighting, atmosphere, lens choices, camera angles, camera motion, and prompt language** for premium realism.

That work is important, but it was intentionally not allowed to dilute the production-fidelity research. Do it after or alongside the first controlled prototype, as its own durable research file.

## Business context to preserve

The premium/exclusivity hypothesis still exists: this may ultimately be more valuable as a scarce bespoke service for higher-end agents than as a public low-priced AI-video product.

Do not finalize that strategy yet.

A warm private test path may exist through the user's niece, a San Diego realtor connected to an office marketing low-million-dollar properties. Use that relationship only after technical quality passes; it is not evidence of demand.

## Decision discipline

- GitHub remains the durable memory.
- Preserve factual property identity.
- Do not optimize cost before proving quality.
- Do not build automation before the manual workflow is repeatable.
- Do not build a broad public website yet.
- Do not let the “wow” factor excuse architectural errors.

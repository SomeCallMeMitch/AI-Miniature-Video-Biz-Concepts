# Project State

**Last updated:** 2026-09-02

## Current status

The project is testing whether AI-generated miniature/scale-model treatments of **actual real-estate listings** can become premium, factual, scroll-stopping listing media.

The first ChatGPT image-generation experiment has now been run on a real listing reference set. It produced one usable front hero miniature and one usable aerial miniature, but it failed to preserve the property reliably across front, rear, and aerial viewpoints. The project is paused by the user until tonight/tomorrow; on resumption, the priority shifts to defining the realtor use case and most saleable video format before investing in a full video build.

A current September 2026 production-feasibility study has now been completed and saved at:

- `research/2026-09-production-stack-feasibility.md`

### Current technical conclusion — 2026-09-02

**Conditional green light for controlled production tests.**

Current image/video systems appear capable of producing premium miniature real-estate creative that preserves a recognizable property **when used in a constrained multi-stage workflow with human QC**. They are **not reliable enough to be treated as exact architectural reconstruction systems or to let one video model freely invent the whole shot.**

The preferred production philosophy is:

> **Lock facts first. Animate second. Stylize scale and presentation, not the property itself.**

Recommended production structure:

**permissioned listing assets -> property identity/geometry pack -> approved miniature still or geometry-locked maquette -> constrained video generation/editing -> real hand/performance plate where needed -> conventional finishing -> property-fidelity QC**

### First direct image-generation evidence — 2026-09-02

**Observed:**

- The first front miniature was close enough to prove that a recognizable, compelling hero image is feasible.
- A second front pass improved the missing pergola/trellis details above the entry and windows, although the facade remained imperfect.
- The aerial miniature was close enough to retain as a useful approved view; the road is unnecessary and can be removed or reframed later.
- Rear/backyard attempts failed the property-fidelity gate. The garage and driveway orientation were reversed, front-facade elements reappeared at the rear, and roof/cupola details drifted.

**Prior assumption:** A well-anchored reference packet might support a convincing pseudo-360 or coherent front/aerial/rear miniature set.

**New evidence:** Even with front, rear, drone, roof, and floorplan references, ChatGPT image generation treated difficult viewpoint changes as opportunities to reinterpret the house rather than preserve one stable architectural object.

**Revised conclusion:** ChatGPT image generation is currently useful for approved hero images, but it is not reliable for true 360 or automatic multi-view architectural continuity. Near-term production should use one approved hero view or a small set of independently approved views. Do not imply that those images constitute a coherent 3D model, and do not generate an orbit between them unless real geometry supports the unseen angles.

## Current leading opportunity

### #1 — Miniature real-estate listing media

Potential formats:

- real -> miniature -> real transformation
- house in a human hand
- premium miniature listing unboxing
- roof-off/dollhouse reveal only when interior geometry can be supported accurately
- guess-the-price / social variants later

Potential buyers remain:

- individual realtors
- teams/brokerages
- builders/developers
- luxury property marketers
- vacation-rental operators
- adjacent high-ticket brokers later

The selling proposition remains:

> Turn an ordinary listing into a scroll-stopping social asset while preserving the identity of the actual property.

### Realtor-value hypothesis — 2026-09-02

The leading commercial hypothesis is now more specific: the miniature may be most valuable as **scroll-stopping paid-ad or social creative**, not as generic listing media for every agent.

Agents already investing in paid listing promotion, frequent Instagram/Reels/TikTok content, or differentiated luxury-property marketing are more plausible early buyers than low-activity agents who rarely advertise or post. This is still a hypothesis and needs current market research and interviews before it becomes positioning.

### #2 — Miniature product affiliate/content channel

Still a secondary concept, not the current focus.

## Production findings that now matter

### Still-image layer

Current leading candidates:

- **Gemini 3 Pro Image** — premium multi-reference miniature master
- **Gemini 3.1 Flash Image** — lower-cost/high-volume reference preparation
- **FLUX.2 Max/Pro** — premium A/B and corrective editing
- **Seedream 5.0 Pro** — useful when a sketch/clay/geometry reference is available
- **GPT Image 2** — corrective/semantic-edit fallback

### Video layer

Current leading candidates:

- **Gemini Omni Flash 1.1** — default control/iteration candidate; GA as of 2026-08-27
- **Wan 3.0** — new high-priority reference/edit candidate; added 2026-08-26
- **MiniMax H3 / Hailuo 3** — very strong cost/quality candidate for approved-still animation
- **Seedance 2.5** — premium specialist for many references, video-to-video, white/clay-model control, and difficult interactions
- **Veo 3.1** — high-finish option when its smaller reference budget is sufficient
- **Runway Gen-4.5** — camera/motion specialist, but provider itself documents object-permanence limitations
- **Runway Aleph 2** — useful for editing real hand/proxy performance footage

### Excluded forward-looking option

**Sora should not be built into the production architecture.** OpenAI’s Sora API is scheduled to shut down on **2026-09-24**.

## Property-accuracy rule

For normal listing media, we may stylize:

- scale
- presentation
- camera treatment
- environment
- packaging

We should not intentionally fabricate material property facts.

Treat these as critical invariants when visible:

- story count
- roof shape/silhouette
- garage count/position
- windows/doors and major placement
- driveway
- balconies/decks
- pool shape/location
- major landscaping/terraces
- exterior materials
- prominent architectural features
- important interior layout/finishes if interiors are shown

A beautiful result with a material property change is a **failed generation**, not a successful creative variation.

## Geometry-anchor strategy

**New inference — 2026-09-02:** When Matterport, CAD, floorplans, or another digital twin exists, use it as a geometry anchor rather than asking AI to infer unseen architecture.

Matterport can provide meshes/textures/photos/floorplans, and MatterPak can provide OBJ geometry plus textures and related assets. A premium workflow may render a simplified clay/white maquette at the exact desired angle, then use an image model to turn that geometry-locked render into a premium physical miniature.

This needs direct testing to determine whether the added labor materially improves property fidelity.

## Hand-interaction strategy

**New production hypothesis — 2026-09-02:** For difficult hand/unboxing shots, use a **real performance plate** with an actual hand and neutral proxy/rough maquette, then use reference-conditioned video editing to replace/transform the proxy into the approved property miniature.

Reason: pure generation otherwise asks one model to solve hand anatomy, physics, occlusion, property geometry, and camera motion simultaneously.

Test with Wan 3.0, Seedance 2.5, Gemini Omni editing, and/or Runway Aleph 2.

## Experiment order

### Test 1 to execute — **Real -> Miniature -> Real**

This currently offers the best ratio of:

**visual impact × property fidelity × repeatability × production complexity**

Why first:

- authentic listing media anchors beginning/end
- miniature still can be approved before motion
- first/last-frame workflows can control the transformation
- avoids hand/occlusion risk initially
- separates still-fidelity problems from video-fidelity problems

### Test 2 after that — **House in Hand**

Use a real hand/performance plate and keep first rotation small. Do not begin with a full 180°/360° orbit.

### Test 3 after Tests 1/2 pass — **Premium Miniature Listing Unboxing**

Use a real box/hand/proxy performance plate. The first prototype should reveal/lift the house but **not open the roof/house itself**. Only test interior/roof-off articulation once interior geometry is documented.

## Planning economics

Current generation-spend estimates for first polished prototypes:

- **Real -> Miniature -> Real:** premium ~$12-$40; cost-efficient target ~$3-$12; roughly 2-4 human hours
- **House in Hand:** premium ~$20-$70; cost-efficient target ~$5-$20; roughly 3-6 human hours
- **Premium Unboxing:** premium ~$50-$150+; low-cost attempt ~$15-$40 but not recommended as the quality target; roughly 6-12 human hours

These are **planning estimates**, not measured project costs. Actual retries and human time must be logged during testing.

### Budget assumption changed — 2026-09-02

**Prior belief:** Stage 1 technical proof should target roughly **$100-$200 total**.

**New evidence:** Premium reference-heavy/V2V workflows can consume meaningful retries, and quality is currently more important than forcing an early low-cost ceiling.

**Revised conclusion:** Do not use $100-$200 as a hard cap for the quality-ceiling test. Allow roughly **$150-$300 in generation spend if necessary for the full controlled three-prototype feasibility run**, while still tracking approved-output economics. The old $100-$200 target can remain an efficiency goal after the winning workflow is known.

## Business-model preference

Current thinking still favors **direct B2B service revenue first** rather than relying on platform ad revenue.

### Premium/exclusivity hypothesis — 2026-09-02

**Hypothesis:** The strongest initial offer may ultimately be a deliberately scarce, high-end creative service for agents handling multi-million-dollar properties rather than a widely advertised low-cost AI-video service.

Potential benefits include higher allowable production cost, differentiation, and less immediate broadcasting of the workflow.

This remains **unvalidated** and should not drive the technical experiment.

### Warm private test path

A possible first private client/realtor-feedback path exists through the user's niece, a San Diego realtor connected with an office marketing properties in the low-million-dollar range.

Use this only **after** the technical workflow passes. It is not evidence of demand.

## Important strategic conclusions

- Miniature itself is not a moat.
- Exact property identity matters more than generating a pretty miniature.
- Current AI can support the workflow but does not guarantee architectural truth.
- Direct testing confirms that strong single-view outputs do not imply cross-view consistency.
- Approve the miniature still/geometry before asking a video model to animate it.
- Avoid free camera orbits unless unseen angles are supported by real references/3D geometry.
- Use one approved hero image or a small independently approved view set rather than claiming a true 360 workflow.
- Human hands remain a strong scale cue, but hand+property interaction is a higher-risk technical problem.
- Performance-plate/V2V may be more reliable than pure generation for hands and packaging.
- Conventional editing/compositing is part of the premium workflow, not a failure of the AI approach.
- Build automation only after the manual/semi-manual workflow is repeatable and buyers care.
- Keep the public-vs-private/exclusivity question separate until technical quality is proven.
- A separate research session should cover professional cinematic terminology, lighting, atmosphere, lens language, camera angles, and motion prompting; do not dilute the fidelity experiment with that work yet.

## Current biggest unknowns

1. What exact video format and use case is most saleable to a realtor?
2. Which realtor segments already spend on paid listing ads or publish enough social content to value a scroll-stopping creative?
3. What current examples show agents using paid/social listing promotion, and where would a miniature asset fit in those campaigns?
4. Does Gemini Pro materially improve property fidelity or cross-view consistency versus the ChatGPT image-generation test?
5. Can an approved single-view hero miniature remain rigid and recognizable under controlled video motion?
6. Does adding actual 3D geometry materially reduce roof/side/footprint errors when a viewpoint change is required?
7. Which video model best preserves an approved miniature under motion: Omni Flash, Wan 3, H3, Seedance 2.5, or Veo 3.1?
8. How many generations/retries and human minutes does an approved client-ready clip actually require?
9. Does the miniature format produce better retention/engagement than conventional listing media?
10. Will luxury/upper-end agents pay materially more for bespoke/exclusive creative?

## Immediate next actions

1. Respect the user's pause until tonight/tomorrow.
2. On resumption, research the most saleable miniature-video format and the exact realtor job/use case it serves.
3. Identify realtor segments and concrete examples of agents using paid listing ads or heavy social promotion; distinguish observed behavior from inferred willingness to pay.
4. Define the first offer/test around that use case, including channel, duration, aspect ratio, hook, CTA, and success metric.
5. If useful, test the same property/reference packet in **Gemini Pro** and compare it with the ChatGPT results using the existing Class A fidelity gate.
6. Treat the approved front and aerial miniatures as independent hero assets; do not attempt a true 360 from them.
7. After the use case is chosen, build the smallest relevant video test. **Real -> Miniature -> Real** remains the technical default unless market research identifies a stronger saleable format.
8. A/B the selected video model(s) and log model/version, generations, rejection reasons, generation spend, edit minutes, and total human time.
9. Use the San Diego realtor connection only as a later private feedback path, not as demand evidence.
10. Keep cinematic-language research as a separate focused session.

## Current recommendation

**Pause as requested. On resumption, determine the realtor use case and most saleable format first, focusing on agents already buying attention through paid ads or heavy social activity. Then run the smallest controlled video test that matches that use case, using approved single-view hero assets rather than a true 360. Do not build the broader business, website, automation, or public launch yet.**

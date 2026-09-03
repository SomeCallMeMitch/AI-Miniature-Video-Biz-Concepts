# September 2026 Production-Stack Feasibility Study

**Date:** 2026-09-02  
**Project:** AI Miniature Video Biz Concepts  
**Research question:** Can currently available AI image and video systems transform actual real-estate listing assets into genuinely premium miniature/scale-model video while preserving the recognizable identity and important architectural facts of the property?

## Status labels used in this document

- **Verified current fact** — supported by current provider documentation, pricing, terms, or first-party release information.
- **Observed** — seen in an independent benchmark, practitioner test, or public example; useful signal, but not proof for our exact real-estate workload.
- **Inference** — conclusion drawn from current capabilities and limitations.
- **Hypothesis / needs testing** — plausible production tactic that must be validated with our own listing assets.
- **Needs revalidation** — time-sensitive point that should be checked again immediately before paid client production.

---

# 1. Executive conclusion

## Direct answer

**Yes, current September 2026 tools appear capable of producing premium miniature real-estate videos that preserve the recognizable identity of an actual property — but only with a controlled multi-stage production workflow and strict human quality control. They are not reliable enough to treat the listing as a prompt and let one generative video model freely invent the finished shot.**

The practical distinction is critical:

> **Current AI is good enough to be a production component; it is not yet a trustworthy architectural reconstruction system.**

For a high-end realtor client, the strongest workflow is:

**permissioned listing assets -> property reference/geometry pack -> approved miniature still or geometry-locked maquette -> constrained image-to-video / video editing -> hand-performance plate where needed -> conventional compositing/editing -> property-fidelity QC**

The property should be treated as a **locked product asset**, not as something the video model is allowed to redesign.

## The highest-confidence format today

**Test 2 — Real -> Miniature -> Real** has the best current ratio of:

**visual impact × property fidelity × repeatability × production complexity**

It lets us anchor the beginning and end in authentic listing media, approve the miniature representation before motion, and keep the AI-generated section short and controlled. It also avoids the most difficult current failure mode: hands physically occluding and manipulating a geometrically precise object.

## The highest-wow format

**Test 3 — Premium Miniature Listing Unboxing** remains the strongest theatrical concept, but it should be tested third. Hands, occlusion, box mechanics, object permanence, model removal, rotation, and property fidelity all have to work simultaneously. Pure generation is the wrong first approach. A real hand/box performance plate plus an AI replacement/edit pass is more promising.

## Important limit

No provider documentation reviewed promises exact preservation of architectural geometry across viewpoint changes. Generative models can still:

- change window count or spacing
- alter roof edges, dormers, balconies, rails, doors, garage bays, and trim
- move or reshape pools and landscaping
- invent unseen sides of a building
- distort the house when a hand crosses in front of it
- change scale during motion
- lose small features after occlusion
- create a beautiful but factually different property

For normal listing media, **a visually attractive error is still an error**.

## Strategic implication

The technical opportunity is credible enough to proceed to controlled production tests. It is **not** yet credible enough to promise arbitrary listings, arbitrary camera moves, or arbitrary hand interactions to paying clients without testing the specific shot.

The service can become premium precisely because the value is not “press the miniature button.” The value is the **reference preparation, shot design, constrained model selection, human correction, and factual QA** required to get from an attractive AI demo to listing-safe creative.

---

# 2. What changed since the project’s earlier assumptions

### Prior belief

The validation plan treated a **$100-$200 total technical-proof budget** as a useful initial constraint and assumed generation cost should be tightly controlled.

### New evidence — 2026-09-02

The strongest 2026 video systems are inexpensive for simple clips, but the difficult premium shots can require:

- separate high-fidelity still generation
- multiple model A/B tests
- first/last-frame transitions
- reference-heavy video generation
- video-to-video editing
- real hand-performance plates
- many rejected generations
- conventional post-production

Seedance 2.5, for example, is priced through Runway Dev at **$0.30/sec for 720p output and $0.68/sec for 1080p**, with additional charges for input/reference video. Veo 3.1 Standard is **$0.40/sec at 720p/1080p and $0.60/sec at 4K**. Cheap alternatives exist, but premium unboxing can consume retries quickly.

### Revised conclusion

**Do not use $100-$200 as a hard cap during the quality-ceiling test.** A controlled three-prototype real-estate feasibility run should be allowed roughly **$150-$300 in generation spend if needed**, while tracking the actual approved-output cost carefully. The recommended first prototype, Real -> Miniature -> Real, should still be testable for a small fraction of that.

The old budget remains useful later as an efficiency target after the best workflow is known.

---

## 2A. Direct property-test evidence added after the research pass

**Evidence date:** 2026-09-02
**Evidence type:** Direct observation from this project's first ChatGPT miniature image-generation test; not a provider claim or general benchmark.

The project used a real listing reference set containing front, rear, drone, roof/cupola, garage/driveway, and floorplan information.

### Results

- **Front hero:** The first miniature was close enough to demonstrate recognizable single-view property transformation. It missed pergola/trellis details above the entry and front windows.
- **Front correction pass:** A second front pass improved the pergola/trellis details but remained imperfect. It was accepted as close enough for experimentation, not as an exact architectural reconstruction.
- **Aerial hero:** The aerial miniature was close enough to retain. An unnecessary road can be removed or reframed later.
- **Backyard/rear:** Multiple attempts failed the factual-property gate. The garage/driveway orientation was reversed, front-facade elements appeared at the rear, and roof/cupola geometry drifted.
- **Drone-reference retry:** Supplying a drone view clarified the real geometry but did not make ChatGPT preserve it reliably in the generated backyard.

### Prior hypothesis

A sufficiently complete multi-reference packet might support a coherent pseudo-360 or at least a stable front/aerial/rear set.

### Revised conclusion

The test supports using ChatGPT for **independently approved single-view hero images**, but it does not support treating those images as views of one stable generated 3D object. True 360 continuity and large viewpoint changes remain unreliable without an actual 3D/geometry workflow.

Near-term production should therefore:

- animate only an approved view
- use small camera moves that do not expose unseen sides
- independently QC every generated angle
- use a small approved multi-view set only as separate editorial shots
- avoid claiming or implying geometric continuity between generated angles
- reserve full or large-angle orbits for geometry-supported workflows

This does not withdraw the study's conditional green light. It narrows it: the current opportunity is strongest for a controlled hero-view video, not for free multi-angle reconstruction.

### Commercial implication requiring research

The next question is now partly commercial: **which controlled hero-view video is most saleable to a realtor, and for what use case?**

The leading hypothesis is that miniature content is most valuable as a scroll-stopping paid-ad or high-frequency social asset for agents already investing in distribution, rather than as generic listing media for low-activity agents. That claim has not yet been validated.

The detailed session record is in `archive/chats/2026-09-02-miniature-image-generation-test.md`.

---

# 3. Current technology landscape

## 3.1 Still-image generation is now the strongest fidelity-control layer

The most important technical change is the strength of current **multi-reference image editing**.

### Gemini 3 Pro Image — primary premium still candidate

**Verified current facts:**

- Current model: `gemini-3-pro-image` (“Nano Banana Pro”).
- Up to **14 total reference images**; Google’s current image guide states up to **6 object images with high fidelity** for Gemini 3 Pro Image.
- Supports image generation/editing up to 4K.
- Paid API pricing: about **$0.134 per 1K/2K image** and **$0.24 per 4K image**.
- Google states that it does not claim ownership of generated content.
- Paid Gemini API data is not used to improve Google’s products under the current terms.
- Generated images contain an invisible **SynthID** watermark.

**Assessment:** Best first premium candidate for turning a multi-view listing reference packet into a controlled miniature still. It is inexpensive enough that we can generate many candidates and spend the budget on selection and correction rather than rationing attempts.

**Limitation:** “High fidelity” is not an architectural guarantee. Every candidate still must be checked against the listing.

### Gemini 3.1 Flash Image — primary cost-efficient still candidate

**Verified current facts:**

- Up to **14 total reference images**.
- Current guide states up to **10 object images with high fidelity**.
- Lower-cost/high-volume counterpart to Gemini 3 Pro Image.
- Current pricing snapshot is approximately **$0.067 at 1K, $0.101 at 2K, and $0.151 at 4K**.

**Assessment:** Very strong candidate for iterative property-reference preparation and the cost-efficient stack. The larger high-fidelity object reference allowance may actually be useful for a property packet that includes facade, side, rear, roof, pool, driveway, and material references.

### FLUX.2 Max / Pro — strong A/B and correction candidate

**Verified current facts:**

- FLUX.2 supports multi-reference editing: up to **8 references via API** and up to 10 in the playground.
- Up to 4MP output.
- BFL positions FLUX.2 Max as its highest-quality/final-asset option and Pro as production-at-scale.
- Current starting prices: Max roughly **$0.07/MP**; Pro roughly **$0.03/MP**.
- BFL’s developer terms say outputs may be used for commercial purposes and BFL claims no ownership rights in outputs.

**Important privacy/licensing note:** BFL’s August 4, 2026 API terms grant BFL a broad license to use API input and output for operating/improving products, including model training. That does not necessarily make the service unusable, but it matters for confidential/pre-market luxury listing assets. Use only after the client’s privacy requirements are understood.

**Assessment:** Excellent premium A/B model for difficult edits and proportion preservation, especially where the Google result is aesthetically strong but geometrically wrong.

### Seedream 5.0 Pro — useful geometry/sketch-reference option

**Verified current facts via current Runway documentation:**

- ByteDance image-generation/editing model.
- Up to **10 reference images**.
- Runway specifically notes strong detailed-prompt following, in-image graphics, and **high-fidelity sketch reference**.
- 1K is about **$0.05/image** and 2K about **$0.09/image** through Runway Dev.

**Assessment:** Worth A/B testing when we have a clay render, architectural sketch, floorplan-derived elevation, or simple 3D maquette render that we want the model to respect.

### GPT Image 2 — strong semantic-edit fallback

**Verified current facts through current Runway Dev documentation:**

- Up to **16 reference images** through Runway Dev.
- 1K/2K high-quality generation about **$0.20/image**; 4K high about **$0.41/image** through Runway Dev.
- OpenAI states customers own output under its applicable terms, subject to input-rights requirements.

**Assessment:** Useful as a second editor when a specific semantic correction is difficult in the primary model. The very high reference count is attractive, but Gemini currently has the clearest first-party workflow for high-fidelity multi-reference object composition.

### Midjourney V8.2 Edit — artistic secondary option, not core workflow

**Verified current facts from Midjourney’s current docs researched this session:**

- V8.2 is the current V8 line.
- V8.2 Edit supports multi-image reference/editing and up to four image references in the current edit workflow.
- Paid plans allow commercial use subject to Midjourney’s plan/company-size terms; Stealth is limited to higher tiers.

**Assessment:** Strong visual-development option, but lower reference count and lack of a public first-party production API discovered in this pass make it less attractive as the project’s property-fidelity backbone.

---

## 3.2 Video has improved sharply, but motion must be constrained

### Gemini Omni Flash 1.1 — strongest general workflow candidate

**Verified current facts:**

- `gemini-omni-1.1-flash` became **generally available on August 27, 2026**.
- Accepts text, image, and video input; generates video.
- Supports `text_to_video`, `image_to_video`, `reference_to_video`, `edit`, and `extend` workflows.
- Supports stateful conversational video editing where later edits can preserve unmentioned portions.
- 3-10 second output; extensions can build longer sequences.
- Supports 360p/720p/1080p/4K output at 24fps; Google notes 1080p and 4K are **upscaled** rather than native.
- Can use multiple reference images and short video references.
- First/last-frame interpolation is available.
- Negative-prompt parameter is not supported; constraints must be written directly in the prompt (“do not change…”).
- Effective direct API pricing is about **$0.10/sec for 720p** under current standard pricing.
- Paid Gemini API inputs/outputs are not used to improve Google products under current terms.

**Observed:** Artificial Analysis currently places Omni Flash among the market leaders in blind video preference. It is currently #1 in the no-audio image-to-video arena cited during this research and at/near the top in text-to-video. Pencil Community reported that a 10-shot stress test involving historically difficult physics/hands required fewer regenerations, with some first-try successes.

**Assessment:** Best default **control/iteration** model to test first. Its editing and reference workflow may matter more to real estate than simply having the prettiest first output.

### Wan 3.0 — new high-priority control/edit candidate

**Verified current facts via Runway Dev:**

- Added August 26, 2026.
- 2-30 second video.
- 480p, 720p, or 1080p.
- Native audio.
- Built for reference-driven shots; current Runway input documentation supports up to **10 image references, 5 video references, and 5 audio references**.
- Supports first/last keyframes.
- Current Runway Dev pricing: **$0.05/sec at 480p, $0.10/sec at 720p, $0.20/sec at 1080p**.

**Observed:** Wan 3.0 currently leads Artificial Analysis’s video-editing arena and is essentially tied for the lead in its text-to-video arena. Because the model is only days old, this is a strong signal but not mature production evidence.

**Assessment:** Must be included in our A/B tests. Especially promising for Real -> Miniature -> Real and for performance-plate editing because it combines long duration, references, editing strength, first/last frames, and reasonable cost.

**Needs revalidation:** Direct Alibaba/creator licensing and API terms should be checked before we build around a non-Runway endpoint. For initial production through Runway, Runway states generated content can be used commercially.

### Seedance 2.5 — premium reference-heavy specialist

**Verified current facts:**

ByteDance announced Seedance 2.5 on July 31, 2026 with:

- up to **30 seconds per generation**
- multi-round extension
- up to **30 image references, 10 video references, and 10 audio references**
- timestamp-level editing
- green-screen capability
- camera-perspective control
- white/clay-model reference workflows
- reference-based editing

Current Runway implementation supports:

- 4-30 second output
- 480p, 720p, 1080p
- text/image/video input
- up to 50 references in the documented limits
- current pricing:
  - 480p: **$0.20/sec output + $0.10/sec input/reference video**
  - 720p: **$0.30/sec output + $0.15/sec input/reference video**
  - 1080p: **$0.68/sec output + $0.34/sec input/reference video**
  - reference images/audio are free through Runway Dev

**Assessment:** Strongest specialist for the hardest premium shot when we need many property references, a real performance plate, a clay/white 3D model, or precise staged actions. The reference budget is uniquely suited to a building because a property may need front, rear, sides, roof, landscape, pool, materials, and multiple keyframes at once.

**Observed but lower-confidence:** Some creator tests report better long-sequence consistency than prior models, but there is no robust property-fidelity benchmark or published production retry rate. Treat provider demos and independent creator tests as capability signals, not reliability guarantees.

### Veo 3.1 — high-finish premium option with reference limits

**Verified current facts:**

- 4/6/8 second output.
- 720p, 1080p, and 4K; 1080p/4K require 8-second generation.
- Up to **3 reference images**.
- First/last frame control.
- Image-to-video and extension.
- Reference-image and high-resolution workflows require 8 seconds.
- 24fps.
- Current Gemini API pricing:
  - Standard: **$0.40/sec at 720p/1080p; $0.60/sec at 4K**
  - Fast: **$0.10/sec at 720p; $0.12/sec at 1080p; $0.30/sec at 4K**
  - Lite: **$0.05/sec at 720p; $0.08/sec at 1080p**
- The current Veo 3.1 Gemini API models are marked **Preview**.

**Assessment:** Excellent high-finish option when the shot is already geometrically locked and does not require many references. The three-reference ceiling is a disadvantage for a complex house compared with Omni, Wan 3, H3, or Seedance 2.5.

### MiniMax H3 / Hailuo 3 — exceptional cost-quality candidate

**Verified current facts:**

MiniMax’s July/August 2026 materials state H3:

- accepts multimodal context across text, images, video, and audio
- produces native stereo audio
- 4-15 seconds
- up to 2K through its regeneration workflow
- 24fps
- first/last frame mode
- reference mode with up to **9 images, 3 videos, and 3 audio clips**

Current Runway Hailuo 3 pricing:

- **$0.10/sec at 768P**
- **$0.15/sec at 2K**
- plus about **$0.02 per reference image**

**Observed:** H3/H3 Max currently ranks at or near the top of Artificial Analysis’s image-to-video arena. This is preference evidence, not architectural-accuracy evidence.

**Assessment:** Excellent candidate for low-cost animation of an already approved miniature still, and worth a premium A/B test because the cost is so low that we can afford many attempts.

**Licensing note:** MiniMax’s open H3 community license has conditions for self-hosted commercial products, including an attribution/UI requirement and a revenue threshold requiring separate authorization. For initial production, using a hosted commercial provider such as Runway avoids building around the self-hosted license before legal review; model/provider terms should still be revalidated before client deployment.

### Runway Gen-4.5 — strong camera/motion specialist, but known permanence risk

**Verified current facts:**

- Text-to-video and image-to-video.
- 2-10 seconds.
- 720p output at 24/25fps.
- **$0.12/sec** via Runway Dev.
- ProRes/PNG-sequence and HDR/10-bit output options are available at additional cost in supported workflows.
- Runway explicitly lists current limitations including **causal reasoning and object permanence**, with objects sometimes disappearing or appearing after occlusion.

**Assessment:** Strong for elegant, moderate camera motion from an approved still. Less attractive for the hand-unboxing problem because hand occlusion is exactly where object-permanence failures matter.

### Runway Aleph 2 / Edit Studio — performance-plate specialist

**Verified current facts:**

- Designed to edit existing footage, including product swaps, relighting, VFX, background changes, and multi-shot sequences.
- Input up to 30 seconds, output up to 1080p in current documented workflows.
- Runway Dev pricing: about **$0.28/sec**.

**Assessment:** Worth testing when we shoot an actual hand opening a box or holding a neutral proxy. It is not the preferred pure miniature generator; it is a way to preserve real camera/hand motion while replacing the proxy object or treatment.

### Luma Ray3.14 / Ray3 Modify — useful web-only V2V backup

**Verified current facts:**

- Ray3.14 supports native 540p/720p/1080p at 24fps and video modification up to 18 seconds.
- Luma explicitly says Ray3.14 currently lacks character consistency and reference-image features.
- Ray3.14 is currently **not available through Luma’s API**.
- Ray3 Modify can use a real input video plus keyframes/character-reference-style control.
- Luma’s paid Plus and higher plans support commercial work; lower tiers have watermark/noncommercial restrictions.

**Assessment:** Interesting manual performance-plate/V2V backup, but lack of current API access and Ray3.14 reference limitations make it secondary to Wan 3, Omni, Seedance 2.5, and Runway Aleph for this project.

### OpenAI Sora — do not build around it

**Verified current fact:** OpenAI’s Sora API is scheduled to shut down **September 24, 2026**, after the Sora web/app product was discontinued earlier in 2026.

**Conclusion:** Exclude Sora from forward-looking production architecture. It can be treated only as a historical quality benchmark.

---

# 4. Comparison matrix

**Important:** The qualitative fidelity assessments below are project-specific research judgments, not provider-certified measurements. No public benchmark found tests exact real-estate architecture preservation.

| Tool/model | Property/reference fidelity | Photorealism / miniature potential | Hand / interaction potential | Camera / edit control | Output / duration | Current pricing snapshot | API / automation | Commercial/privacy notes | Best role | Major limitation |
|---|---|---|---|---|---|---|---|---|---|
| **Gemini 3 Pro Image** | **Very strong still candidate**; up to 14 total refs, lower high-fidelity object sublimit | Very strong | N/A still only | Strong image edit | up to 4K | ~$0.134 1K/2K; $0.24 4K | Yes | Google claims no output ownership; paid data not used to improve products; SynthID | Premium miniature master still | Still generative; no architectural guarantee |
| **Gemini 3.1 Flash Image** | **Strong / high reference capacity**; up to 10 high-fidelity objects | Strong | N/A | Strong iterative edit | up to 4K | ~$0.067 1K; $0.101 2K; $0.151 4K | Yes | Same paid-data advantage; SynthID | Cost-efficient reference preparation | May trail Pro in final polish |
| **FLUX.2 Max/Pro** | Strong multi-ref edit; up to 8 API refs | Very strong | N/A | Strong editing; Flex adds control | up to 4MP | Max from ~$0.07/MP; Pro ~$0.03/MP | Yes | Commercial output allowed; API terms permit broad input/output use for improvement | Premium A/B still / correction | Privacy terms may be undesirable for confidential listings |
| **Seedream 5.0 Pro** | Strong reference/sketch candidate; up to 10 refs via Runway | Strong | N/A | Good image edit | 1K/2K via Runway | ~$0.05/$0.09 image | Yes via Runway | Runway commercial rights; revalidate ByteDance-specific terms | Clay/sketch-to-premium still | Less property-specific evidence |
| **GPT Image 2** | Strong; up to 16 refs through Runway | Strong | N/A | Strong semantic editing | 1K/2K/4K | high: ~$0.20 1K/2K; $0.41 4K via Runway | Yes | Commercial; input rights required | Difficult corrective edit / alternate master | Not specifically benchmarked for architecture |
| **Gemini Omni Flash 1.1** | Strong reference/edit workflow | Strong; 1080/4K are upscale | **Promising**, especially with input/reference video | **Excellent:** I2V, ref-to-video, edit, extend, first/last, conversational edits | 3-10s; extensions; 24fps | ~**$0.10/s 720p** direct | **Yes, GA** | Google paid-data protections; output ownership not claimed; invisible provenance | Default controlled video engine | High-res is upscale; no negative-prompt parameter; geometry can still drift |
| **Wan 3.0** | **Very promising**; up to 10 image refs + video refs | Strong current benchmark signal | Promising for performance-plate edits | **Excellent:** first/last, reference-heavy, edit | 2-30s; 480/720/1080 | $0.05/$0.10/$0.20 per sec via Runway | Yes via Runway | Runway commercial rights; direct terms need revalidation | Real-mini-real; V2V; cost-efficient control | Very new; production reliability unknown |
| **Seedance 2.5** | **Highest reference budget**; 30 image + 10 video refs | Very strong official examples | **Highest upside for complex interaction** | **Excellent:** timestamp edit, V2V, camera, white/clay model | 4-30s; 480/720/1080 via Runway | $0.20/$0.30/$0.68 per output sec + video-ref costs | Yes through Runway; BytePlus route emerging | Runway commercial rights; direct BytePlus terms revalidate | Hard premium shots / unboxing / many refs | Expensive at 1080p; new; retry reliability not established |
| **Veo 3.1** | Good but only 3 refs | **Very strong finish** | Good but not our highest-control option | first/last, I2V, extension | 4/6/8s; 720/1080/4K; 24fps | Standard $0.40/s 720/1080, $0.60 4K; Fast lower | Yes | Google paid-data protections; Preview endpoint risk | Polished hero/transition A/B | 3-ref ceiling; 8s requirement for refs/high-res; preview |
| **MiniMax H3 / Hailuo 3** | Strong multimodal refs; up to 9 images official H3 | Strong benchmark signal | Promising | first/last + reference mode | 4-15s; 768P / up to 2K | ~$0.10/s 768P; $0.15/s 2K + image refs via Runway | Yes | Hosted-provider terms easiest initially; self-host license has conditions | Cheapest serious I2V animation candidate | Architecture-specific fidelity unproven; licensing differs by route |
| **Runway Gen-4.5** | Good start-image lock, low multi-ref control | Strong | Moderate | Strong motion/camera prompting | 2-10s; 720p | $0.12/s | Yes | Runway says outputs commercially usable | Controlled camera movement from approved still | Runway itself lists object-permanence/causal failures; 720p |
| **Runway Aleph 2** | Depends on input plate/reference | Strong VFX/edit role | **Strong workflow potential with real hands** | V2V editing, product/scene replacement | up to 30s input; up to 1080p | ~$0.28/s | Yes | Runway commercial rights | Transform a filmed hand/proxy performance | Not a property reconstruction model; input/edit quality dependent |
| **Luma Ray3.14/Modify** | Ray3.14 lacks refs; Modify can preserve motion | Strong | Useful V2V | Keyframes/Modify | up to 18s Modify; native 1080p | credit/subscription based | **Ray3.14 no API currently** | Plus+ commercial; lower plans limited/watermarked | Manual V2V backup | API/reference limitations |

---

# 5. Property reconstruction and reference preparation

## The property reference packet should become a formal production asset

For every listing, create a **Property Identity Pack** before any premium generation.

### Exterior minimum

Recommended ideal source set for a detached luxury property:

1. canonical front three-quarter hero image — high resolution
2. straight or near-straight front elevation
3. left/front three-quarter
4. right/front three-quarter
5. left side
6. right side
7. rear three-quarter
8. rear elevation
9. elevated/drone front
10. elevated/drone rear
11. roof/footprint aerial if available
12. driveway/garage relationship
13. pool/yard relationship if applicable
14. prominent architectural detail close-ups
15. material/color reference close-ups

**Ideal:** 12-20 original-resolution exterior images rather than compressed MLS screenshots.

### Drone footage

**Strongly helpful, not always mandatory.**

Drone media resolves facts that ground-level photos often hide:

- roof plan and pitch relationships
- footprint
- chimney/skylight placement
- pool location and shape
- driveway approach
- side-yard geometry
- relationship to landscaping/terraces

It is especially valuable if a miniature rotates or the camera moves above eye level.

### If a Matterport / digital twin exists

**Verified current fact:** Matterport’s 2026 API exposes digital-twin assets including meshes, textures, photos, floorplans, and related model data. MatterPak exports can include an `.OBJ` 3D mesh with textures plus floorplans and a colorized point cloud.

**Premium recommendation:** If rights/access permit, use the mesh/floorplan/CAD/architectural model as a **geometry anchor**, not merely as another aesthetic reference.

Possible workflow:

1. import OBJ/CAD/mesh into Blender/SketchUp/3D workflow
2. simplify it into a clean architectural maquette / “white model”
3. render exact camera angles needed for the miniature shot
4. use Gemini Pro Image / Seedream 5 Pro / FLUX.2 to convert the geometry-locked clay render into a premium physical scale-model finish
5. animate that approved view

This hybrid approach should reduce the model’s need to invent unseen architecture.

### Interior requirement

Do not show an open roof/interior miniature unless we can document the interior.

If an interior miniature appears, request:

- floorplans
- Matterport/3D tour if available
- 2-4 photos per important room/zone
- staircase/hall relationships
- major finishes
- window/view direction
- ceiling heights/features when visually material

---

# 6. Property-fidelity system

## 6.1 Create an “invariants ledger” before prompting

For each shot, list facts that **must not change**.

Example exterior invariants:

- number of stories
- overall roof silhouette and major roof planes
- garage bay count and garage position
- primary entry position
- major window/door count and spacing visible in the shot
- balcony/deck presence and position
- pool shape/location
- driveway direction
- major retaining walls / terraces
- exterior material palette
- prominent chimney / tower / dormer / arch / cantilever

## 6.2 Fidelity classes

### Class A — critical factual features

Must be correct. Any error = reject.

Examples:

- extra/missing garage bay
- changed roof form
- moved pool
- extra balcony
- removed exterior staircase
- changed story count
- materially different front-door/major-window layout

### Class B — important recognizable details

Should be visually consistent. Repeated or obvious mismatch = reject.

Examples:

- railing design
- window mullions
- exact trim/stone distribution
- landscape masses
- small roof vents/skylights

### Class C — miniature presentation details

May change if they do not imply a false property fact.

Examples:

- scale-model base
- tiny plaque
- background tabletop
- packaging material
- macro depth-of-field treatment
- lighting environment

## 6.3 QC method

For the canonical hero view:

1. put real reference and miniature output side-by-side
2. also test an aligned overlay where practical
3. check every Class A feature
4. check Class B details
5. scrub every video frame around occlusions and transitions
6. watch once at normal speed for “AI weirdness”
7. watch once muted and frame-by-frame for geometry changes
8. realtor/client gets final factual sign-off before publication

---

# 7. Best-quality premium production stack

## A. Best-quality premium stack

### Stage 1 — rights and source intake

- Obtain permission for listing images/video and any photographer/MLS/3D-tour assets used.
- Request original files.
- Determine whether the listing is pre-market/confidential and select providers accordingly.

### Stage 2 — geometry/reference preparation

**Best case:** use Matterport/CAD/floorplans + listing photos + drone.

Create:

- property identity pack
- invariants ledger
- canonical hero frame
- optional clay/white 3D maquette renders for difficult angles

### Stage 3 — premium miniature master still

**Primary:** Gemini 3 Pro Image, 2K initially; 4K once the composition is approved.  
**A/B:** FLUX.2 Max.  
**Geometry/sketch specialist:** Seedream 5.0 Pro when a clay render is available.  
**Correction fallback:** GPT Image 2.

Generate multiple candidates. Do not animate until one passes the fidelity checklist.

### Stage 4 — video motion

**Default A/B pair:**

- Gemini Omni Flash 1.1
- Wan 3.0

Use short, restrained motion and strong “rigid physical model” constraints.

**Premium specialists:**

- Seedance 2.5 for reference-heavy hand/V2V/white-model/complex sequences
- Veo 3.1 for a polished high-resolution shot when three references are sufficient
- Gen-4.5 for elegant camera motion from a locked image

### Stage 5 — real hand / object interaction

For difficult hand shots, do **not** ask the model to invent precise fingers, precise property geometry, and complex mechanics from scratch.

**Hypothesis to test:**

1. shoot a real hand performing the action with a neutral proxy object or crude physical maquette of similar size
2. use the approved miniature still/3D render as the target object reference
3. run the plate through Wan 3.0, Seedance 2.5, or Runway Aleph 2
4. use masking/compositing for stubborn occlusion boundaries

The performance plate supplies real physics, hand anatomy, timing, shadows, and camera behavior. The model’s job becomes **replacement/transformation**, not simultaneous invention of everything.

### Stage 6 — conventional finishing

Use normal editing/VFX tools for:

- match cuts
- masks / rotoscoping where required
- speed adjustments
- stabilization
- color matching between real and miniature shots
- subtle sharpening/upscale only after the shot is approved
- sound design
- titles/branding
- final 9:16 and 16:9 crops

### Expected premium economics

For a single 6-12 second hero asset during prototyping:

- still generation itself is usually only a few dollars even with many candidates
- controlled video generation can be $10-$50 for a simple successful shot
- a complex reference-heavy hand/unboxing shot can consume **$50-$150+** in generation attempts
- early R&D may exceed this because we should A/B several models rather than prematurely optimize cost

**The expensive input is likely to be human production time, not inference.**

---

# 8. Lowest-cost commercially viable stack

## B. Lowest-cost commercially viable stack

This stack is only acceptable if it passes the same factual fidelity gates.

### Still preparation

**Primary:** Gemini 3.1 Flash Image.  
**Alternate:** Seedream 5.0 Pro or FLUX.2 Pro.

### Video

Use three inexpensive engines according to the shot:

1. **Hailuo 3 / MiniMax H3** — animate an already approved miniature still; very low current cost.
2. **Wan 3.0 720p** — first/last-frame transitions, reference-driven shots, and editing at ~$0.10/sec.
3. **Gemini Omni Flash 720p** — iterative edit/reference workflows at roughly ~$0.10/sec.

Do not introduce Seedance 2.5 or Veo Standard unless the lower-cost engines fail the fidelity/quality gate.

### Finishing

Use conventional editing to hide joins and avoid paying a generative model to solve something that a match cut, mask, or 8-frame dissolve can solve deterministically.

### Expected economics

For the recommended Real -> Miniature -> Real format, a production-mature version may plausibly reach **single-digit to low-teens generation spend per approved asset**. This is a hypothesis until we log actual retries.

The cheap stack is not meant to make the hardest unboxing format cheap. It is meant to identify the simplest repeatable premium-looking format whose property fidelity survives.

---

# 9. Prompting approach for property fidelity

## 9.1 Still-image prompt structure

Use a structured prompt with explicit roles for each reference.

Example pattern:

> Create a museum-quality physical architectural scale model of the **exact property** represented by the supplied references. Reference 1 is the canonical camera angle and composition. References 2-8 exist only to resolve the property’s true roof geometry, side/rear massing, window and door positions, garage, pool, driveway, landscaping, and materials. Preserve the exact exterior architecture and relative position of all visible permanent features. Change only **scale and presentation**: the property should look like a professionally fabricated 1:24 display maquette on a premium base. Do not redesign, modernize, simplify, add, remove, or relocate architectural features. Do not invent views or amenities. If a detail is ambiguous, prefer the geometry visible in the references rather than creating a new feature.

Then add only the minimum presentation description necessary for the shot.

## 9.2 Constraint language

Where the model supports negative prompts, explicitly exclude:

- extra windows or doors
- altered roofline
- extra garage bays
- invented balconies
- relocated pool
- redesigned driveway
- fantasy landscaping
- warped railings
- changed exterior materials
- text/signage unless requested
- deformed straight lines

Gemini Omni does not have a separate negative-prompt parameter, so put constraints in normal prose.

## 9.3 Video prompt structure

Video prompt should primarily describe **motion**, because the approved image already defines appearance.

Example:

> Single continuous shot. The house is a rigid, professionally fabricated physical scale model; its architecture, window/door layout, roof shape, materials, landscaping, pool, and proportions do not change at any point. The model does not flex, morph, grow, shrink, or redesign. Camera makes a very slow short push-in. The human hand remains anatomically correct and supports the model from below. Fingers never pass through the structure. Only the hand and camera move; the property remains a rigid object.

Avoid asking for multiple complex actions in one short generation unless the model has first/last keyframes or a performance plate.

---

# 10. Controlled experiment 1 — House in Hand

## Objective

Produce an immediate first-second visual hook in which the actual listing is unmistakably represented as a premium physical miniature resting in or being gently manipulated by a real-looking human hand.

## Source assets required

**Ideal exterior set:** 12-18 high-resolution listing photos.

Mandatory:

- front three-quarter hero
- front elevation
- both front-side views
- rear
- both sides when available
- garage/driveway
- pool/yard if present
- 2-4 elevated/drone views
- close material/detail references

**Drone:** strongly helpful, especially if any rotation reveals roof or side geometry.

**Performance asset:** for the premium route, shoot a real hand plate with a neutral proxy object of approximately the target model’s size.

## Recommended production stages

1. **Reference prep:** property identity pack + invariants ledger.
2. **Miniature master:** Gemini 3 Pro Image; A/B FLUX.2 Max.
3. **Hand plate:** photograph or shoot a real palm/pinch grip with proxy.
4. **Composite/keyframe:** place approved miniature into the real hand plate and establish correct scale/shadow.
5. **Motion A/B:** Wan 3.0 + Gemini Omni Flash.
6. **Hard-shot escalation:** Seedance 2.5 V2V/reference mode or Aleph 2 if fingers/occlusion fail.
7. **Edit:** add optional 0.5-1.0s cut/match to real listing footage.

## Reference strategy

- Use the actual hero listing view as the primary composition reference.
- Supply side/aerial references only to resolve geometry, not to invite a free orbit.
- If the miniature tilts, limit the first prototype to roughly **5-10 degrees** of object rotation so the model does not have to invent an entirely unseen elevation.
- If a larger rotation is desired later, use a second approved miniature keyframe generated from the corresponding real property view.

## Shot list

**Version 1 — safest premium hook, 4-5s total**

- **0.0-0.5s:** miniature already fully visible in palm — no slow reveal; viewer understands the impossible scale immediately.
- **0.5-2.5s:** fingers gently settle; hand tilts only a few degrees; camera makes a small push.
- **2.5-3.5s:** hold long enough for the property to read.
- **3.5-5.0s:** optional hard/match cut to actual listing hero footage.

## Prompt approach

Focus on:

- rigid model
- exact property
- anatomically correct hand
- no object deformation
- subtle motion
- shallow macro look only after fidelity is locked

Do **not** prompt a dramatic 180° rotation on the first test.

## Planning retry budget

No provider publishes a reliable retry rate for this exact architecture+hand task.

**Planning estimate until measured:**

- still master: 8-16 candidates/edits
- hand/video stage: 10-25 video generations across two models
- escalation: 2-6 V2V generations if using Seedance/Aleph

## Estimated generation spend

**Premium exploratory:** roughly **$20-$70**.  
**Cost-efficient attempt:** roughly **$5-$20** if H3/Wan/Omni handles the shot.

These are planning estimates, not observed costs.

## Expected human production time

**3-6 hours** for the first serious prototype, excluding learning/setup time for a new model or 3D tool.

A mature repeated workflow should be faster.

## Major failure modes

- fingers merge or duplicate
- finger passes through roof/wall
- miniature deforms under grip
- roofline changes during tilt
- windows disappear behind occlusion and return differently
- house changes size relative to hand
- shadow/contact makes model look pasted on
- landscaping becomes a soft green blob
- hand looks synthetic even if house is accurate

## Property-fidelity checklist

- story count exact
- roof silhouette exact
- garage bay count/position exact
- front entry exact
- visible major windows/doors agree with reference
- balcony/deck exact
- pool/driveway/major landscaping relationship correct
- exterior material/color correct
- no new architectural feature appears during motion

## Quality-control checklist

- first frame reads as the same house in under one second
- hand anatomy survives every frame
- contact/occlusion is believable
- no house morph during hand motion
- no visible AI jitter on straight architectural lines
- lighting/shadow makes model feel physically present
- optional transition to real house confirms rather than exposes a mismatch

## Pass/fail

**PASS** only if all Class A property features are correct and the house remains rigid during the full hand interaction.  
**FAIL** if the clip is visually exciting but any material architectural fact changes or the hand/house intersection is obviously synthetic.

---

# 11. Controlled experiment 2 — Real -> Miniature -> Real

## Objective

Create a short transformation where viewers see the real listing, watch it become a convincing miniature of the **same property**, experience a brief miniature moment, and return to real footage.

This is the recommended first experiment.

## Source assets required

**Ideal:** 8-14 high-resolution exterior images plus one real listing clip from the desired hero angle.

Best source clip:

- 4-8 seconds
- gentle movement or stable gimbal/drone movement
- clear front three-quarter view
- limited foreground occlusion
- high resolution

**Drone:** helpful but not mandatory. A drone clip is excellent if it gives a slow, stable angle that can be recreated in miniature.

## Recommended model/tool by stage

1. **Select canonical frame:** actual listing video.
2. **Miniature still:** Gemini 3 Pro Image; A/B FLUX.2 Max or Seedream 5 Pro.
3. **Alignment/composite:** conventional editor; keep camera/framing as close as possible.
4. **Real -> miniature transition:** Wan 3.0 first/last-frame or Gemini Omni first/last interpolation/edit.
5. **Miniature motion:** Omni, H3, Wan 3, or Gen-4.5 with restrained movement.
6. **Miniature -> real:** second first/last transition or a carefully designed reverse/match edit.
7. **Optional high-finish A/B:** Veo 3.1 Fast/Standard if the transition needs more polish and the three-reference ceiling is sufficient.

## Exact workflow

1. Choose the exact real frame we want viewers to recognize.
2. Build the miniature still at the **same camera angle and perspective**.
3. Overlay real and miniature frames and fix property discrepancies before video.
4. Generate a short A->B interpolation rather than asking one model to invent the entire sequence.
5. Generate a separate 2-3s miniature “hold” shot with almost no property motion.
6. Generate or edit a B->A transition.
7. Assemble the sequence conventionally.
8. Color/sound-match the real and miniature sections.
9. Run fidelity QC frame by frame.

## Reference-image strategy

The real source frame is the canonical geometry/composition. Multi-view references are only for resolving hidden facts.

This is the format where **alignment is a feature**: the more closely the real and miniature frames match, the stronger the transformation feels and the easier it is to identify property drift.

## Shot list — recommended 7-8s version

- **0.0-1.2s:** actual listing footage, stable recognizable hero view
- **1.2-2.4s:** real -> miniature transformation
- **2.4-5.0s:** miniature hold with subtle camera push / environmental motion
- **5.0-6.2s:** miniature -> real
- **6.2-7.5s:** actual property confirmation

A shorter 5-6s version can be tested for social retention after technical proof.

## Prompt approach

Transition prompt should say:

- same property
- same camera/perspective
- architecture does not redesign
- only material scale/presentation transforms
- no added/removed features

Miniature hold prompt should focus almost exclusively on restrained motion.

## Planning retry budget

- still master: 6-12 candidates/edits
- A->B transition: 4-8 generations
- miniature hold: 4-8 generations
- B->A transition: 4-8 generations

Not every stage must use a different model; A/B only where needed.

## Estimated generation spend

**Premium exploratory:** about **$12-$40**.  
**Cost-efficient target:** about **$3-$12**.

## Expected human production time

**2-4 hours** for the first polished prototype.

## Major failure modes

- miniature does not line up with real frame
- transition invents windows/roof geometry mid-morph
- landscaping melts rather than transforms
- camera drifts during interpolation
- miniature hold subtly changes architecture
- transition back exposes different roof/window layout
- real clip contains foreground occlusions the model cannot reconcile

## Property-fidelity checklist

Same as Test 1, plus:

- miniature silhouette aligns with real silhouette
- major facade landmarks map to the same positions before/after
- pool/driveway/landscape do not teleport
- no new feature is introduced during the transformation

## Quality-control checklist

- viewer immediately understands “same house, different scale”
- start/end real footage is unmodified or clearly source-authentic
- transformation is visually smooth but not so morph-heavy that factual changes are hidden
- miniature still passes side-by-side/overlay review
- miniature hold remains stable

## Pass/fail

**PASS** if the same-property identity is obvious, every Class A fact is preserved, the miniature section looks physically plausible, and the transition does not expose architectural invention.  
**FAIL** if it is merely a stylish house-to-small-house morph but the property itself has changed.

## Why this should be first

This test separates the two hardest questions:

1. Can we build a faithful miniature still?
2. Can we animate/transition it without losing that fidelity?

It minimizes hand/physics risk while still producing a compelling commercial asset. If this format fails the property-fidelity standard, the more elaborate tests should not be pursued yet.

---

# 12. Controlled experiment 3 — Premium Miniature Listing Unboxing

## Objective

Create a luxury package-opening sequence where a human hand opens a premium box and reveals a highly accurate miniature of the actual listing; the model may be lifted or gently rotated, then the sequence can transition into real listing footage.

## Scope discipline for prototype 1

**Do not make the house itself open in the first unboxing test.**

Opening/removing a roof or revealing interior rooms creates another factual reconstruction problem. First prove:

1. box mechanics
2. hand anatomy
3. miniature fidelity
4. model removal
5. limited rotation
6. transition to real footage

A roof-off/interior version should be a later test only when floorplans/3D-tour geometry is available.

## Source assets required

**Exterior:** 16-24 high-resolution images.  
**Drone:** strongly recommended.  
**3D/floorplan:** strongly recommended if available.  
**Interior:** required only if an interior is shown.

Also create:

- approved box/packaging design
- physical performance plate with a real box
- neutral proxy/maquette matching intended miniature size
- clean plate without hands when possible

## Recommended tool by stage

1. **Property/geometry prep:** Matterport/CAD/OBJ if available + reference pack.
2. **Miniature still/keyframes:** Gemini 3 Pro Image; FLUX.2 Max / Seedream 5 Pro A/B.
3. **Package still/keyframes:** Gemini Pro or conventional design/composite.
4. **Real performance plate:** actual hands open real box and lift proxy.
5. **Primary V2V A/B:** Wan 3.0 + Seedance 2.5.
6. **Secondary V2V:** Runway Aleph 2 or Gemini Omni edit.
7. **Transition to real:** Wan/Omni first-last; Veo optional polish.
8. **Post:** masks/rotoscoping, shadow/contact fixes, sound design, color match.

## Exact workflow

1. Build and approve the miniature master from property references.
2. Create front/side/aerial approved keyframes if rotation is required.
3. Shoot hand performance with a real box and a neutral proxy object.
4. Lock the strongest start/end keyframes.
5. Transform proxy into the approved miniature using V2V/reference workflow.
6. Split the sequence into multiple short shots if object permanence fails; do not insist on a single heroic 10s take.
7. Composite/mask finger edges rather than regenerating a nearly perfect shot because of one local problem.
8. Match cut from the lifted model to the actual property.

## Reference strategy

Seedance 2.5 is attractive because its reference budget can include:

- canonical miniature hero
- left/right miniature views
- aerial/clay render
- real property views
- packaging style frame
- hand/proxy performance video

Wan 3.0 is attractive because it currently benchmarks very strongly for video editing while remaining inexpensive.

## Shot list — 8-10s first prototype

- **0.0-1.2s:** premium box already centered, hand enters
- **1.2-3.0s:** lid opens with real physical mechanics
- **3.0-4.5s:** miniature is revealed, full property readable
- **4.5-6.5s:** fingers lift model and tilt only 10-15°
- **6.5-8.0s:** model held cleanly for recognition
- **8.0-9.5s:** match/transition into real listing footage

Avoid a full spin.

## Prompt approach

Prioritize physical invariants:

- real filmed hand motion is authoritative
- box shape and lid mechanics remain unchanged
- replacement miniature is rigid
- fingers stay outside solid geometry
- property architecture remains fixed
- no extra appendages/fingers
- no model flexing
- no feature changes after occlusion

## Planning retry budget

- still/keyframes: 10-20
- V2V per shot: 5-12 attempts
- likely 3-4 generated/edited shot segments
- total video generations: approximately **20-50** across models for the first polished prototype

## Estimated generation spend

**Premium exploratory:** approximately **$50-$150+**.  
At 1080p, Seedance V2V can become expensive because both output and input/reference video are billed. Wan 3, H3, Omni, or Aleph may solve some sections more cheaply.

**Low-cost version:** technically possible to attempt around **$15-$40**, but it is not recommended as the quality target for this prototype. If the cheaper engines cannot pass the hand/fidelity gate, stop rather than shipping a compromised result.

## Expected human production time

**6-12 hours** for the first polished prototype, including plate shooting and compositing.

## Major failure modes

- box lid opens before hand action or with impossible mechanics
- fingers duplicate/merge
- fingertips pass through miniature
- miniature disappears/reappears differently after occlusion
- house changes geometry as it is lifted
- scale changes between reveal and lift
- shadows fail to follow hand/model
- miniature “floats” in foam insert
- side revealed during tilt is hallucinated incorrectly
- package branding/text mutates

## Property-fidelity checklist

All Test 1 rules plus:

- every newly revealed angle has a real reference or geometry anchor
- side/rear architecture does not get invented during lift
- box insert does not conceal a known feature and reveal a different one
- if any roof/interior articulation is later attempted, it must agree with floorplan/3D-tour evidence

## Quality-control checklist

- hand motion looks physically filmed, not generative
- box mechanics are coherent
- miniature has contact weight
- property identity survives every occlusion
- sequence cuts together as a premium ad, not an AI demo
- transition to real property confirms the miniature rather than exposing differences

## Pass/fail

**PASS** only if hand, box mechanics, and Class A property fidelity all survive.  
**FAIL** if the “wow” relies on fast motion hiding deformations.

---

# 13. Experiment economics summary

These are **planning ranges** built from current list prices and conservative retry assumptions. They are not measured production costs yet.

| Prototype | Premium generation spend | Cost-efficient generation target | Human time, first polished prototype | Technical risk |
|---|---:|---:|---:|---|
| **Test 1 — House in Hand** | ~$20-$70 | ~$5-$20 | 3-6 h | Medium-high |
| **Test 2 — Real -> Miniature -> Real** | **~$12-$40** | **~$3-$12** | **2-4 h** | **Medium** |
| **Test 3 — Premium Unboxing** | ~$50-$150+ | ~$15-$40 but not recommended quality target | 6-12 h | High |

### Why inference cost is not the main concern

At current pricing, high-quality stills are cents, and several excellent video engines are around $0.10-$0.20/sec. The economic risk is instead:

**rejected shots × human correction time × client revision cycles**.

The production log must therefore record:

- model/version
- source assets used
- generation parameters
- generations attempted
- generations rejected
- rejection reason
- approved-output cost
- edit time
- total human time

---

# 14. Key technical risks

## Risk 1 — Architectural hallucination

**Highest business risk.** Models optimize for plausible visual output, not legal/factual representation of a listing.

**Mitigation:** geometry anchors, multi-reference still master, no unapproved free orbit, Class A ledger, client sign-off.

## Risk 2 — Occlusion/object permanence

Hands and packaging hide exactly the features we need the model to remember. Runway explicitly documents object-permanence limits in Gen-4.5; the general issue applies across generative video.

**Mitigation:** performance plate, keyframes, short shots, multiple property references, composite local finger edges.

## Risk 3 — Invented unseen angles

A model cannot reliably infer the exact side/rear of a house from one front photo.

**Mitigation:** obtain side/rear/drone views or use 3D assets. Never market a free 360° orbit unless source coverage supports it.

## Risk 4 — “Pretty but wrong” selection bias

Human reviewers may favor the most cinematic output and overlook factual differences.

**Mitigation:** separate creative review from property-fidelity review. Fidelity is a gate, not a weighted aesthetic score.

## Risk 5 — Provider/model volatility

August 2026 introduced Omni GA, Wan 3, Seedance 2.5, H3, and other major changes. Sora is shutting down September 24.

**Mitigation:** save model/version/provider with every experiment; revalidate pricing/API/terms before production; keep pipeline provider-independent.

## Risk 6 — Privacy / pre-market listings

Some provider terms allow submitted media to be used for model/product improvement, especially free tiers and some providers’ API contracts.

**Mitigation:** use paid business/API tiers with acceptable data terms, review confidentiality needs, do not upload embargoed assets casually.

## Risk 7 — Commercial rights to listing media

The realtor may not own the photographer’s copyright or broad derivative rights.

**Mitigation:** explicit permission/intake terms covering the listing photos, video, drone, floorplan, and 3D assets before publication or paid commercial use.

---

# 15. Recommended first experiment

## Start with Test 2 — Real -> Miniature -> Real

### Recommended specific A/B

**Still master:**

- Gemini 3 Pro Image
- FLUX.2 Max or Seedream 5.0 Pro as alternate

**Transition/video A/B:**

- Gemini Omni Flash 1.1
- Wan 3.0

**Optional third control:** H3/Hailuo 3 for the miniature hold because its current cost/quality signal is exceptional.

### First test should answer exactly four questions

1. Can the approved miniature still pass our property-fidelity gate?
2. Can a transition preserve the facade rather than morph it into a similar house?
3. Can a 2-3 second miniature motion shot keep the architecture rigid?
4. How many attempts and human minutes does one client-ready 7-8 second asset require?

If the answer to #1 is no, stop and improve the reference/geometry workflow before testing hands.

If #1 passes but #2/#3 fail, switch video models or reduce motion; do not abandon the concept prematurely.

---

# 16. Specific next actions

1. Respect the user's pause until tonight/tomorrow.
2. Research the most saleable miniature-video format and exact realtor use case before investing in a full production build.
3. Identify realtor segments and current examples using paid listing ads or heavy social promotion; distinguish observed marketing behavior from inferred willingness to pay.
4. Recommend one first format with channel, aspect ratio, duration, hook, CTA, source requirements, and measurable success criterion.
5. Reuse the existing listing reference packet for a controlled Gemini Pro image test if useful; compare it with ChatGPT using the same Class A invariants.
6. Treat the accepted front and aerial results as independent hero assets, not as a coherent 360 model.
7. Once the use case is selected, create the smallest relevant video. **Real -> Miniature -> Real** remains the technical default unless the market/use-case research identifies a better format.
8. Keep animation constrained to an approved view and do not reveal unsupported sides.
9. A/B the selected video tools and log retries, rejection reasons, spend, and human minutes.
10. If the controlled hero-view video passes, run House in Hand using a **real hand performance plate** rather than pure generation.
11. If the earlier tests pass, run Premium Unboxing using real box/hand/proxy footage and Seedance 2.5/Wan/Aleph V2V.
12. Use the San Diego realtor connection only as a later private reaction test, not as demand evidence.
13. Conduct the separate planned research session on **cinematic terminology, lighting, atmosphere, lens language, camera angles, and motion prompting** without mixing it into the property-fidelity work.

---

# 17. What still needs direct validation by us

No amount of web research replaces these project-specific tests.

### Needs direct measurement

- which image model best preserves a real house, not a generic product; ChatGPT has now shown useful single-view results but failed the rear-view continuity test
- whether 6 vs 10 vs 14 reference images improves or harms architectural consistency
- whether Gemini Pro preserves garage/driveway, roof/cupola, and facade identity across views better than ChatGPT
- whether a flat drone reference can materially reduce roof/footprint errors in other models; it was insufficient to correct ChatGPT's backyard generation
- whether actual 3D geometry is required whenever the shot changes viewpoint materially
- Omni vs Wan 3 vs H3 vs Seedance 2.5 on the **same approved miniature still**
- exact hand-interaction retry rate
- whether performance-plate V2V is materially better than pure image-to-video for hands
- whether Matterport/OBJ -> clay render -> image model improves fidelity enough to justify the added labor
- actual approved-output cost
- actual human minutes per shot
- whether a realtor notices or cares about small AI substitutions that a general viewer overlooks
- which realtor use case and video format creates enough value to purchase
- whether agents already using paid ads or heavy social promotion respond more strongly than low-activity agents

---

# 18. Source list — September 2026 snapshot

## Google / Gemini / Veo

1. **Gemini Developer API pricing** — current pricing for Gemini Omni Flash, Gemini image models, and Veo 3.1. Accessed 2026-09-02.  
   https://ai.google.dev/gemini-api/docs/pricing

2. **Gemini Omni Flash model page** — GA model specs, 3-10s, input/output types, resolution. Updated 2026-08-27.  
   https://ai.google.dev/gemini-api/docs/models/gemini-omni-flash

3. **Generate and edit videos with Gemini Omni Flash** — reference/edit/extend workflow, first/last-frame behavior and constraints. Accessed 2026-09-02.  
   https://ai.google.dev/gemini-api/docs/omni

4. **Gemini API release notes** — Omni Flash 1.1 GA 2026-08-27; resolution/interpolation update and preview deprecation.  
   https://ai.google.dev/gemini-api/docs/changelog

5. **Veo 3.1 Gemini API guide** — reference images, first/last frame, duration, resolution, model status. Accessed 2026-09-02.  
   https://ai.google.dev/gemini-api/docs/veo

6. **Gemini image generation guide** — up to 14 references and high-fidelity object/character sublimits; SynthID. Accessed 2026-09-02.  
   https://ai.google.dev/gemini-api/docs/image-generation

7. **Gemini API Additional Terms of Service** — effective 2026-03-23; generated-content ownership and paid/unpaid data-use terms.  
   https://ai.google.dev/gemini-api/terms

## ByteDance Seed / Seedance

8. **One-take Creation, Flexible Referencing: Introducing Seedance 2.5** — ByteDance Seed, 2026-07-31.  
   https://seed.bytedance.com/en/blog/one-take-creation-flexible-referencing-introducing-seedance-2-5

9. **Seedance 2.5 model page** — 30s, reference/edit/camera/white-model capabilities. Accessed 2026-09-02.  
   https://seed.bytedance.com/en/seedance2_5

## MiniMax H3

10. **MiniMax H3: An Open Model Breaking the Boundaries Between Tasks and Modalities** — MiniMax, 2026-07-31.  
    https://www.minimax.io/blog/minimax-h3

11. **MiniMax H3 open-source release / technical specifications** — MiniMax, 2026-08-03.  
    https://www.minimax.io/news/minimax-h3-open-source

## Runway / current hosted model specs

12. **Runway Dev API pricing** — current Wan 3.0, Seedance 2.5, Hailuo 3, Gemini Omni, Veo, Gen-4.5, Aleph and image-model rates. Accessed 2026-09-02.  
    https://docs.dev.runwayml.com/guides/pricing/

13. **Runway Dev API changelog** — Wan 3.0 (2026-08-26), Seedance 2.5, Hailuo 3, current model availability/specs.  
    https://docs.dev.runwayml.com/api-details/api_changelog/

14. **Runway API input parameters** — Wan 3 reference counts, duration/resolution; other model input constraints. Accessed 2026-09-02.  
    https://docs.dev.runwayml.com/assets/inputs/

15. **Creating with Seedance 2.5** — current Runway reference limits/resolution/pricing. Accessed 2026-09-02.  
    https://help.runwayml.com/hc/en-us/articles/53542207042323-Creating-with-Seedance-2-5

16. **Creating with Gen-4.5** — duration, 720p, pricing, prompting and output formats. Accessed 2026-09-02.  
    https://help.runwayml.com/hc/en-us/articles/46974685288467-Creating-with-Gen-4-5

17. **Runway Gen-4.5 research announcement** — includes explicit causal-reasoning and object-permanence limitations. Published 2025-12-01.  
    https://runwayml.com/research/introducing-runway-gen-4.5

18. **Creating with Edit Studio / Aleph 2** — current V2V edit capability. Accessed 2026-09-02.  
    https://help.runwayml.com/hc/en-us/articles/51683104370451-Creating-with-Edit-Studio

19. **Runway usage rights** — commercial-use and ownership statement. Accessed 2026-09-02.  
    https://help.runwayml.com/hc/en-us/articles/18927776141715-Usage-rights

20. **Creating with Gemini Omni Flash — Runway** — current reference slots and edit workflow through Runway. Accessed 2026-09-02.  
    https://help.runwayml.com/hc/en-us/articles/53031657806611-Creating-with-Gemini-Omni-Flash

21. **Creating with Seedream 5.0 Pro — Runway** — current reference/sketch and pricing details. Accessed 2026-09-02.  
    https://help.runwayml.com/hc/en-us/articles/53253654113299-Creating-with-Seedream-5-0-Pro

## Black Forest Labs / FLUX

22. **FLUX.2 overview** — multi-reference limits, role by variant, pricing. Accessed 2026-09-02.  
    https://docs.bfl.ai/flux_2/flux2_overview

23. **FLUX.2 image editing** — multi-reference editing and output controls. Accessed 2026-09-02.  
    https://docs.bfl.ai/flux_2/flux2_image_editing

24. **FLUX API Service Terms** — revised 2026-08-04; input/output license/data-use implications.  
    https://bfl.ai/legal/flux-api-service-terms

25. **BFL Developer Terms** — commercial output use / ownership statement. Revised 2026-08-04.  
    https://bfl.ai/legal/developer-terms-of-service

## Luma

26. **Ray3.14 FAQ** — resolution, duration, Modify support, API limitation and credits. Accessed 2026-09-02.  
    https://lumalabs.ai/learning-hub/ray3-faq

27. **Ray3 Modify user guide** — performance/video-to-video/keyframe workflow. Published 2025-12-12.  
    https://lumalabs.ai/learning-hub/ray3-modify-user-guide

28. **Luma payments/subscriptions** — commercial-use tier distinction. Updated 2026-01-25.  
    https://lumalabs.ai/learning-hub/payments-subscriptions

## Matterport

29. **Matterport 2026 API model docs** — digital twin assets including mesh, textures, photos and floorplans.  
    https://static.matterport.com/api-doc/2026.06.68-main-g3a4e710/reference/graphdoc/model/model.doc.html

30. **MatterPak file exports** — OBJ mesh/textures, point cloud, floorplans. Accessed 2026-09-02.  
    https://matterport.com/en-gb/add-ons/matterpak

## Independent benchmarks / practitioner signals

31. **Artificial Analysis Image-to-Video Leaderboard** — blind preference benchmark; current H3/H3 Max/Omni results. Accessed 2026-09-02.  
    https://artificialanalysis.ai/video/leaderboard/image-to-video

32. **Artificial Analysis Text-to-Video Leaderboard** — current Omni/Wan/H3 results. Accessed 2026-09-02.  
    https://artificialanalysis.ai/video/leaderboard/text-to-video

33. **Artificial Analysis Video Editing Leaderboard** — current Wan 3 / H3 / Omni / Aleph comparison. Accessed 2026-09-02.  
    https://artificialanalysis.ai/video/leaderboard/video-editing

34. **Pencil Community — We Put Gemini Omni Flash To The Test** — practitioner stress test involving difficult hands/physics; published 2026-07-21.  
    https://community.trypencil.com/en/public/blogs/we-put-gemini-omni-flash-to-the-test-2026-07-13

## OpenAI / Sora status

35. **OpenAI Sora help/API deprecation notices** — Sora web/app discontinued and API scheduled for shutdown 2026-09-24. Revalidated during this research.  
    https://help.openai.com/

---

# 19. Bottom line

**Technical feasibility: conditional green light.**

The first real-listing image test has now produced a usable front hero and aerial view while failing rear-view continuity. The project should proceed only with constrained, independently approved views and should not promise unrestricted architectural fidelity, true 360 continuity, or complex miniature manipulation.

The best near-term production philosophy is:

> **Lock facts first. Animate second. Let AI stylize scale and presentation, not the property itself.**

After the current pause, first determine the most saleable realtor use case and format. Unless that research points elsewhere, the first build should remain **Real -> Miniature -> Real** using an approved single-view miniature master and a controlled Omni/Wan A/B. If that passes, move to **House in Hand** with a real performance plate. Only then attempt the full **Premium Listing Unboxing**.

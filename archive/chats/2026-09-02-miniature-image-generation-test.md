# Miniature Image-Generation Test Session

**Date:** 2026-09-02
**Project:** AI Miniature Video Biz Concepts
**Session type:** Hands-on property-fidelity experiment and strategy handoff

## Session objective

Test whether ChatGPT image generation could turn a real listing reference set into a recognizable physical-scale-model treatment, then determine whether the property could remain consistent across front, backyard, and aerial views.

This was a private, non-commercial technical experiment. It did not test a completed video, realtor demand, engagement lift, willingness to pay, or production economics.

## Inputs used

The reference packet included multiple exterior/front images, rear/backyard images, drone views, a roof/cupola detail, and a floorplan. The property was deliberately useful as a stress test because it included:

- distinctive roof and cupola/tower structures
- a detached garage and nontrivial driveway relationship
- a corner-lot presentation
- pergola/trellis details on the facade
- a long, narrow backyard
- rear deck/pergola structures
- drone coverage that exposed the true footprint and orientation

## Generation sequence and observed results

### 1. First front miniature — successful proof of concept

The first front miniature was not exact, but it was close enough to establish that ChatGPT could create a compelling miniature hero image recognizable as the source property.

It retained much of the overall massing, detached-garage relationship, corner-lot feel, roof towers/cupolas, material/color family, landscaping character, and premium architectural-model aesthetic.

The main visible omissions were the pergola/trellis beams above the front door and front windows, plus smaller facade and entry details.

### 2. Second front pass — improved but still imperfect

A correction pass focused on the missing pergola/trellis structures. The second result was closer and improved those details, but it did not become an exact architectural replica.

Decision: close enough to treat as a usable front hero candidate for experimentation, subject to normal side-by-side property QC before any client use.

### 3. First backyard attempt — failed property-fidelity gate

The backyard generation did not preserve the same house across the viewpoint change. It:

- reversed or misoriented the driveway and garage
- failed to honor the relationship established by the front view
- drifted in roof and cupola/tower geometry
- treated the rear as a new interpretation rather than the same property from behind

The unusually long, narrow backyard and awkward rear geometry made this a legitimate stress test, but the errors were material property changes rather than harmless style variation.

### 4. Aerial miniature — close enough

The aerial miniature was judged close enough to be useful. The included road was unnecessary, but that is a presentation issue that can be removed or reframed later rather than a reason to discard the view.

Decision: retain the aerial as an independently approved/useful view, not as proof of a coherent 3D model.

### 5. Backyard retry using the drone view — still failed

The drone image was used as a geometry anchor for another backyard attempt. It provided clear evidence of the true garage position, driveway direction, house/garage relationship, roof footprint, cupola placement, pergola areas, lot shape, and corner geometry.

Despite that added information, the generated backyard still showed the driveway and garage backward, presented front-of-house architecture in the backyard, and remained materially inconsistent with the source property.

Decision: stop pursuing the backyard/360 workflow in ChatGPT for now.

## Durable technical conclusion

### Prior working hypothesis

A strong multi-reference packet might allow a coherent pseudo-360 consisting of approved front, rear, and aerial miniatures.

### New direct evidence

ChatGPT produced useful front and aerial hero images, but did not preserve the property's identity reliably across a difficult front-to-rear viewpoint change—even after drone geometry was supplied.

### Revised conclusion

ChatGPT image generation is currently viable for **single-view hero miniature creation and targeted correction**, but it is not reliable enough for:

- true 360 architectural continuity
- automatic reconstruction of unseen sides
- assumption that one approved angle defines a stable 3D house
- free camera orbits that reveal angles unsupported by actual geometry

Near-term production should use:

- one approved hero view, or
- a small set of independently generated and independently approved views

These assets may be edited or animated with small, constrained motion, but they should not be presented as a geometrically continuous 360 unless a real 3D/digital-twin workflow supplies that continuity.

## What this confirms from the feasibility research

The session directly supports the earlier rule:

> **Lock facts first. Animate second. Stylize scale and presentation, not the property itself.**

It also confirms that a beautiful image can pass a creative review while failing a factual property review. Hero-view success does not predict multi-view success.

The earlier recommendation to consider floorplans, Matterport, CAD, or another digital twin as a geometry anchor remains valid. A flat drone reference alone was informative but insufficient to force cross-view consistency in this test.

## Gemini follow-up

The user has a Google Gemini Plus account and plans to investigate or obtain a Pro plan if useful, including access to its image and video capabilities.

The next model comparison should reuse the same source packet and fidelity checklist so it answers a real question: whether Gemini improves architectural detail and cross-view constraint versus ChatGPT, not merely whether it produces a prettier image.

Plan names, promotional pricing, included models, and usage limits are time-sensitive and were not verified in this session. Revalidate them before purchase or testing.

## Strategy shift: from technical novelty to realtor value

The session ended with a more important commercial question:

> What miniature-video format is most saleable to a realtor, and what exact job would the realtor use it to perform?

The leading hypothesis is that the asset is more valuable as **scroll-stopping paid-ad or social creative** than as generic listing media. Agents who already buy attention or publish frequently have an existing distribution mechanism and a reason to seek differentiated creative. Agents who rarely advertise or post may see little value even if the video is impressive.

Promising segments to research include:

- agents running paid listing or lead-generation ads
- high-frequency Instagram/Reels/TikTok/Shorts users
- teams or brokerages with repeatable listing-content operations
- luxury/upper-end agents investing in differentiated marketing

This is a business hypothesis, not demand evidence.

## Next research assignment

On resumption:

1. Determine the most saleable video format and exact realtor use case.
2. Compare paid-ad creative, organic listing launch, retargeting, open-house promotion, seller-pitch differentiation, and generic listing-media use.
3. Identify current realtor segments and concrete examples using paid ads or heavy social listing promotion.
4. Define the first offer/test around observed distribution behavior rather than around novelty alone.
5. Specify channel, aspect ratio, duration, hook, CTA, source assets, and success metric for the recommended format.
6. Then run the smallest relevant video prototype using an approved hero view.

The prior **Real -> Miniature -> Real** recommendation remains the best technical default, but it is not yet proven to be the most saleable format.

## Pause and handoff

The user intends to shelve the project until tonight/tomorrow while working on another project. No reminder or scheduled automation was requested.

## Files updated from this session

- `PROJECT_STATE.md`
- `HANDOFF.md`
- `research/2026-09-production-stack-feasibility.md`
- `archive/chats/2026-09-02-miniature-image-generation-test.md` (this file)

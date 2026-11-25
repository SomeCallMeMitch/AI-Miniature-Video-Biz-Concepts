# Animation planning, contact and delivery review

November 25, 2026. General production lessons for deterministic 3D product films. This record contains no private client media or private asset links. It supplements the real-estate fidelity work and the separate Blender tote pilot; those remain separate experiments.

## What transfers from design skills

Reviewed source snapshot: [Charles Skills, f019faf3](https://github.com/LemonFace0309/charles-skills/tree/f019faf3d8900734b283df0786b1a221cccf8b81). These are applicability notes from an earlier review, not a new verification of the upstream repository. Follow source credits and license requirements before copying third-party implementations.

| Skill | Method | Use in our film workflow |
| --- | --- | --- |
| UX Animation | Purpose, attention, timing, arcs and easing | Plan named action beats and contact poses before implementation. UI duration recipes do not prescribe character timing. |
| Polish | Inspect actual output, adjacent frames and contact sheets | Find pops, intersections, unsupported objects and dead motion; repeat after changes. Frame differences flag candidates, not automatic failures. |
| Explainers Assets | Visible state changes, phone-size and muted checks | Check whether the product benefit and sequence read without narration. Its narrated UI tooling is optional. |
| Unreasonable Craft | Compare directions, define a visual system, critique rendered evidence | Compare a small number of actual scene stills before committing to a full render. |
| Unslop | Clarify subject, remove clutter, simplify type and copy | Keep titles readable while preserving attention on hands, product and payoff. |
| Accent Heroes | One dominant subject, controlled accent and reference-based stills | Optional poster/thumbnail work; does not solve animation continuity. |
| Store Screenshots | Hook and continuity across static panels | Useful for carousels, little direct value for a 3D movie. |
| Claude Editing | Talking-head selection, narration-led captions, audio and overlays | Revisit for narrated or on-camera variants; not a rigging solution. |
| Arcade Assets | Beat-sheet-driven sprite action | Borrow beat planning; its pixel-art stack does not improve a rounded 3D film. |
| Storage Cleanup | OS storage inventory and housekeeping | No direct animation benefit. |

## Contact is a staging problem before it is a rendering problem

More pixels or a stronger image model can improve an individual look-development still. They do not repair deterministic joint paths, hand anchors or missing character entrances. A high-quality still also does not establish temporally coherent motion. Retain the rigged scene when exact product mechanics and repeated camera coverage matter.

1. Block the feet, hips, shoulders, prop, work surface, doorways and open-hinge sweep in a simple overhead plan. If a reach is too long, reposition the character or product.
2. Name approach, reach, grip, lift, rim crossing, lower, release and withdrawal. Store grips in prop-local coordinates and transform them into the rig’s working space.
3. Choose elbow bend direction. Check upper arms and sleeves as well as wrists against the product, furniture, heads, hair and the other character. Endpoint tests alone miss crossings.
4. Lift above a container rim before crossing it. Withdraw through its opening before moving sideways. A hand operating a lid follows a real reachable hinge-edge anchor.
5. Preserve support throughout transfers. Show who takes the weight before the first person releases. Give any strap or latch a visible cause and a shared sound event.
6. Show every visible character entrance and exit across cuts. Door or vehicle occlusion must explain disappearance. Review both sides of every edit.

## Gates before a full render

- Render three actual scene stills: environment/vehicle, simultaneous interaction, and loaded/secured product. A separate concept illustration is a style reference, not proof the scene can deliver it.
- Sample swept limb capsules against conservative, correctly transformed obstacles, including moving hinge panels. Report time, body segment, obstacle and reach error. Approximate colliders reduce risk; they cannot certify fingers or all mesh contact.
- Inspect side and three-quarter views, dense frame strips around contact, then a short encoded motion test at the target resolution.
- Play the complete final encode in a real browser, with sound and muted at likely mobile size. Inspect edited transitions after assembly; an isolated successful test does not prove the whole film.
- Check duration, dimensions, frame count, audio channels and full decode. Retain versioned files, rejected previews, manifests and explicit remaining issues.

1080p is a reasonable delivery target when approved. Spend effort first on staging, geometry, lighting, believable materials and contact. Higher resolution is a finishing choice, not the quality gate.

## Continuing work

Use the [contact-review skill](../.agents/skills/animation-contact-review/SKILL.md) for a new scene. Keep a shot/action ledger and reject a shot with visible intersections even if its lighting is attractive. Do not treat earlier model/provider recommendations in this knowledge base as current purchasing advice without rechecking them.

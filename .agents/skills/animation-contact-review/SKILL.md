---
name: animation-contact-review
description: Plan and verify hand-to-prop contact, character clearance, hinged mechanisms and visible entrances/exits in deterministic 3D product films.
---

# Animation contact review

Use for packing, carries, handoffs, lids, loading and nesting. Establish contact and support before polishing the look.

## Plan

- Draw standing space, supporting surfaces, the prop opening, doorway and hinge sweep.
- Specify approach, grip, lift, crossing, lower, release and withdrawal. Define local grip anchors on the actual prop.
- Keep targets within reach; move feet or torso instead of silently clamping an unreachable IK target. Set elbow bend direction deliberately.
- Keep rigid product geometry rigid. Move hinged parts about their real pivot. Make latch sounds use the same timeline event as visible closure.

## Check

- Sweep upper-arm and forearm capsules against container walls/rims, moving lids, furniture, both characters’ heads/hair and other limbs where relevant.
- Track reach error separately from collision clearance. Permit intended fingertip contact without allowing sleeve penetration.
- Sample the whole interaction, then refine samples around minima. Conservative shapes are diagnostics; inspect rendered geometry too.
- Inspect approach, peak lift, rim crossing, latch and withdrawal from the audience camera plus a side or three-quarter view.
- During a transfer, identify what supports the object at every moment. Do not release before the next support takes over.
- Review every entry and exit across edits. People should walk into or out of an occluder; camera cuts must preserve an understandable route.

## Deliver

Inspect actual scene stills, a short motion test and the entire assembled encode at the agreed resolution. Play with sound and muted at mobile size. Decode the final file and verify stream metadata. Save frames, source version, failures, limitations and hashes. Never claim sampled proxy collisions certify every mesh intersection.

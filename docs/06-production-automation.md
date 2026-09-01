# Production and Automation

## Core production reality

The software layer may be inexpensive or open source, but **watchable video is not free**.

The biggest technical/business question is not whether AI can output an MP4. It is whether the system can create a convincing, useful miniature treatment at a cost that leaves room for profit.

## Production tiers considered

### Cheap prototype tier

Approximate monthly tooling: **$30-$100**

Possible stack:

- LLM for concepts/prompts/scripts
- inexpensive image generation
- low-cost or free TTS when needed
- FFmpeg / templated assembly
- limited generative-video seconds

Best for testing concepts, not for assuming professional client quality.

### Practical early commercial tier

Approximate monthly tooling: **$100-$300**

Possible additions:

- higher-quality video generation
- better voice
- more retries
- consistent branding
- stronger image generation/editing
- occasional stock/assets

### High-generation tier

Can easily reach **$500-$1,500+/month** or much more if every video uses many expensive generative-video clips and retries.

Do not start here.

## Cost discipline

Before product-market fit:

- set a hard cost ceiling per prototype/video
- log every generation and retry
- record usable-seconds-per-dollar
- separate model inference cost from human editing time
- prefer short hero moments where generative video adds the most value
- use existing listing/product assets wherever possible

## Technical challenge: subject fidelity

For products:

- logo/branding drift
- wrong button/port placement
- altered proportions
- inconsistent accessories

For real estate:

- roof/window changes
- invented landscaping
- incorrect room geometry
- changed finishes
- altered pool/lot shape
- inconsistent views between shots

The first production experiment should explicitly score fidelity rather than only aesthetic quality.

## Useful automation architecture from prior research

An open-source project, `darkzOGx/youtube-automation-agent`, was examined as an architectural reference.

Useful patterns:

1. **Persistent objective/guardrails**
2. **Specialized pipeline stages**
3. **Human approval gates**
4. **Analytics feedback loop**
5. **Comment/audience mining**
6. **Provider-independent model adapters**
7. **Production-readiness checks**
8. **Fail-closed publishing behavior**
9. **Separate real output from simulated/fallback output**

## Proposed future system for this project

Do not build this until validation succeeds.

Potential service pipeline:

1. **Lead/listing discovery**
2. **Asset ingestion**
3. **Property/product understanding**
4. **Creative concept selection**
5. **Miniature still generation/editing**
6. **Video animation/generation**
7. **Fidelity QC**
8. **Brand/CTA assembly**
9. **Watermarked preview generation**
10. **Human approval**
11. **Client delivery / publication**
12. **Performance analytics**
13. **Learning loop**

## Human-in-the-loop principle

The best target is not "zero humans."

The target is:

> AI does the repetitive work and presents high-leverage decisions to a human.

Human gates should remain around:

- factual/property accuracy
- final quality
- legal/rights concerns
- public publishing
- client-facing claims
- strategy changes based on analytics

## Metrics to log from day one

For each prototype:

- model/provider
- prompt version
- source assets used
- generations attempted
- generation cost
- human edit minutes
- total cost
- fidelity score
- realism score
- hook strength score
- final usable seconds
- defects/hallucinations
- client/viewer response if tested

This data will tell us whether automation is improving economics or merely increasing output volume.

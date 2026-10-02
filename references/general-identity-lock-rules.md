# General Identity Lock Rules

## Identity Review Checklist (must pass all)

Before approving any image:

### Face & Head
- [ ] Same recognizable face as Master Reference
- [ ] Same approximate age
- [ ] Same hairstyle and hair color
- [ ] Same beard / facial hair style and density (if applicable)
- [ ] Same eye color and shape
- [ ] Same skin tone and texture quality
- [ ] Realistic facial asymmetry preserved
- [ ] No sudden change in nose, jawline or cheekbones

### Body & Proportions
- [ ] Same approximate height impression and body type
- [ ] Same shoulder width and overall build
- [ ] Normal human proportions (no elongation or shortening)
- [ ] Clothing fits the same body realistically

### Overall
- [ ] Character is immediately recognizable as the same person
- [ ] No “new person” feeling
- [ ] Lighting and shadows do not hide identity-critical features

**Fail any single item → Reject the image.**

## Stable Identity Block Template

Keep a fixed block like this and reuse it:

```
Character ID: <ID>
[exact age], [ethnicity/appearance], [skin tone], [eye color],
[hair description], [beard description if any],
[height], [body type], realistic skin texture, natural facial asymmetry,
same person as the provided master reference image.
```

Never rewrite the core description from memory for each new prompt.

## Negative Prompt Lock (recommended baseline)

```
different person, face morph, identity drift, changed face, new face,
younger, older, different hair, different beard, different skin tone,
model-like face, perfect symmetry, beauty filter, plastic skin,
extra limbs, deformed hands, distorted proportions
```

Adjust only for tool-specific needs; never remove identity-protection terms.

## Naming Convention

```
<CHARACTER-ID>_<category>_<YYYYMMDD>_v<NN>.<ext>
```

Examples:
- FX-TRADER-01_master_reference_20260928_v01.jpg
- FX-TRADER-01_full_body_20261001_v01.png
- FX-TRADER-01_lifestyle_cafe_20261002_v03.jpg

## Change Control

Any intentional change to core identity requires:
1. Written reason
2. Update to the visual identity document
3. New Master Reference version
4. Review of previously approved images if the change is significant
5. Version bump and date record

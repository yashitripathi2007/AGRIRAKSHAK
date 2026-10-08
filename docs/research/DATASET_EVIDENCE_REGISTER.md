# Target-Crop Dataset Evidence Register

**Task:** Task 7 — Y1 Target-crop feasibility and dataset evidence
**Owner:** Yashi (@yashitripathi2007)
**Issue:** #10
**Scope:** Sehore, Madhya Pradesh — soybean, wheat, gram/chickpea
**Status:** Evidence screening; not an approved training-data selection

## Purpose

This register records candidate image datasets relevant to the Task 7 target crops. It is a research/evidence handoff, not a dataset approval, project metric, agronomic recommendation, or model-validation result.

The existing `ml/src/agrirakshak_ml/prepare_plantvillage.py` baseline currently covers bell pepper, potato and tomato. These target-crop candidates therefore do **not** imply that soybean, wheat or chickpea are currently supported by the AGRIRAKSHAK model.

## Evidence summary

| Crop | Candidate dataset | Version/source | Reported coverage | Conditions / geography | License | Current assessment |
|---|---|---|---|---|---|---|
| Soybean | SoyNet: Indian Soybean Image Dataset | Mendeley Data V3, DOI `10.17632/w2r855hpx8.3` | 29,000+ images; healthy and diseased | Field images from Jabalpur, Madhya Pradesh; natural lighting/backgrounds; Nikon L810 and Motorola G40 | CC BY 4.0 | **Strong candidate for further audit.** Geographically relevant to MP, but exact per-class counts and disease-label definitions still require dataset-level inspection. |
| Soybean | Soybean Healthy and Diseased Images Dataset | Mendeley Data V1, DOI `10.17632/w8vm4mm8t4.1` | Healthy and diseased folders; exact counts not recorded here | Mobile-phone images from farms in Kolhapur, Maharashtra | CC BY 4.0 | **Useful supplementary field evidence.** Two broad folders are insufficient by themselves for a detailed disease-class contract. |
| Wheat | Wheat disease images (small dataset) | Zenodo V1, DOI `10.5281/zenodo.7573133` | 999 images; yellow rust, brown rust, septoria, mildew and healthy; full dataset reported as 19,172 images | Realistic growth conditions; source page describes a small subset of the full dataset | License not exposed on the retrieved Zenodo record | **Potential candidate, licensing unresolved.** Do not use for project training until permitted use is independently verified. |
| Chickpea | Seven Major Pulses Image Dataset | Mendeley Data V1, DOI `10.17632/skd9w9g5jm.1` | Approximately 17,500 images across 11 classes; includes chickpea/chola | Natural field conditions in Bangladesh; multiple growth stages, angles and distances | CC BY 4.0 | **Potential supplementary candidate.** Field conditions and expert labeling are useful, but Bangladesh geography and class structure create a significant transferability gap for Sehore. |

## Dataset-level evidence

### 1. Soybean — SoyNet V3

**Source:** Rajput et al., Mendeley Data, V3, DOI `10.17632/w2r855hpx8.3`.

The source reports 29,000+ soybean images containing healthy and diseased material. It states that images were captured directly in soybean fields in Jabalpur under natural lighting and varying backgrounds, using a Nikon L810 digital camera and Motorola G40 mobile phone. The dataset is listed under CC BY 4.0.

**Relevant strengths**
- Indian field imagery.
- Jabalpur, Madhya Pradesh, gives geographic relevance to the target region.
- Natural backgrounds and lighting are more representative of deployment than controlled-background imagery.
- Includes both digital-camera and mobile-phone capture.

**Still requiring verification**
- Exact image count per health/disease class.
- Exact disease categories and their label definitions.
- Whether multiple images of the same plant/leaf occur and how source grouping should be performed.
- Whether any expert/pathologist review was used for labels.
- Whether the V3 preprocessing folder should be excluded in favor of original images.
- Whether duplicate or near-duplicate images exist between raw and processed subsets.
- Whether metadata identifies collection sites/fields sufficiently for grouped splitting.

**Y1 assessment:** High-priority candidate for deeper audit, but not yet approved for model training.

### 2. Soybean — Healthy and Diseased Images Dataset

**Source:** Khandagale et al., Mendeley Data, V1, DOI `10.17632/w8vm4mm8t4.1`.

The source describes unprocessed soybean leaf images separated into Healthy and Diseased folders. Images were captured with mobile-phone cameras on farms in Kolhapur district, Maharashtra, India. The dataset is listed under CC BY 4.0.

**Relevant strengths**
- Real farm imagery.
- Mobile-phone capture.
- Indian agricultural context.
- Explicit reuse license.

**Limitations**
- The source exposes only broad Healthy/Diseased organization in the reviewed metadata.
- Exact counts and disease subclasses are not recorded in this register until inspected from the downloadable data.
- Maharashtra collection sites do not establish Sehore-specific performance.
- Expert-label review is not established by the reviewed metadata.

**Y1 assessment:** Useful supplementary field dataset; insufficient by itself for a detailed target-crop disease taxonomy.

### 3. Wheat — Wheat disease images (small dataset)

**Source:** Long et al., Zenodo, V1, DOI `10.5281/zenodo.7573133`.

The source reports 999 wheat disease images covering yellow rust, brown rust, septoria, mildew and healthy leaves, taken in realistic growth conditions. It describes this as a small subset of a full dataset containing 19,172 images across the same five categories.

**Relevant strengths**
- Five explicit categories including healthy leaves.
- Realistic growth conditions.
- Dataset has a DOI and identifiable authorship.

**Limitations**
- The reviewed Zenodo metadata does not expose a usable license value.
- The full 19,172-image dataset is described as available on request, so its access conditions require separate verification.
- Geographic/device details and expert-label review are not established in this screening.
- No Sehore/MP-specific evidence is established.

**Y1 assessment:** Candidate for investigation, but **not cleared for reuse until licensing and permitted-use conditions are verified**.

### 4. Chickpea — Seven Major Pulses Image Dataset

**Source:** Rahman et al., Mendeley Data, V1, DOI `10.17632/skd9w9g5jm.1`.

The source describes approximately 17,500 images across 11 classes covering seven pulse species, including chickpea/chola. Images were collected from pulse-cultivation fields in Bangladesh during the 2023–2024 growing season. The source reports natural field conditions, multiple growth stages and viewpoints, and manual classification/labeling by agricultural experts. The dataset is listed under CC BY 4.0.

**Relevant strengths**
- Includes chickpea.
- Natural field imagery rather than only controlled backgrounds.
- Multiple growth stages and viewpoints.
- Source reports agricultural-expert labeling.
- CC BY 4.0 reuse license.

**Limitations**
- Collection geography is Bangladesh, not Madhya Pradesh.
- The reviewed metadata does not establish a Sehore-specific disease distribution.
- The 11-class taxonomy covers seven pulse species, so chickpea-specific sample counts and disease labels must be extracted before use.
- Cross-species and cross-region transfer cannot be assumed.

**Y1 assessment:** Potential supplementary source for chickpea research, but current evidence is insufficient to establish Sehore-targeted coverage.

## Crop-level feasibility status

### Soybean

**Evidence status: promising, not yet model-ready.**

SoyNet provides the strongest geographic match found in this screening because its source describes field collection in Jabalpur, Madhya Pradesh. However, exact class counts, label definitions, duplicate structure, and label-review evidence still need dataset-level inspection.

### Wheat

**Evidence status: candidate found, licensing gap remains.**

A five-class wheat dataset exists with realistic-condition images, but the reviewed source does not expose a license. It must not be treated as cleared training data until reuse permission is established.

### Gram / chickpea

**Evidence status: partial coverage, significant regional gap.**

A CC BY 4.0 field-image dataset with chickpea exists, but it was collected in Bangladesh. Chickpea-specific counts, disease classes and regional transferability need further investigation. No Sehore-specific image dataset has been established by this screening.

## Field versus controlled-background evidence

The target-crop candidates above are preferable to relying on PlantVillage alone for field-generalization claims because their source descriptions include natural/realistic field conditions.

However, source descriptions do **not** establish that these datasets are representative of:
- Sehore farms;
- local cultivars;
- local disease prevalence;
- local weather/lighting;
- the user's eventual mobile devices;
- the exact scanner framing;
- the final AGRIRAKSHAK preprocessing pipeline.

Therefore, dataset existence must not be converted into a project field-accuracy claim.

## Label and expert-review gaps

The following are not yet established for all candidate datasets:

1. Per-class image counts.
2. Whether labels were assigned or verified by plant pathologists/agronomists.
3. Whether disease severity is represented.
4. Whether healthy and diseased images can be mapped to a common project label taxonomy.
5. Whether multiple images originate from the same plant, leaf, plot or capture session.
6. Whether duplicate/near-duplicate images occur.
7. Whether image preprocessing creates derived copies that could leak across splits.
8. Whether metadata permits source/group-aware train/validation/test splitting.

These must be resolved before training.

## License and permitted-use register

| Dataset | License evidence | Training-use status |
|---|---|---|
| SoyNet V3 | CC BY 4.0 reported by Mendeley | License-compatible candidate; attribution and dataset terms still need to be preserved |
| Soybean Healthy/Diseased | CC BY 4.0 reported by Mendeley | License-compatible candidate; attribution and dataset terms still need to be preserved |
| Wheat disease images | License value not exposed in reviewed Zenodo metadata | **Unresolved — do not treat as cleared training data** |
| Seven Major Pulses | CC BY 4.0 reported by Mendeley | License-compatible candidate; attribution and dataset terms still need to be preserved |

## Current Y1 gaps / next actions

1. Inspect downloadable metadata/files for the highest-priority soybean candidate (SoyNet V3).
2. Record actual per-class counts rather than relying on approximate source-level totals.
3. Determine whether leaf/plant/source identifiers allow grouped splitting.
4. Verify exact disease-label definitions and any expert-review evidence.
5. Verify wheat licensing before considering it for training.
6. Extract chickpea-specific counts/classes from the pulse dataset.
7. Search specifically for additional India/MP/central-India wheat and chickpea field datasets with clear reuse terms.
8. Do **not** modify `prepare_plantvillage.py` until the target-crop label/preprocessing contract is agreed with Arindam on issue #10.
9. Do **not** claim target-crop model support, accuracy, field reliability, or agronomic validity from this register.

## Sources

- Soybean Healthy and Diseased Images Dataset — Mendeley Data, V1: `https://data.mendeley.com/datasets/w8vm4mm8t4/1`
- SoyNet — Mendeley Data, V3: `https://data.mendeley.com/datasets/w2r855hpx8/3`
- Wheat disease images (small dataset) — Zenodo, V1: `https://zenodo.org/records/7573133`
- An Image Dataset of Seven Major Pulses Grown in Bangladesh for Smart Agriculture Applications — Mendeley Data, V1: `https://data.mendeley.com/datasets/skd9w9g5jm/1`

**Evidence date:** 2026-10-09
**Important:** This register records source-level evidence and unresolved gaps. It does not constitute project validation, expert approval, or a final dataset-selection decision.

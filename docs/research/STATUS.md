# Supporting research integration status

Owner-authorized integration of Yashi’s PR #14 on the Task 10 branch. Original commit 1fa6799f8565359d217bffd9699b212f502fc848 is cherry-picked with her authorship and source reference intact. The bibliography, review and claims register are research context, not runtime catalog advice or executed model evaluation.

Owner review corrections: current inference is consented server-side, browser inference remains pending; no reviewed runtime content is claimed. Noyan’s initials corrected to M. A. and evidence labelled preprint. Ramcharan 2019’s reported F1 decrease is 32% for real-world images and 39% for video, rather than attributing the image result to video. These points were checked against primary arXiv/Frontiers sources on October 9, 2026. Original reported verification/access caveats remain attributed to the submission; all sixteen sources were not independently reverified by owner integration. IEEE source [8] remained inaccessible in this review; its existing access caveat is preserved.

Validation: UTF-8 and local document links checked; original files and attribution preserved; runtime checks are recorded in CORE_STATUS.md. Next Task 7 work remains Yashi’s registered research/Colab/training/evaluation/export brief and branch. No accuracy, calibration, agronomy review or target-crop model coverage is established by this delivery.

## Task 7 Y1 — target-crop dataset evidence

A first source-level screening has been recorded in `DATASET_EVIDENCE_REGISTER.md` for the owner-selected Sehore, Madhya Pradesh scope: soybean, wheat and gram/chickpea.

Current evidence:
- Soybean: promising field-data candidates identified, including SoyNet V3 from Jabalpur, Madhya Pradesh; exact per-class counts, label definitions, grouping metadata and label-review evidence remain to be audited.
- Wheat: a five-class realistic-condition candidate was identified, but licensing/permitted-use evidence remains unresolved.
- Gram/chickpea: a CC BY 4.0 field-image candidate was identified from Bangladesh; chickpea-specific counts/classes and regional transferability remain unresolved.
- No target-crop model support, accuracy, field reliability or agronomic validity is established by this screening.

Next Y1 actions:
1. Inspect candidate dataset metadata/files and record actual class counts.
2. Verify grouping/duplicate information and label-review evidence.
3. Resolve wheat licensing before any training use.
4. Extract chickpea-specific coverage.
5. Continue searching for India/MP/central-India wheat and chickpea field datasets with clear reuse terms.
6. Do not change the PlantVillage baseline until the target-crop label/preprocessing contract is agreed with Arindam on issue #10.

Y1 remains **in progress**; this evidence register is a research handoff, not dataset approval or model validation.

### SoyNet V2 local audit - October 9, 2026

A local inspection of the downloaded SoyNet V2 archive found 1,363 raw image files: 1,056 in the camera disease folder, 138 in the camera healthy folder, and 169 in an unlabelled mobile-click folder. All 1,363 images were readable in the initial image-integrity scan.

Exact SHA-256 comparison of the camera disease and healthy folders found eight cross-label duplicate groups (16 file entries). These are unresolved label conflicts; exclude all members of those groups from any candidate training manifest until the source labels are reviewed. Four healthy-folder images are 160x120 pixels and require visual/source inspection before inclusion.

A perceptual-hash comparison found that all 7,975 processed/grayscale images had a nearest raw-image hash distance of 0-2. This indicates substantial visual overlap, but perceptual hashes alone do not establish exact provenance. Keep processed and grayscale variants out of the initial candidate training set pending a stronger source-to-derivative audit. Mobile-click images remain excluded until their labels are established.

These findings describe a local dataset audit only. They do not establish expert-verified labels, an approved training dataset, model performance, field reliability, or agronomic validity. Within-class duplicates, grouping by original leaf/source, dataset terms, and label definitions still require review before a defensible split and training run.

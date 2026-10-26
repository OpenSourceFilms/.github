# Public repository licensing and provenance register

**Audit snapshot:** 26 October 2026. This is publication hygiene, not an
opinion that every repository or downstream film use is legally cleared.
The linked repository's own `LICENSE` and upstream rights govern each
specific file and dependency. **OSF can license only rights it owns or has
permission to sublicense.** A GitHub repo being public does not itself
grant a general open-source licence:
[GitHub licensing guidance](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/licensing-a-repository).

## Current public repository status

A root MIT file applies only to **OSF-owned original portions**, not automatically
to third-party code, pretrained weights, model checkpoints, upstream workflow
graphs, imagery, data, or any other material with separate rights.

| Public repository | Current root reuse notice | Specific follow-up or boundary |
|---|---|---|
| [opensourcefilms-tools](https://github.com/OpenSourceFilms/opensourcefilms-tools) | MIT | Historical archive, disabled unsafe startup; underlying dependency rights must be checked separately. |
| [opensourcefilms-comfyui-workflows](https://github.com/OpenSourceFilms/opensourcefilms-comfyui-workflows) | MIT for OSF originals | SAM 3 has a **custom SAM License**, not MIT/Apache/GPL; VideoMaMa, BiM-VFI and EffectErase workflows include noncommercial/research-limited dependencies. See the per-workflow manifest. |
| [opensourcefilms-baton](https://github.com/OpenSourceFilms/opensourcefilms-baton) | MIT | OSF continuity code, version-specific hook integration. |
| [opensourcefilms-erf](https://github.com/OpenSourceFilms/opensourcefilms-erf) | MIT for OSF originals | Code and pretrained identity/diarization models can have different terms. Some weights are noncommercial or unverified. |
| [opensourcefilms-platelock](https://github.com/OpenSourceFilms/opensourcefilms-platelock) | MIT for OSF originals | CoTracker3 is CC-BY-NC; SAM 3 has a custom agreement; other method/weight terms vary. |
| [opensourcefilms-bikematch](https://github.com/OpenSourceFilms/opensourcefilms-bikematch) | MIT | Early-development application code; dependencies and data rights are separate. |
| [opensourcefilms-three-camera-hdr](https://github.com/OpenSourceFilms/opensourcefilms-three-camera-hdr) | MIT | Concept documentation, no tested camera software/hardware release. |
| [opensourcefilms-orbitturn](https://github.com/OpenSourceFilms/opensourcefilms-orbitturn) | MIT for OSF originals | Several external models' weight terms remain explicitly unverified in THIRD_PARTY_LICENSES.md. |
| [opensourcefilms-motiongen-tests](https://github.com/OpenSourceFilms/opensourcefilms-motiongen-tests) | MIT for OSF originals and any rights OSF holds in synthetic sample | One generated Kimodo numeric sample, no model checkpoints; upstream GENMO and STMC have noncommercial restrictions. |
| [opensourcefilms-runpod-orchestration](https://github.com/OpenSourceFilms/opensourcefilms-runpod-orchestration) | MIT | Public planner/tools, not a grant of rights to RunPod or external services. |
| [opensourcefilms-deepseek-agent](https://github.com/OpenSourceFilms/opensourcefilms-deepseek-agent) | MIT | Retired helper; users obtain their own provider licences and access. |
| [opensourcefilms-video-edit-method-bench](https://github.com/OpenSourceFilms/opensourcefilms-video-edit-method-bench) | MIT for OSF originals; upstream Apache-2.0 portions of adapted graphs retain their terms | Edit Anything and FlexAM workflow modifications have [provenance notices](https://github.com/OpenSourceFilms/opensourcefilms-video-edit-method-bench/blob/main/workflows/UPSTREAM_NOTICES.md); Ditto's NC-SA graph is excluded. LTX model terms are conditional. |
| [opensourcefilms-vsr-stab4](https://github.com/OpenSourceFilms/opensourcefilms-vsr-stab4) | MIT for OSF postprocessor | SeedVR2, ComfyUI integrations, model weights and footage are external, not relicensed. |
| [opensourcefilms-basics-auto](https://github.com/OpenSourceFilms/opensourcefilms-basics-auto) | MIT for OSF core | Published CPU quality-control extract, not the upstream segmentation/matting models. |
| [opensourcefilms-bts-ingest](https://github.com/OpenSourceFilms/opensourcefilms-bts-ingest) | MIT for OSF core | Published offline registry, not live uploader, B2 assets or contributor footage. |
| [osf-viewer](https://github.com/OpenSourceFilms/osf-viewer) | **No general reuse licence granted yet** | Ownership, attribution and licence decision in [issue #1](https://github.com/OpenSourceFilms/osf-viewer/issues/1). Public/source-visible is not automatically MIT. |
| [osf-backup](https://github.com/OpenSourceFilms/osf-backup) | **No general reuse licence granted yet** | Historical implementation. Ownership, attribution and licence decision in [issue #1](https://github.com/OpenSourceFilms/osf-backup/issues/1). |
| [.github](https://github.com/OpenSourceFilms/.github) | No root licence; organisation documentation only | Do not infer a universal licence for organisational identity, logos or copied documentation. |

**Inventory:** 18 public repositories, 15 with root MIT files, two with no
general reuse licence pending owner review, and one organisation-profile
documentation repository.

## Review findings and limits

- **File inventory:** Complete GitHub recursive trees for the 17 public code
  repositories were inspected for common model-weight and media file
  extensions. No `.safetensors`, `.ckpt`, `.pth`, `.pt` or `.onnx` model
  files were identified. One generated Kimodo `.npz` sample and a small WAV
  file in the older tools archive were identified. This filename-based
  inspection does **not** establish copyright provenance, inspect historical
  Git blobs, or guarantee there are no embedded assets in text or unrecognised
  formats.
- **Known attribution corrections:** Meta's SAM 3 custom terms are disclosed
  without calling them an OSI-approved permissive licence; adapted upstream
  Apache workflows retain author/source notices and a full licence copy.
- **Open rights checks:** Public authorship, contractor/contributor assignments,
  imported code and all dependency licences have **not** been independently
  verified file-by-file. A root MIT file is an OSF permission claim, not proof
  of chain of title. Resolve third-party contributors' rights before assuming
  OSF can relicense their expression.
- **Model use versus model redistribution:** Separate licences may govern code,
  weights, model outputs, datasets and underlying media. Not bundling weights
  reduces redistribution risk; it does not automatically clear every use of
  the model.
- **NonCommercial is about the specific use:** Creative Commons states that
  a nonprofit organisation can still make a commercial use; being non-profit
  does not itself waive NC terms. See the
  [Creative Commons FAQ](https://creativecommons.org/faq/).
- **Commercial-status labels:** A label such as `commercial-compatible`
  records an assessment of known dependencies, not legal clearance. Custom
  model agreements, source-release obligations, usage restrictions and
  changes upstream must be reviewed for the exact deployment.

## Publication acceptance checklist

Before publishing or materially updating a repository:

1. Identify original OSF-authored files versus copied/adapted upstream work;
   verify authority to grant the selected licence for each original component.
2. Retain upstream copyright, licence and required NOTICE texts where
   applicable; mark material modifications and credit original researchers.
3. Independently review source-code and model-weight terms, plus downstream
   assets/datasets and output-use requirements. Record upstream URL, exact
   release or commit, check date and uncertainty.
4. Exclude unlicensed model weights, protected footage, private enrolment
   records, user data and other material without redistribution permission.
5. Match root licences, READMEs, dependency manifests, workflow sidecars and
   actual included files. Avoid blanket claims like *all dependencies are
   permissive* when custom model licences are involved.
6. Run safe, isolated CI and check published paths and GitHub Actions;
   do not mistake an offline test for operational or rights clearance.
7. Publish any unresolved rights question explicitly as a tracked issue.
   **Do not silently add a licence or claim ownership on behalf of others.**

This snapshot will need review when dependencies or the public repository
inventory change. The source licence texts and written authorisations,
not this register, determine permissions.

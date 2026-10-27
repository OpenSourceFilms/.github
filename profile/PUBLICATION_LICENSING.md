# Public repository licensing and provenance register

**Audit snapshot:** 28 October 2026 (with earlier dated CI checkpoints preserved below). This is publication hygiene, not an
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
| [opensourcefilms-orbitturn](https://github.com/OpenSourceFilms/opensourcefilms-orbitturn) | MIT for OSF originals | **MiniMax H3 custom licence excludes the US, EU, UK and South Korea from its standard territory, including restrictions on use/display of generated Outputs**; international film exhibition/distribution may require separate permission. LTX 2.x has conditional commercial terms; Bernini and other weights remain unverified. See THIRD_PARTY_LICENSES.md. |
| [opensourcefilms-motiongen-tests](https://github.com/OpenSourceFilms/opensourcefilms-motiongen-tests) | MIT for OSF originals and any rights OSF holds in synthetic sample | One generated Kimodo numeric sample, no model checkpoints; upstream GENMO and STMC have noncommercial restrictions. |
| [opensourcefilms-runpod-orchestration](https://github.com/OpenSourceFilms/opensourcefilms-runpod-orchestration) | MIT | Public planner/tools, not a grant of rights to RunPod or external services. |
| [opensourcefilms-deepseek-agent](https://github.com/OpenSourceFilms/opensourcefilms-deepseek-agent) | MIT | Retired helper; users obtain their own provider licences and access. |
| [opensourcefilms-video-edit-method-bench](https://github.com/OpenSourceFilms/opensourcefilms-video-edit-method-bench) | MIT for OSF originals; upstream Apache-2.0 portions of adapted graphs retain their terms | Edit Anything and FlexAM workflow modifications have [provenance notices](https://github.com/OpenSourceFilms/opensourcefilms-video-edit-method-bench/blob/main/workflows/UPSTREAM_NOTICES.md); Ditto's NC-SA graph is excluded. LTX model terms are conditional. |
| [opensourcefilms-vsr-stab4](https://github.com/OpenSourceFilms/opensourcefilms-vsr-stab4) | MIT for OSF postprocessor | SeedVR2, ComfyUI integrations, model weights and footage are external, not relicensed. |
| [opensourcefilms-basics-auto](https://github.com/OpenSourceFilms/opensourcefilms-basics-auto) | MIT for OSF core | Published CPU quality-control extract, not the upstream segmentation/matting models. |
| [opensourcefilms-bts-ingest](https://github.com/OpenSourceFilms/opensourcefilms-bts-ingest) | MIT for OSF core | Published offline registry, not live uploader, B2 assets or contributor footage. |
| [osf-viewer](https://github.com/OpenSourceFilms/osf-viewer) | **MIT for OSF-controlled original source only** | [LICENSE](https://github.com/OpenSourceFilms/osf-viewer/blob/main/LICENSE) and [scope](https://github.com/OpenSourceFilms/osf-viewer/blob/main/LICENSING_SCOPE.md) expressly exclude 12 Office fixtures with unresolved provenance, external packages and other independently owned material. [Issue #1](https://github.com/OpenSourceFilms/osf-viewer/issues/1) tracks residual rights. |
| [osf-backup](https://github.com/OpenSourceFilms/osf-backup) | **MIT for OSF-controlled original source only** | [LICENSE](https://github.com/OpenSourceFilms/osf-backup/blob/main/LICENSE) and [scope](https://github.com/OpenSourceFilms/osf-backup/blob/main/LICENSING_SCOPE.md) do not relicense its 14 upstream dependencies or third-party material. Historical implementation only, not active B2/restic deployment. [Issue #1](https://github.com/OpenSourceFilms/osf-backup/issues/1) remains available for residual rights claims. |
| [.github](https://github.com/OpenSourceFilms/.github) | No root licence; organisation documentation only | Do not infer a universal licence for organisational identity, logos or copied documentation. |

**Inventory (28 October):** 18 public repositories, 17 with scoped root
MIT grants for OSF-controlled originals, and one organisation-profile
documentation repository without a root licence. The 12 Viewer binary
fixtures and all independently owned components remain excluded; the
publication of these two MIT grants is not a complete chain-of-title
or dependency-redistribution clearance.

## Post-merge exact-`main` CI verification: 27 October 2026

A post-merge read-only repository/Actions API comparison checked each public
repository's **current `main` branch commit SHA** against the
`head_sha`, completion status and conclusion of recent **push**-triggered
GitHub Actions runs. At this checkpoint:

- **16/16 public code repositories with a configured Actions workflow** had
  a **completed successful run on their exact current `main` SHA**.
- [`opensourcefilms-three-camera-hdr`](https://github.com/OpenSourceFilms/opensourcefilms-three-camera-hdr)
  remains a **design-only repository without any Actions runs**. This is
  neither a failed CI run nor hardware acceptance.
- [`.github`](https://github.com/OpenSourceFilms/.github) contains the
  organisation's profile/licensing documentation; it has **no Actions runs**
  and is excluded from the 17 code-repository denominator.
- This **supersedes only the older 14/17 point-in-time CI comparison below**.
  The older result described an earlier set of head commits, not failures
  that remain outstanding. This checkpoint also incorporates the merged
  BASICS, Viewer, ComfyUI and retired-DeepSeek hardening changes.

| Public code repository | Verified `main` SHA prefix | Exact-commit run |
|---|---|---|
| [opensourcefilms-tools](https://github.com/OpenSourceFilms/opensourcefilms-tools) | `48f4561` | [Successful exact-head run](https://github.com/OpenSourceFilms/opensourcefilms-tools/actions/runs/40383169189) |
| [opensourcefilms-comfyui-workflows](https://github.com/OpenSourceFilms/opensourcefilms-comfyui-workflows) | `aeef177` | [Successful exact-head run](https://github.com/OpenSourceFilms/opensourcefilms-comfyui-workflows/actions/runs/40415315601) |
| [opensourcefilms-baton](https://github.com/OpenSourceFilms/opensourcefilms-baton) | `602369f` | [Successful exact-head run](https://github.com/OpenSourceFilms/opensourcefilms-baton/actions/runs/40400128505) |
| [opensourcefilms-erf](https://github.com/OpenSourceFilms/opensourcefilms-erf) | `0889133` | [Successful exact-head run](https://github.com/OpenSourceFilms/opensourcefilms-erf/actions/runs/40396771707) |
| [opensourcefilms-platelock](https://github.com/OpenSourceFilms/opensourcefilms-platelock) | `c2adbd6` | [Successful exact-head run](https://github.com/OpenSourceFilms/opensourcefilms-platelock/actions/runs/40389541831) |
| [opensourcefilms-bikematch](https://github.com/OpenSourceFilms/opensourcefilms-bikematch) | `da25d19` | [Successful exact-head run](https://github.com/OpenSourceFilms/opensourcefilms-bikematch/actions/runs/40377000233) |
| [opensourcefilms-orbitturn](https://github.com/OpenSourceFilms/opensourcefilms-orbitturn) | `789283d` | [Successful exact-head run](https://github.com/OpenSourceFilms/opensourcefilms-orbitturn/actions/runs/40378943022) |
| [opensourcefilms-motiongen-tests](https://github.com/OpenSourceFilms/opensourcefilms-motiongen-tests) | `1c5533c` | [Successful exact-head run](https://github.com/OpenSourceFilms/opensourcefilms-motiongen-tests/actions/runs/40381836547) |
| [opensourcefilms-runpod-orchestration](https://github.com/OpenSourceFilms/opensourcefilms-runpod-orchestration) | `cc450b1` | [Successful exact-head run](https://github.com/OpenSourceFilms/opensourcefilms-runpod-orchestration/actions/runs/40385024327) |
| [opensourcefilms-deepseek-agent](https://github.com/OpenSourceFilms/opensourcefilms-deepseek-agent) | `cb22fc3` | [Successful exact-head run](https://github.com/OpenSourceFilms/opensourcefilms-deepseek-agent/actions/runs/40419951647) |
| [opensourcefilms-video-edit-method-bench](https://github.com/OpenSourceFilms/opensourcefilms-video-edit-method-bench) | `6a2720d` | [Successful exact-head run](https://github.com/OpenSourceFilms/opensourcefilms-video-edit-method-bench/actions/runs/40412599497) |
| [opensourcefilms-vsr-stab4](https://github.com/OpenSourceFilms/opensourcefilms-vsr-stab4) | `779c0b4` | [Successful exact-head run](https://github.com/OpenSourceFilms/opensourcefilms-vsr-stab4/actions/runs/40397949219) |
| [opensourcefilms-basics-auto](https://github.com/OpenSourceFilms/opensourcefilms-basics-auto) | `b9c9598` | [Successful exact-head run](https://github.com/OpenSourceFilms/opensourcefilms-basics-auto/actions/runs/40414214863) |
| [opensourcefilms-bts-ingest](https://github.com/OpenSourceFilms/opensourcefilms-bts-ingest) | `7437ec4` | [Successful exact-head run](https://github.com/OpenSourceFilms/opensourcefilms-bts-ingest/actions/runs/40412712795) |
| [osf-viewer](https://github.com/OpenSourceFilms/osf-viewer) | `0290e84` | [Successful exact-head run](https://github.com/OpenSourceFilms/osf-viewer/actions/runs/40415608004) |
| [osf-backup](https://github.com/OpenSourceFilms/osf-backup) | `6405634` | [Successful exact-head run](https://github.com/OpenSourceFilms/osf-backup/actions/runs/40399243854) |

**Evidence boundary:** GitHub reports successful completion of the configured
workflow; this check did not independently replay its assertions, review
untrusted runtime dependencies, guarantee that the checks cover all relevant
files, validate GPU image quality, qualify a fresh deployment, or settle
upstream model/output permissions. Changing `main` requires a fresh
exact-head comparison; treat this as a dated checkpoint, not continuous
monitoring.

## Independent GitHub check: 27 October 2026 (historical checkpoint)

The following 27 October inventory predates the 28 October Viewer and
Backup MIT grants and is preserved as dated evidence, not current status.

A read-only GitHub inspection rechecked the organisation's 18 currently public
repositories: 15 contain root `LICENSE` files with the standard MIT
permission and preservation clauses and an Open Source Films 2026 copyright
notice, two (`osf-viewer` and `osf-backup`) still have **no general reuse
licence**, and `.github` is organisation-profile documentation without a root
licence. This confirms the root-level inventory above; it does **not** prove
OSF's chain of title, cover embedded assets or grant rights in third-party
dependencies. The existing owner/licence issues remain open.

Public GitHub Actions results were also compared against exact `main`
commit SHAs for the **17 public code repositories**, at the time of review:

- **14/17** had a completed successful run at the then-current `main` SHA.
- `opensourcefilms-platelock`: latest successful run preceded two
  README-only commits. This is **not** exact-head CI acceptance, and the
  published workflow's CPU smoke contract does not validate GPU image quality.
- `opensourcefilms-orbitturn`: latest successful run was on a **different
  documentation-licensing commit branch** from `main` (siblings with the
  same parent). The result is not exact-`main` acceptance.
- `opensourcefilms-three-camera-hdr`: no GitHub Actions runs returned.
  The repository describes a design, not measured hardware acceptance.

The `.github` profile is not counted among those 17 code repositories.
These are point-in-time publication checks, **not** evidence that all 17
projects are deployable, commercially cleared, GPU-tested or free of
security issues. A CI pass only establishes the contract actually tested
by that repository's workflow.

## GitHub Actions static security snapshot: 27 October 2026

The current public `main` trees contain **16 GitHub Actions YAML files**
across the 17 public code repositories; the `opensourcefilms-three-camera-hdr`
design-only repository has no Actions workflow. The organisation-profile
`.github` repository has no Actions workflow either.

A direct read of all 16 YAML definitions found:

- All 16 explicitly scope the job token to `permissions: contents: read`.
  None declares broader repository write permissions.
- All **30 external `uses:` action occurrences** refer to full 40-character
  commit SHAs rather than mutable release tags, covering the GitHub
  Actions checkout/Python setup uses and the `astral-sh/setup-uv` use.
- No `pull_request_target` or `workflow_run` privileged event triggers,
  `write-all` grant, or direct `secrets.*` interpolation was found in
  those workflow definitions.
- The published jobs do include downloads of Python dependencies from
  package indexes. Version pinning does not independently prove that
  wheel contents are reproducible or satisfy licence/security obligations.

**Limits:** This is a static review of current workflow YAML only. It
does **not** audit arbitrary scripts that workflows execute, action-code
contents at the pinned SHAs, transitive supply-chain integrity, historical
branches, release assets, organisation Actions settings, secret exposure
in repository history, or what a malicious pull request can do with a
runner. No workflows, permissions or organisation settings were modified.
Rerun this review after future CI changes.

## Viewer redistribution evidence update: 27 October 2026 (historical checkpoint)

This dated section predates the scoped MIT grants recorded above.
The previously unlicensed [osf-viewer repository](https://github.com/OpenSourceFilms/osf-viewer)
now has two additional **evidence-only** publication safeguards:

- [A 12-file Office fixture inventory](https://github.com/OpenSourceFilms/osf-viewer/blob/main/docs/fixture-inventory.json)
  records exact Git blob IDs and unresolved source/embedded-asset provenance.
  [CI rejects unexpected file changes](https://github.com/OpenSourceFilms/osf-viewer/blob/main/scripts/verify_fixture_manifest.py);
  a matching byte hash is **not** a redistribution licence or authorship proof.
- [A version-specific 21-package Python dependency register](https://github.com/OpenSourceFilms/osf-viewer/blob/main/DEPENDENCY_LICENSES.md)
  records **publisher-declared** licence metadata for every locked direct
  dependency. It identifies `mutagen` as GPL-2.0-or-later, five
  compression/archive dependencies as LGPL-2.1-or-later and `odfpy`'s
  unresolved mixed-family licence metadata. Offline CI checks exact-pin
  inventory coverage, **not** compliance with those licences.

Neither item changes the **absence of a root Viewer reuse licence** or
clears its Office binary fixtures. The [Viewer rights issue](https://github.com/OpenSourceFilms/osf-viewer/issues/1)
and the [historical Backup rights issue](https://github.com/OpenSourceFilms/osf-backup/issues/1)
remain open pending authorised code-contribution and third-party-material
review. Do not infer that permission to run or view published source is
permission to redistribute the full application or all dependency binaries.

## Review findings and limits

- **Current-tree media/fixture inventory:** Recursive trees of the 17
  public code repositories were checked for common model and media
  extensions. No `.safetensors`, `.ckpt`, `.pth`, `.pt` or `.onnx` model
  checkpoints were identified in those current trees. Identified non-source
  artifacts include one generated Kimodo `.npz` sample, a one-second
  **digital-silence WAV independently reproduced byte-for-byte** in the
  [historical Tools archive](https://github.com/OpenSourceFilms/opensourcefilms-tools/blob/main/scripts/generate_silence_fixture.py)
  (original committer's authorship not established), and **12 Office-format test fixtures**
  (`.doc/.docx/.xls/.xlsx/.ppt/.pptx/.odt/.ods/.odp/.rtf` and corrupt test
  files) under `osf-viewer/tests/fixtures/`. Viewer tests describe these
  as hand-built synthetic samples; third-party template content or document
  metadata **has not been independently audited**. Their provenance is
  included in the unresolved [Viewer rights review](https://github.com/OpenSourceFilms/osf-viewer/issues/1).
  This filename-based current-tree inspection does **not** establish
  copyright ownership, search historical removed blobs exhaustively, or
  rule out embedded content in unrecognised formats.
- **Known attribution corrections:** Meta's SAM 3 custom terms are disclosed
  without calling them an OSI-approved permissive licence; adapted upstream
  Apache workflows retain author/source notices and a full licence copy.
- **Open rights checks:** Public authorship, contractor/contributor assignments,
  imported code and all dependency licences have **not** been independently
  verified file-by-file. A root MIT file is an OSF permission claim, not proof
  of chain of title. Resolve third-party contributors' rights before assuming
  OSF can relicense their expression.
- **Geographic rights:** The [MiniMax H3 official agreement](https://huggingface.co/MiniMaxAI/MiniMax-H3/blob/main/LICENSE) excludes the United States, European Union, United Kingdom and Republic of Korea from its standard licence territory. It restricts use and display of H3-generated Outputs outside that territory, not only hosting or transfer of weights. Australia is not listed as excluded, but generation location does not establish worldwide exhibition rights. Treat international production/distribution as requiring independent legal review or written authorisation. This source-level analysis does **not** conclude whether any particular LifeR footage or final release is licensed. 
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

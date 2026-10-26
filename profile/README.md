# Open Source Films

Open Source Films is a small, independent production making a feature film without industry
backing, a psychological character drama with genre and fantastical elements. Because the
production can't rely on a studio's editorial, VFX, or infrastructure teams, we build the tools we
need ourselves, and release the ones that are broadly useful.

## Credit to upstream researchers and developers

Much of OSF's engineering is **integration, testing, adaptation and publication of workflows using other people's research and software**. We do not claim to have invented the underlying AI models, tracking algorithms, rendering engines, numerical libraries or upstream custom nodes. OSF's own contributions are the specific code, post-processing, engineering, test methods and documentation identified in each repository.

For example, our video-restoration experiments depend on [ByteDance Seed's SeedVR and SeedVR2](https://github.com/ByteDance-Seed/SeedVR), with ComfyUI integrations including [NumZ, Adrien Toupet (AInVFX) and contributors' SeedVR2 package](https://github.com/numz/ComfyUI-SeedVR2_VideoUpscaler). Our STAB4 work is an **experimental temporal post-processor applied to enhanced frames**, not a new restoration model or a replacement for their work.

Each repository should identify upstream authors and licences prominently. OSF's licence covers only its own original contributions and never relicenses third-party code, weights, models or media.

For the current public-repository licence inventory, upstream rights boundaries
and publication checklist, see our [public licensing and provenance register](PUBLICATION_LICENSING.md).
Public code does not grant rights to separate model weights, media or third-party components.

## Why these tools exist

A small production still has to solve the same problems a large one does:

- searching a large, continuously growing archive of raw footage
- producing usable edits from behind-the-scenes and documentation footage
- registering AI-generated clean plates back onto original footage for VFX
- running large video models without owning a render farm
- keeping long AI-assisted development sessions coherent across restarts and context limits
- making experimental workflows reproducible for anyone who wants to check our work

## Runpod

GPU development and processing for much of this toolchain happens in collaboration with Runpod,
whose on-demand infrastructure makes it practical for a small independent production to access
large-VRAM and newer GPU hardware only when it's actually needed, rather than owning it outright.

## Start with an offline example

Some of our most reusable releases can be explored on an ordinary computer,
using synthetic inputs instead of production footage, model weights or live services:

- [Try a timestamped ERF footage search](https://github.com/OpenSourceFilms/opensourcefilms-erf/blob/main/docs/try-footage-search.md): run the actual FTS5 lexical indexing/search code against invented transcripts and inspect synthetic HTML thumbnails. It is not semantic or visual retrieval.
- [Reproduce PlateLock's before/after registration](https://github.com/OpenSourceFilms/opensourcefilms-platelock/blob/main/docs/try-registration-demo.md): generate a three-panel PNG from a known synthetic transform using PlateLock's own backward maps, without trackers or film footage.
- [Validate ComfyUI workflow graphs](https://github.com/OpenSourceFilms/opensourcefilms-comfyui-workflows/blob/main/docs/validate-workflows.md): check editor and API exports without launching ComfyUI or downloading models.
- [Fingerprint a PNG source sequence](https://github.com/OpenSourceFilms/opensourcefilms-vsr-stab4/blob/main/docs/sequence-inventory.md): a standard-library-only, read-only source inventory with 21 synthetic tests; it is not a PNG decoder or CRC audit.
- [Try offline GPU admission planning](https://github.com/OpenSourceFilms/opensourcefilms-runpod-orchestration/blob/main/docs/fleet-admission-offline-demo.md): test fail-closed placement decisions using 19 synthetic checks; nothing is scheduled or allocated.

Passing an offline test demonstrates only its documented contract. It does not
qualify a model, a production workflow or real-world output quality.

## Public projects

These repositories document working tools, development prototypes and research. Read each
repository's README and licensing notes before relying on a workflow in production.

### Film production and VFX

| Repository | Purpose | Current published maturity |
|---|---|---|
| [Editorial Retrieval Fabric (ERF)](https://github.com/OpenSourceFilms/opensourcefilms-erf) | Media analysis, semantic retrieval and editorial assembly | Active development; initial public release |
| [PlateLock](https://github.com/OpenSourceFilms/opensourcefilms-platelock) | Register generated clean plates to original footage; Nuke STMaps | Work in progress |
| [ComfyUI workflows](https://github.com/OpenSourceFilms/opensourcefilms-comfyui-workflows) | Production-oriented graph recipes and OSF custom nodes | Initial public release; workflow-specific licensing |
| [STAB4 temporal stabilisation](https://github.com/OpenSourceFilms/opensourcefilms-vsr-stab4) | Experimental temporal post-processing for externally enhanced frames, including SeedVR2 workflows; credits upstream research | Standalone synthetic-tested experimental release |
| [BASICS mask and matte QC](https://github.com/OpenSourceFilms/opensourcefilms-basics-auto) | CPU-based actor-mask ownership flags, alpha QC and review overlays | Initial offline-tested core, not full inference pipeline |
| [BTS Ingest registry core](https://github.com/OpenSourceFilms/opensourcefilms-bts-ingest) | SQLite-backed media-intake metadata, provenance, state and quota logic | Initial offline-tested core, not an upload service |
| [OrbitTurn / H3](https://github.com/OpenSourceFilms/opensourcefilms-orbitturn) | Camera-motion-guided video generation experiments | Experimental / production tooling |
| [Video edit method bench](https://github.com/OpenSourceFilms/opensourcefilms-video-edit-method-bench) | Reproducible comparisons of video-editing methods | Research evaluation, not a finished pipeline |
| [Motion generation tests](https://github.com/OpenSourceFilms/opensourcefilms-motiongen-tests) | Compatibility and results for motion-generation models | Research snapshot |
| [Three-camera HDR](https://github.com/OpenSourceFilms/opensourcefilms-three-camera-hdr) | Low-cost multi-camera HDR capture concept | Design only; not built or measured |

### Infrastructure and development tools

| Repository | Purpose | Current published maturity |
|---|---|---|
| [Baton](https://github.com/OpenSourceFilms/opensourcefilms-baton) | Preserve AI-assisted development state across session boundaries | Offline-tested, environment-specific continuity hooks |
| [RunPod orchestration](https://github.com/OpenSourceFilms/opensourcefilms-runpod-orchestration) | Pod bootstrapping, orchestration examples and offline GPU placement advice | Historical scripts plus tested reference planner, not a live scheduler |
| [OSF Backup](https://github.com/OpenSourceFilms/osf-backup) | Selective, auditable content-addressed backup design | Historical implementation; not a current deployment guide |
| [OSF Viewer](https://github.com/OpenSourceFilms/osf-viewer) | Local universal file inspection and previews | Environment-specific utility |
| [DeepSeek agent](https://github.com/OpenSourceFilms/opensourcefilms-deepseek-agent) | Research and delegation helper scripts | Historical; no longer in OSF's active agent stack |

### Other research and project history

| Repository | Purpose | Current published maturity |
|---|---|---|
| [BikeMatch](https://github.com/OpenSourceFilms/opensourcefilms-bikematch) | Privacy-conscious stolen-bicycle matching concept and code | Early development; not deployed |
| [Earlier filmmaking tools](https://github.com/OpenSourceFilms/opensourcefilms-tools) | Predecessor of the present ERF implementation | Superseded development snapshot |

## Reading the status labels

- **Active development / initial public release:** published code, changing interfaces, limited general installation support.
- **Work in progress / experimental:** partial implementations or methods under evaluation, not a general production guarantee.
- **Research snapshot / design only:** documentation or evaluation evidence, not a complete operational product.
- **Environment-specific / historical:** useful engineering examples that may require significant adaptation.

Source-code licenses do not automatically cover third-party models, pretrained weights, media or upstream custom nodes. See each repository's specific license and dependency documentation.

## Standalone tools and methods

These can be read or tested without access to our feature-film media:

- [Validate ComfyUI workflow graphs](https://github.com/OpenSourceFilms/opensourcefilms-comfyui-workflows/blob/main/docs/validate-workflows.md):
  offline structural checks for both API and editor exports; tests cover all 16 published graphs.
- [Audit native ComfyUI PNG outputs](https://github.com/OpenSourceFilms/opensourcefilms-comfyui-workflows/blob/main/docs/audit-native-png-sequence.md):
  read-only file hashes, count, PNG CRC and optional geometry checks. Does not alter, decode or composite images.
- [Check ComfyUI export publication safety](https://github.com/OpenSourceFilms/opensourcefilms-comfyui-workflows/blob/main/docs/publication-hygiene.md):
  an offline, redacted diagnostic for common private paths, endpoints, credentials and embedded preview caches.
- [Search synthetic ERF footage records](https://github.com/OpenSourceFilms/opensourcefilms-erf/blob/main/docs/try-footage-search.md): executed SQLite FTS5 queries, timestamped JSON results and an optional local HTML report with invented thumbnails; no GPU inference or real video.
- [Verify PlateLock synthetic registration visually](https://github.com/OpenSourceFilms/opensourcefilms-platelock/blob/main/docs/try-registration-demo.md): CPU-only real backward-map functions, original/misaligned/aligned panels and five regression tests; not tracker quality acceptance.
- [Try ERF's explicit outcome journal](https://github.com/OpenSourceFilms/opensourcefilms-erf/blob/main/docs/try-outcome-journal.md):
  a self-contained Python/SQLite example of stage statuses and derived projections, using synthetic inputs and temporary storage only.
- [Run the offline GPU placement planner](https://github.com/OpenSourceFilms/opensourcefilms-runpod-orchestration/blob/main/docs/fleet-admission-offline-demo.md):
  19 synthetic tests for stale pods, native broker capacity, admission boundaries, invalid timestamps and duplicate jobs. It selects advisory candidates only; it does not allocate VRAM or launch jobs.
- [Fleet GPU scheduling design](https://github.com/OpenSourceFilms/opensourcefilms-runpod-orchestration/blob/main/docs/fleet-gpu-scheduling.md):
  host discovery, native VRAM reservations, duplicate-job avoidance and delivery-evidence boundaries.
  This is architecture guidance, not the private deployed broker.

- [Test STAB4 on synthetic sequences](https://github.com/OpenSourceFilms/opensourcefilms-vsr-stab4): the original OSF post-processor with full SeedVR2, ComfyUI and numerical-library attribution; no model weights or real shot footage.
- [Inspect video-editing method workflow exports](https://github.com/OpenSourceFilms/opensourcefilms-video-edit-method-bench): offline structure checks for published ComfyUI editor and API graphs; not runtime or image-quality acceptance.
- [Check the published motion-generation sample](https://github.com/OpenSourceFilms/opensourcefilms-motiongen-tests/blob/main/tests/test_motiongen_published_sample.py): verify the public Kimodo NPZ array schema and launcher syntax with six CPU-only checks; does not generate motion.
- [Exercise Baton's continuity-hook self-check](https://github.com/OpenSourceFilms/opensourcefilms-baton/blob/main/tests/selfcheck.sh): synthetic hook and redaction tests, without production transcripts. Redaction is best-effort and not a secret vault.
- [Check actor masks and mattes without GPU inference](https://github.com/OpenSourceFilms/opensourcefilms-basics-auto): generated test frames, area/ownership checks, matte QC and review overlays.
- [Explore the offline BTS intake registry](https://github.com/OpenSourceFilms/opensourcefilms-bts-ingest): synthetic SQLite and provenance tests, without a publicly deployable uploader.

## Links

- [Runpod](https://www.runpod.io/)
- [Open Source Films website](https://opensourcefilms.org/).
- Contribution guidance: see each repo's own `CONTRIBUTING.md` where present.

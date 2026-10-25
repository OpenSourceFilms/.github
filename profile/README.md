# Open Source Films

Open Source Films is a small, independent production making a feature film without industry
backing, a psychological character drama with genre and fantastical elements. Because the
production can't rely on a studio's editorial, VFX, or infrastructure teams, we build the tools we
need ourselves, and release the ones that are broadly useful.

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

## Public projects

These repositories document working tools, development prototypes and research. Read each
repository's README and licensing notes before relying on a workflow in production.

### Film production and VFX

| Repository | Purpose | Current published maturity |
|---|---|---|
| [Editorial Retrieval Fabric (ERF)](https://github.com/OpenSourceFilms/opensourcefilms-erf) | Media analysis, semantic retrieval and editorial assembly | Active development; initial public release |
| [PlateLock](https://github.com/OpenSourceFilms/opensourcefilms-platelock) | Register generated clean plates to original footage; Nuke STMaps | Work in progress |
| [ComfyUI workflows](https://github.com/OpenSourceFilms/opensourcefilms-comfyui-workflows) | Production-oriented graph recipes and OSF custom nodes | Initial public release; workflow-specific licensing |
| [OrbitTurn / H3](https://github.com/OpenSourceFilms/opensourcefilms-orbitturn) | Camera-motion-guided video generation experiments | Experimental / production tooling |
| [Video edit method bench](https://github.com/OpenSourceFilms/opensourcefilms-video-edit-method-bench) | Reproducible comparisons of video-editing methods | Research evaluation, not a finished pipeline |
| [Motion generation tests](https://github.com/OpenSourceFilms/opensourcefilms-motiongen-tests) | Compatibility and results for motion-generation models | Research snapshot |
| [Three-camera HDR](https://github.com/OpenSourceFilms/opensourcefilms-three-camera-hdr) | Low-cost multi-camera HDR capture concept | Design only; not built or measured |

### Infrastructure and development tools

| Repository | Purpose | Current published maturity |
|---|---|---|
| [Baton](https://github.com/OpenSourceFilms/opensourcefilms-baton) | Preserve AI-assisted development state across session boundaries | Initial public release |
| [RunPod orchestration](https://github.com/OpenSourceFilms/opensourcefilms-runpod-orchestration) | Pod bootstrapping and remote worker orchestration | Historical scripts with documented limits |
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
- [Try ERF's explicit outcome journal](https://github.com/OpenSourceFilms/opensourcefilms-erf/blob/main/docs/try-outcome-journal.md):
  a self-contained Python/SQLite example of stage statuses and derived projections, using synthetic inputs and temporary storage only.
- [Fleet GPU scheduling design](https://github.com/OpenSourceFilms/opensourcefilms-runpod-orchestration/blob/main/docs/fleet-gpu-scheduling.md):
  host discovery, native VRAM reservations, duplicate-job avoidance and delivery-evidence boundaries.
  This is architecture guidance, not the private deployed broker.

## Links

- [Runpod](https://www.runpod.io/)
- [Open Source Films website](https://opensourcefilms.org/).
- Film/production channel and YouTube links: not added here.
- Contribution guidance: see each repo's own `CONTRIBUTING.md` where present.
- Contact: not yet added here, pending a public contact route Daniel is comfortable with.

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

## Projects

**[opensourcefilms-erf](https://github.com/OpenSourceFilms/opensourcefilms-erf)**: Editorial
Retrieval Fabric, the current, canonical media-intelligence system. Ingests footage, enriches it
with audio and visual analysis, builds a semantic index, and supports short-form and narrative edit
assembly. *Status: active development, initial public release.*

**[opensourcefilms-platelock](https://github.com/OpenSourceFilms/opensourcefilms-platelock)**: a VFX
tool that locks an AI-generated clean plate back onto original footage via point tracking and
exports STMaps for Nuke. *Status: work in progress, initial public release.*

**[opensourcefilms-comfyui-workflows](https://github.com/OpenSourceFilms/opensourcefilms-comfyui-workflows)**:
production ComfyUI workflow graphs, pinned dependency documentation, and our own optical-flow
mask-propagation custom node. *Status: initial public release.*

**[opensourcefilms-baton](https://github.com/OpenSourceFilms/opensourcefilms-baton)**: a Claude Code
session-continuity tool. Survives context compaction, `/clear`, restarts, and model switches. Grew
out of the same production engineering environment as the rest of this tooling. *Status: initial
public release.*

**[opensourcefilms-tools](https://github.com/OpenSourceFilms/opensourcefilms-tools)**: an earlier
generation of the media-retrieval pipeline, superseded by erf. Kept public for its development
lineage. *Status: development snapshot, not actively maintained as a separate product.*

## Status labels used above

- **Active development**: changing regularly, in step with the production.
- **Initial public release**: published and usable, expect rough edges.
- **Work in progress**: functional but incomplete.
- **Development snapshot**: kept for reference, not the current recommended entry point.

## Links

- [Runpod](https://www.runpod.io/)
- Website, film/production channel, YouTube: not yet added here, pending Daniel's preferred links.
- Contribution guidance: see each repo's own `CONTRIBUTING.md` where present.
- Contact: not yet added here, pending a public contact route Daniel is comfortable with.

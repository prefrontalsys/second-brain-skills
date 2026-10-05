# Canonical personal agent skills

This repository is the canonical semantic source for Scot Campbell's reusable agent skills.

## Source-of-truth policy

- Canonical skill source lives under `skills/<skill-name>/SKILL.md`.
- ChatGPT plugins and other runtime-specific packages are generated from these files.
- Runtime packaging may add manifests or compatibility metadata, but it must not silently change skill behavior.
- Obsidian copies are working mirrors, not independent semantic sources. Changes should be reconciled back to this repository.
- Installation state and runtime attachment state are separate. A plugin can be installed without its skills appearing in an already-open conversation.

## ChatGPT release process

1. Read the canonical skill inventory from `skills/`.
2. Verify all required packaging prerequisites before mutation.
3. Update the existing private ChatGPT plugin rather than creating a duplicate.
4. Preserve canonical skill text unless a documented compatibility adaptation is required.
5. Read back the installed release and compare its inventory and contents with this repository.
6. Record the plugin ID and release ID after successful publication.

## Current ChatGPT plugin

- Package name: `agent-workflow-guardrails`
- Plugin ID: `plugins_6ac243b119b481919ab6df19f8373d03`
- This identifier is stable; future releases should update this plugin rather than create another copy.

---
name: chatgpt-skill-plugin-installation
description: Install or update user-authored skills in ChatGPT as a private plugin while preserving a canonical source, checking prerequisites before use, avoiding duplicate plugins, and verifying installed files separately from runtime attachment.
metadata:
  author: "S2B"
  version: "1.0"
  category: "workflow"
---

## ChatGPT Skill Plugin Installation

### Trigger
Use this skill when the user asks to install, update, synchronize, or verify locally authored skills as ChatGPT skills or a ChatGPT plugin.

### Scope
Manage packaging and installation of user-authored skill sources. Treat the canonical repository as the semantic source of truth when one exists. Do not rewrite skill behavior merely to make packaging easier.

### Procedure
1. Resolve the canonical source and intended plugin identity before creating or updating anything.
2. Determine whether the target operation is a create or an update. If a plugin with the intended identity already exists, update it instead of creating a duplicate.
3. Inspect every validator, scanner, executable, connector, or other prerequisite required by the chosen installation path before relying on it. If a prerequisite is unavailable, report it before starting a dependent mutation.
4. Read the current installed plugin release before an update and retain its plugin ID and current release ID.
5. Preserve canonical skill text verbatim unless ChatGPT packaging requires a compatibility adaptation. Keep compatibility changes narrow and document them explicitly.
6. Build a package containing the intended skills and a valid plugin manifest. Bump the semantic version for updates.
7. Before upload, compare the candidate skill inventory with the intended canonical inventory. Resolve unexplained omissions or additions.
8. Create or update exactly one target plugin.
9. Read back the installed release and compare each installed skill with the intended source. Installation succeeds only when the inventory and contents match except for documented compatibility adaptations.
10. Check runtime attachment separately. A successfully installed plugin may not appear in the current conversation's attached-skill catalog until a later refresh or conversation.

### Completion checks
- The intended plugin exists exactly once.
- The installed release contains every intended skill and no unexplained extra skill.
- Installed skill text matches the canonical source except for documented compatibility adaptations.
- Plugin ID and release ID are recorded for later updates.
- Installation state and current-conversation attachment state are reported separately.
- Missing optional runtime attachment is not reported as installation failure.

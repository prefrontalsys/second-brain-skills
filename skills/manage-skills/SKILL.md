---
name: manage-skills
description: Create, revise, audit, or retire reusable agent skills. Use before editing or creating a skill, and use review-only mode when the user asks only for analysis or recommendations.
metadata:
  author: "S2B"
  version: "1.5"
  category: "core"
---

## Managing Skills

### Review-only mode
When the user asks to audit, analyze, compare, or recommend skill changes without applying them, do not mutate skills. Inspect the current target skill and return proposed edits only. Separate reusable procedures from facts, preferences, project notes, and one-time requests; only reusable procedures belong in skills. This rule overrides the automatic-revision guidance below unless the user separately authorizes skill changes in the current task.

During a skill audit, distinguish skills attached to the current conversation from skills present in owned plugin releases and from local, vault, or repository source files. An empty attached-skill catalog does not establish that no installed skills exist. State which layer was inspected and do not infer presence, absence, or version equality across layers without verification.

Skill mutations apply immediately unless the active skill-management capability explicitly provides staging. Verify the current capability before writing.

Skills are where task knowledge lives: how a kind of task is done, the pitfalls, and the user's corrections about that work. Memory holds facts about the user and pointers into external knowledge; it is not the place for procedures.

### Revising a skill
- Read the current skill before changing it so the edit is based on current text.
- Revise the skill used whenever it misled the agent or lacked a reusable step, and whenever the user corrects how this kind of task should be done, unless the current task is review-only.
- Fold only verified task knowledge into the skill so future runs can skip rediscovery.
- Fix in place. Change the sentence that was wrong instead of appending a dated update log.
- Write lessons, not logs: one rule per point, imperative plus one clause explaining why.
- Write only instructions that have been confirmed. Do not encode speculation as procedure.
- Preserve locked identity or linkage fields when the active skill-management system defines them as immutable.

### Patch
Prefer a targeted patch for a small revision. Match enough current surrounding text to make the target unambiguous.

### Update
Replace a whole body only when the skill needs restructuring. Prefer a patch for smaller changes.

### Create
- Create a skill when the workflow has no home in an existing skill. Prefer extending a skill that already covers the area.
- Keep new skills narrow and instructions concrete. Record only behavior worth reusing.
- Grant only the tools required for the workflow.

### Delete or retire
Delete or retire a skill only when the user explicitly authorizes it or when an authorized governance workflow has produced a retirement decision. Do not remove a skill merely because it is unused, duplicated-looking, or temporarily broken. Verify any replacement preserves required behavior before retirement.

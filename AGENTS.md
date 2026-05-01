# Agent Context — woke-no-animal-violence

This repo distributes the woke scanner configuration for detecting speciesist and animal-violence idioms in text.

## Files

| File | Description |
|---|---|
| `.woke.yaml` | Auto-generated woke rule set. Contains one rule per idiom pattern: `terms` to match, `alternatives` to suggest, `severity`, and `reason`. Categories include `animal-violence` and `industry-euphemism`. |
| `README.md` | Usage instructions for integrating `.woke.yaml` into a project. |
| `.mcp.json` | MCP server config for this repo (local tooling, not committed upstream). |
| `AGENTS.md` | This file. |
| `LICENSE` | MIT license. |

## Toolchain position

This repo is a **generated distribution target** in the [Open Paws no-animal-violence](https://github.com/Open-Paws/no-animal-violence) suite. The canonical rule source lives in `no-animal-violence`; `tools/generate_all.py` in that repo writes `.woke.yaml` here. Do not edit `.woke.yaml` directly — raise changes in the canonical repo and re-run the generator.

Downstream consumers copy `.woke.yaml` into their project root or pass it via `--config` to [woke](https://github.com/get-woke/woke).

## Constraints for agents

- **Do not edit `.woke.yaml` manually.** It is auto-generated; manual edits will be overwritten on the next generator run.
- **Do not add rule logic here.** New patterns belong in `no-animal-violence/rules.yaml`, not in this repo.
- Changes to `README.md`, `AGENTS.md`, or `LICENSE` follow the normal pipeline (branch → PR → merge).
- The only legitimate commit types here are: `chore:` (tooling/meta), `docs:` (README/AGENTS), or a regeneration commit from the generator (`chore: regenerate from no-animal-violence@<sha>`).

# Bright Lights Gas City Configuration

Persistent Gas City configuration for the Bright Lights workspace.

This repository follows the PackV2 layout recommended by Gas City:

- `pack.toml`, `agents/`, `formulas/`, and `assets/imports/` are the portable team definition.
- `city.toml` is the deployment configuration for this city.
- `.gc/`, `.beads/`, `.runtime/`, and worktrees are machine-local runtime state and are intentionally not committed.

## Local Setup

1. Clone this repository.
2. Install `gc`, `bd`, `dolt`, `git`, `jq`, and a supported agent provider.
3. Bind local rigs on the machine that will run the city:

   ```bash
   gc rig add /path/to/hello-gas-city --name hello-gas-city
   gc rig add /path/to/schreinerei --name schreinerei
   ```

4. Start or reload the city:

   ```bash
   gc start
   # or, if already running:
   gc reload
   ```

## Notes

The Gastown and maintenance packs are vendored under `assets/imports/` so this repository does not depend on `.gc/system` materialization paths. Update those vendored imports deliberately when upgrading Gas City pack behavior.

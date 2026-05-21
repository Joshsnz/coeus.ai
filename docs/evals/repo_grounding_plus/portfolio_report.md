# RepoGrounding-Eval: Codebase Context Benchmark

- Run ID: `20260521_094148`
- Dataset: `repo_grounding_core.jsonl`

## Headline results

- Stable scenario score: **12 / 12**
- Overall scenario score: **12 / 12**
- Repository QA turn score: **13 / 13**
- Bootstrap reliability: **12 / 12**
- Context retention: **13 / 13**
- False context refusals: **0**
- Repo route retention: **12 / 12**
- Repo follow-up route losses: **0**
- Artifact suppression: **13 / 13 clean**
- Internal artifact leaks: **0**
- Diff-route discipline: **13 / 13 clean**
- Patch/diff misroutes: **0**
- Negative grounding: **3 / 3**
- Semantic comparison: **1 / 1**
- Multi-turn continuity: **1 / 1**

## Benchmark framing

This is a codebase-context benchmark. It measures repository bootstrap, source-grounded QA, execution/data-flow tracing, semantic file comparison, negative grounding, multi-turn continuity, routing discipline, and internal artifact suppression.

## Failures

No failed scenarios. All benchmark assertions passed.
## Route-retention diagnostics

No repository-scoped turns were silently routed as general chat / no-repo.

## Scenario table

| Scenario | Status | Steps | Turns | Stress | Description |
|---|---:|---:|---:|---:|---|
| `core_startup_flow` | passed | 5 | 1 |  | Core repo-grounding: startup flow from entrypoint into the game loop. |
| `core_player_movement_path` | passed | 5 | 1 |  | Core repo-grounding: trace how a movement command changes the player's position. |
| `core_semantic_compare_game_world` | passed | 5 | 1 |  | Core repo-grounding: semantic comparison of game.py and world.py responsibilities. |
| `core_config_usage_trace` | passed | 5 | 1 |  | Core repo-grounding: trace map dimensions from constants into runtime use. |
| `core_input_normalization_flow` | passed | 5 | 1 |  | Core repo-grounding: trace user input normalization into command handling. |
| `core_rendering_path` | passed | 5 | 1 |  | Core repo-grounding: rendering logic with exact grid variables and player marker. |
| `core_player_lifecycle` | passed | 5 | 1 |  | Core repo-grounding: Player state and its use in the game loop. |
| `core_items_absence_in_runtime` | passed | 5 | 1 |  | Core negative grounding: item definitions exist but are not wired into runtime gameplay. |
| `core_no_save_load_negative_grounding` | passed | 5 | 1 |  | Core negative grounding: save/load persistence is absent. |
| `core_no_enemy_system_negative_grounding` | passed | 5 | 1 |  | Core negative grounding: enemies and combat mechanics are absent. |
| `core_multi_turn_movement_then_rendering` | passed | 6 | 2 |  | Core multi-turn continuity: movement summary followed by rendering comparison. |
| `core_internal_artifact_suppression` | passed | 5 | 1 |  | Core artifact suppression: answer should cite source files, not internal agent storage. |

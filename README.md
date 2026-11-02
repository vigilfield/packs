# Vigilfield packs

Ready-made Vigilfield rules, one folder per pack. A pack's `rules/` folder
holds rule files you apply as code, and a later `playbooks/` folder will hold
playbook files: <https://vigilfield.com/docs/detect/packs>.

| Pack | What it holds |
| --- | --- |
| [`core`](core/rules/) | Rules over signals from any source: the entity risk rule, and an anomaly followed by a sensitive action |

## Apply a pack

1. Copy the pack's `rules/` folder into the repository you keep your rule
   files in, for example as `rules/core/`.
2. Set your own table names in its queries. The `core` pack reads only
   `vf_signals` and `vf_alert_events`, so it needs no change.
3. Run its tests and apply it, with the GitHub Action, the GitLab template or
   `vf`:

   ```sh
   vf test  --dir rules
   vf plan  --scope github.com/acme/detections --dir rules
   vf apply --scope github.com/acme/detections --dir rules
   ```

The rules are then yours. A newer version of a pack is a change to its files:
compare it with your copy and apply what you want.

Apache-2.0: see [LICENSE](LICENSE).

# Claude Code Adapter

Use this file when porting the workflow to Claude Code or another agent runtime that supports explicit user-confirmation steps.

## Confirmation Behavior

Default full-report mode should behave like a `user_confirmation` workflow.

After product decomposition, stop and show:

- product tree, 3-5 levels
- proposed swimlanes for the main atlas
- preliminary top-3 bottlenecks
- major technology routes or design variants
- assumptions needing user confirmation

Then ask the user to confirm or adjust before building the final atlas.

## One-Pass Mode

If the user requests direct generation, skip the confirmation pause but include a short assumptions block in the non-render Render Brief.

Examples:

- "直接生成完整 MD"
- "不要中途确认"
- "one-pass"
- "batch mode"

## Portable Runtime Notes

- Keep the reusable workflow in `SKILL.md` and `references/`.
- Treat `agents/openai.yaml` as OpenAI/Codex UI metadata, not as the full portable schema.
- Use [io-contract.md](io-contract.md) for input fields, output fields, and examples.
- Preserve the distinction between visible report blocks and non-render production data.
- Do not show raw node/edge/evidence tables in the final HTML unless the user explicitly asks for a technical appendix.

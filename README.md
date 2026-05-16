## Rules for Creating Copilot Skills

1. **Description format:** Always begin the `description` frontmatter with "Use this skill when..." to clearly define the trigger condition.

2. **Non-exhaustive examples:** Never present examples as exhaustive lists. Always terminate them with "etc." or "and so on" to prevent the model from ignoring unlisted valid options.

3. **Conditional checks:** Do not mandate absolute environment checks. Use "if needed" or "when necessary" (e.g., "Query it first if needed:") to avoid unnecessary token waste.

4. **Precise terminology:** Adapt vocabulary to the specific domain. Do not blindly reuse standard legal or technical boilerplate (like "Software") if it misrepresents the actual content (like "Instructions" or "Prompts").

5. **Conciseness:** Keep instructions brief and direct. Omit the obvious. Do not contradict the base instructions (e.g., adding sycophancy).

6. **No hardcoded absolutes:** Avoid words like "always" or "never" unless it is a strict architectural constraint. Prefer pragmatic directives.

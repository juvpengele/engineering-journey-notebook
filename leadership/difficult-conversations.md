# Difficult Conversations

## Framework

When having a difficult conversation:
1. Name the specific behavior — not the person
2. Set the explicit standard going forward
3. Ask questions before drawing conclusions
4. Have sensitive conversations in private, in the person's preferred language if possible
5. Separate the diagnosis from the solution

## Situations & How I Handled Them

### Developer with Language Barrier
**Situation:** Developer was misunderstanding English tickets from the business, leading to wrong implementations.

**Diagnosis:** Language barrier, not a skill gap. He understands the code once requirements are clear.

**Actions taken:**
- Private conversation in French to name the issue without blame
- Introduced "restate before you build" step — he explains the root cause in French before coding
- Rolled out ticket confirmation with business as a team-wide practice (not singling him out)

**Lesson:** Always separate language gap from skill gap before drawing conclusions.

### Developer Using AI Without Understanding the Code
**Situation:** Developer was using AI to generate fixes without understanding root cause. PRs contained changes he couldn't explain.

**Diagnosis:** Relying on AI output without verifying understanding.

**Actions taken:**
- Set explicit team rule: every line pushed to prod must be understood and defensible
- Required bug replication tests to prove understanding before fix
- PR review now includes "walk me through what this change does and why"

**Lesson:** "This might fix it" is not acceptable for production code.

## Notes

<!-- Add notes as you encounter new situations -->

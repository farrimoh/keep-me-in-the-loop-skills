# Decision Levels

Use these levels to assess impact and propose boundaries during adoption. During operation, the accepted areas in `KEEP_ME_IN_THE_LOOP.md` determine which changes require a decision; these levels do not add approval requirements on their own.

| Level | Meaning | Guidance when defining boundaries |
| --- | --- | --- |
| 0 | Observation | Proceed |
| 1 | Routine, reversible implementation | Proceed and summarize |
| 2 | Component-design choice | Make visible; log when the project lists the area |
| 3 | Architecture or externally meaningful behavior | Log and request an explicit decision |
| 4 | Destructive, critical, scientific, or domain-significant change | Log, request a decision, and define recovery and verification |

Consider impact, uncertainty, scope, reversibility, and recovery cost rather than diff size. Several small edits may collectively become consequential.

Only an explicit human response makes a proposal accepted. Discussion, recommendation, silence, provisional work, or existing code does not.

Record only choices that help the human stay in control. Do not turn the decision log into a worklog.

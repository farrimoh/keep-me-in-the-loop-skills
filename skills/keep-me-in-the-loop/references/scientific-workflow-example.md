# Scientific Workflow Example

Use this example only to help define boundaries for scientific work. Adapt it to the actual project and obtain the scientist's explicit acceptance before writing it into project policy.

## Example areas requiring a decision

- New or modified energy terms or physical interactions
- Changes to simulation rules or scientific mechanisms
- Geometry or initialization changes that alter the model
- Domain assumptions or interpretations that affect conclusions
- Use of provisional results as established evidence

## Usually routine when meaning is preserved

- Expose an existing hard-coded value as a parameter
- Add parsers, observables, or parameter-sweep tooling
- Improve execution or performance
- Refactor while preserving equations, initialization, numerical meaning, and behavior

Escalate any routine-looking change if it can alter scientific meaning or conclusions. Classify the effect, not the apparent size of the code edit.

## Keep claims distinct

- **Observed behavior:** State only what a recorded run or measurement shows.
- **Proposed interpretation:** Label an explanation as a hypothesis pending evidence and review.
- **Accepted scientific decision:** Record the scientist's accepted interpretation or model change with scope and date.
- **Provisional result:** Do not use results from an unaccepted model change as established evidence.
- **Verified finding:** State the verification evidence and its limits without broadening the accepted claim.

# Thinking Frameworks

Three cross-cutting reasoning frameworks applied throughout the design thinking process. These are not phases — they are lenses applied within existing phases to sharpen reasoning, challenge assumptions, and resist unnecessary complexity.

---

## 1. First Principles Thinking

**Core idea:** Decompose any problem or assumption to its fundamental truths — things that are physically or logically necessary — and rebuild understanding from there. Strip away conventions, industry norms, and "how it's always been done."

### The Method

1. **State the belief:** Write down the assumption or conventional wisdom being examined.
2. **Ask "Why is this true?"** repeatedly until you hit bedrock — a constraint that cannot be removed without violating physics, logic, or a hard requirement.
3. **Separate bedrock from convention:**
   - **Bedrock:** "Users need to authenticate to access private data" — this is a security requirement.
   - **Convention:** "Authentication means a username/password form" — this is just one implementation.
4. **Rebuild from bedrock only:** Given only the unchallengeable constraints, what is the simplest, most direct path to the goal?

### Forcing Questions

- "What would we build if this problem had never been solved before?"
- "Which parts of the current approach exist because of genuine constraints vs. historical accident?"
- "What are we assuming because competitors do it, not because users need it?"
- "If we removed [X], what would actually break? What would users actually lose?"

### When to Apply

| Phase | Application |
|-------|-------------|
| Phase 0: Frame | Decompose the problem statement — is the stated problem the real problem, or a symptom? |
| Phase 2: Define | Challenge the POV statement — are we building on bedrock needs or conventional framing? |
| Phase 3: Ideate | Already exists as the `first-principles` creative lens — use this framework to deepen it |
| Phase 4: Prototype | Question every feature in the prototype — does it trace to a bedrock need? |

---

## 2. Socratic Questioning

**Core idea:** Use structured, probing questions to surface hidden assumptions, test the strength of reasoning, and deepen understanding. Not interrogation — collaborative inquiry that helps the thinker (user, persona, or the design itself) discover what they actually believe and why.

### The Six Question Types

1. **Clarification:** "What do you mean by [X]?" / "Can you give an example?"
   - Use when terms are vague or could mean different things to different people.

2. **Probing assumptions:** "What are we taking for granted here?" / "Why do we believe [X] is true?"
   - Use when a claim feels obvious — obvious claims hide the most dangerous assumptions.

3. **Probing evidence:** "What evidence supports this?" / "How do we know this isn't just our expectation?"
   - Use when conclusions are drawn from empathy data, user research, or persona responses.

4. **Exploring perspectives:** "What would [skeptical persona] say about this?" / "Who would disagree, and why?"
   - Use when the group seems aligned — alignment can mean convergence, not correctness.

5. **Examining consequences:** "If this is true, what follows?" / "What's the worst case if we're wrong about this?"
   - Use when evaluating design decisions, especially at shortlisting and prototyping.

6. **Questioning the question:** "Why is this the right question to ask?" / "What question should we be asking instead?"
   - Use when the framing itself feels off — sometimes the problem is the problem statement.

### Application Rules

- **One question at a time.** Let the answer land before asking the next.
- **Follow the thread.** The next question should respond to the answer, not follow a script.
- **No leading questions.** "Don't you think X?" is not Socratic — it's persuasion. Ask "What do you think about X?"
- **Genuine curiosity.** If you already know the answer, you're testing, not inquiring. Socratic questioning works when the questioner is genuinely exploring.

### When to Apply

| Phase | Application |
|-------|-------------|
| Phase 0: Frame | Replace informational scoping questions with probing ones — don't just ask "what's the problem?" but "why is this a problem now? What changed?" |
| User gates (all phases) | Don't just ask "Ready to proceed?" — probe: "What are you least confident about in what we just produced?" |
| Critic subagent | The critic's challenge process should follow Socratic structure — probing assumptions and evidence, not just listing objections |
| Phase 5: Test | Persona testers should probe the prototype Socratically — "Why would I use this instead of [current workaround]?" |

---

## 3. Occam's Razor

**Core idea:** Among competing solutions that adequately solve the problem, prefer the simplest one. Complexity must justify itself — every added element needs to earn its place by serving a real, evidenced user need.

### The Simplicity Test

For any design decision, feature, or solution concept, ask:

1. **Does removing this break the core value proposition?** If no, remove it.
2. **Does this serve an evidenced need?** Trace it to a specific persona quote, behavior, or pain point from Phase 1. If it only serves a hypothetical need, cut it.
3. **Is this the simplest way to deliver this value?** If a simpler mechanism achieves the same outcome, prefer it.
4. **Does the complexity earn its keep?** Sometimes complexity is necessary — but it must be proportional to the problem it solves.

### Complexity Red Flags

- A feature that serves only one persona's edge case but adds complexity for everyone
- A solution that requires users to learn new concepts or change existing habits without proportional benefit
- An architecture with more moving parts than the problem has dimensions
- "Future-proofing" that adds complexity now for benefits that may never materialize
- Ideas that combine multiple mechanisms when one would suffice

### The Razor in Practice

| Situation | Apply Occam's Razor |
|-----------|-------------------|
| Two ideas solve the same HMW question equally well | Prefer the one with fewer moving parts |
| A prototype feature doesn't trace to empathy evidence | Cut it — it's solving an imagined problem |
| The prototype has grown complex during iteration | Audit: which elements serve bedrock needs vs. accumulated "nice to haves"? |
| Multiple HMW questions could be collapsed into one | Collapse them — the simpler framing is usually more honest |
| Critic identifies over-engineering | Trust the razor — simplify unless evidence justifies the complexity |

### When to Apply

| Phase | Application |
|-------|-------------|
| Phase 2: Define | Are HMW questions over-specified? Could fewer, simpler questions cover the same ground? |
| Phase 3: Ideate | Shortlisting filter — when two ideas are comparable, prefer the simpler one |
| Phase 4: Prototype | Every prototype element must trace to evidence. Audit for unnecessary complexity. |
| Phase 5: Test | If personas struggle with complexity, the razor says simplify, not train |
| Critic (all phases) | The critic should flag Occam's Razor violations — solutions more complex than the problem requires |

---

## How the Frameworks Interact

The three frameworks reinforce each other:

- **First Principles** strips the problem to bedrock. **Occam's Razor** strips the solution to essentials. Together they prevent both problem-bloat and solution-bloat.
- **Socratic Questioning** is the engine that drives both — it's how you actually probe assumptions (first principles) and challenge unnecessary complexity (Occam's razor).
- When the critic applies all three: it decomposes claims to fundamentals (first principles), probes whether evidence supports them (Socratic), and flags when the proposed solution is more complex than the evidence warrants (Occam's razor).

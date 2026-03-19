Run the full crypto analysis pipeline for the given asset: $ARGUMENTS

Execute the agents in this sequence, passing all prior outputs to each subsequent agent:

---

**Step 1 — Statistics Agent**
Use the `statistics-agent` to analyze quantitative market data for $ARGUMENTS.
Produce: `## Statistics Report`

---

**Step 2 — Fact Agent**
Use the `fact-agent` to extract objective facts about $ARGUMENTS.
Produce: `## Facts Report`

---

**Step 3 — Fact Reasoning Agent**
Use the `fact-reasoning-agent` with the `## Facts Report` as input.
Produce: `## Fact Reasoning Report`

---

**Step 4 — Subjectivity Agent**
Use the `subjectivity-agent` to capture sentiment and narrative signals for $ARGUMENTS.
Produce: `## Subjectivity Report`

---

**Step 5 — Subjectivity Reasoning Agent**
Use the `subjectivity-reasoning-agent` with the `## Subjectivity Report` as input.
Produce: `## Subjectivity Reasoning Report`

---

**Step 6 — Trade Agent**
Use the `trade-agent` with the Statistics Report, Fact Reasoning Report, and Subjectivity Reasoning Report as input.
Produce: `## Trade Decision`

---

**Step 7 — Reflection Agent**
Use the `reflection-agent` with ALL prior reports as input.
Produce: `## Reflection Report` with final amended recommendation.

---

After all steps complete, output a **Pipeline Summary**:

- Asset analyzed
- Final Trade Decision
- Reflection amendment (CONFIRM / REVISE / ABORT)
- Top 3 key drivers
- Top 2 risks to watch

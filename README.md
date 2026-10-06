# Master Prompt — Mock DSAT Practice Paper (Brain & Mind Academy · Abhyas)

Use this prompt every time a new source paper is shared. Every paper from now on is built to the **standard Digital SAT format** below. The original paper's title is not used; every paper is titled **Mock DSAT Practice Paper N**.

---

## 1. The prompt (copy-paste)

> Build **Mock DSAT Practice Paper [N]** for Brain & Mind Academy (Abhyas Practice Series) from the attached source paper, following the Brain & Mind Master Prompt for Mock DSAT papers.
>
> 1. **Map the source to the standard Digital SAT:** Reading & Writing Module 1 and Module 2 (27 questions each, 32 min), a 10-minute break, then Math Module 1 and Module 2 (22 questions each, 35 min). Total 98 questions, 2 h 14 min.
> 2. **Tag every question** with section, module, domain, skill, application type, difficulty and question number in the source.
> 3. **Use the source answer key** (or solve and flag if none), write a worked explanation for every question, and verify every answer.
> 4. **Build one self-contained HTML file** in the Abhyas Bluebook-style engine, with student sign-in, timers, tools and a full Score Gap Report.
> 5. **Check the domain counts** against the standard spec, run an all-correct browser test plus a mixed-answer test, and deliver the file.
>
> Flag anything that doesn't match the spec instead of silently changing it.

---

## 2. Standard Digital SAT pattern (College Board)

| Section | Module | Questions | Time | Notes |
|---|---|---|---|---|
| Reading & Writing | Module 1 | 27 | 32 min | Broad mix of easy, medium, hard |
| Reading & Writing | Module 2 | 27 | 32 min | Harder or easier (adaptive) |
| — | Break | — | 10 min | Between the two sections |
| Math | Module 1 | 22 | 35 min | Broad mix of easy, medium, hard |
| Math | Module 2 | 22 | 35 min | Harder or easier (adaptive) |
| **Total** | 4 modules | **98** | **134 min** | Score 400–1600 (RW 200–800, Math 200–800) |

- On the real test, 2 questions per module are unscored pretest items. Brain & Mind mocks score all questions.
- **Timer:** each module has its own countdown and auto-submits at 0:00. Students cannot return to a submitted module.
- **Adaptive routing:**
  - If the source gives one fixed Module 2 (as College Board's linear PDF practice tests do), the mock runs **linear**: everyone gets the same Module 2.
  - If the source gives both a harder and an easier Module 2, the mock routes on Module 1 performance.
  - Always state which mode the paper uses.

### 2a. Reading & Writing (54 questions)

- Every question has **one short passage (25–150 words) or a passage pair**, followed by **one 4-option multiple-choice question**.
- Within each module, questions are grouped by skill in the order below, and each group runs easiest to hardest.

| Order | Domain | Share (≈ of 54) | Skills (topic tags) |
|---|---|---|---|
| 1 | **Craft and Structure** | ≈28% (13–15) | Words in Context · Text Structure and Purpose · Cross-Text Connections |
| 2 | **Information and Ideas** | ≈26% (12–14) | Central Ideas and Details · Command of Evidence: Textual · Command of Evidence: Quantitative (tables/graphs) · Inferences |
| 3 | **Standard English Conventions** | ≈26% (11–15) | Boundaries (punctuation, sentence joining) · Form, Structure, and Sense (agreement, verb tense, pronouns, modifiers, plurals/possessives) |
| 4 | **Expression of Ideas** | ≈20% (8–12) | Rhetorical Synthesis (student notes) · Transitions |

### 2b. Math (44 questions)

- Calculator allowed on every question (built-in Desmos graphing calculator plus a reference sheet).
- About **75% multiple choice (4 options)** and **25% student-produced response** (SPR, typed answer).
- About **30% are in context**: a word problem set in science, social studies or real life.
- Within each module, questions are mixed by domain and run easiest to hardest.

| Domain | Share (≈ of 44) | Skills (topic tags) |
|---|---|---|
| **Algebra** | ≈35% (13–15) | Linear equations in 1 variable · Linear equations in 2 variables · Linear functions · Systems of 2 linear equations · Linear inequalities |
| **Advanced Math** | ≈35% (13–15) | Equivalent expressions · Nonlinear equations & systems · Nonlinear functions |
| **Problem-Solving & Data Analysis** | ≈15% (5–7) | Ratios, rates, proportions & units · Percentages · One-variable data · Two-variable data & scatterplots · Probability & conditional probability · Inference from samples & margin of error · Evaluating statistical claims |
| **Geometry & Trigonometry** | ≈15% (5–7) | Area & volume · Lines, angles & triangles · Right triangles & trigonometry · Circles |

**SPR answer rules** (shown on screen, as in Bluebook):
- Up to 5 characters for a positive answer, 6 for a negative one.
- Fractions or decimals are accepted. Decimals that don't fit can be truncated or rounded.
- Mixed numbers must be entered as improper fractions or decimals. No symbols.
- If more than one answer is correct, enter one of them.


### 2c. Mapping College Board "nondigital" (paper) practice tests

College Board's PDF practice tests for students taking the digital SAT on paper have **33 / 33 / 27 / 27** questions (RW 39 min and Math 43 min per module). To keep every mock at the standard length:
- **Select 27 / 27 / 22 / 22** in the original order. Drop items evenly across each domain so the counts land in the ranges above (e.g. RW per module: Craft & Structure 7, Information & Ideas 7, Conventions 7, Expression of Ideas 6; Math overall: Algebra 15, Advanced Math 15, PSDA 7, Geometry & Trig 7, about 11 SPR).
- **Scoring:** scale the raw score to the paper version's question count (RW × 66/54, Math × 54/44, rounded), then apply the College Board raw-to-scale table from that test's scoring guide.
- Use the keys from the scoring guide and College Board's answer explanations for RW. Keep the 22 unused questions on file for revision sets.

---

## 3. Tagging scheme (drives the analysis)

Every question carries these fields:

| Field | Values |
|---|---|
| `sec` | RW · M |
| `mod` | 1 · 2 |
| `dom` | RW: CAS, INI, SEC, EOI · Math: ALG, ADV, PSDA, GEO |
| `sk` | the skill codes in 2a / 2b |
| `app` (application type) | **Math:** F = Fluency (procedure) · C = Conceptual understanding · A = Application in context. **RW:** R = Comprehension (literal: what the text says) · N = Analysis & Inference (reasoning, purpose, evidence) · E = Editing & Revision (applying a convention or rhetorical goal) |
| `diff` | E · M · H (source difficulty if published, otherwise position in its skill group) |
| `type` | mcq · spr |
| `src` | question number in the source, e.g. "RW M1 Q7" |
| `ctx` | 1 if in context (Math) |

---

## 4. Build rules

1. **Title and branding:**
   - Title: **"Mock DSAT Practice Paper N"**. Never the source's title.
   - Branding: Brain & Mind Academy · Abhyas Practice Series, in the navy and gold theme.
   - Footer credits the source and notes that SAT is a College Board trademark.
2. **Test engine (Bluebook-style):**
   - Student sign-in (name, roll number, PIN), a directions screen per section, and a 10-minute break screen between RW and Math.
   - Per-module countdown with Hide, Mark for Review, answer eliminator (ABC), question navigator, and a "Check your work" page before each submit.
   - Save & exit / resume.
   - Math only: Desmos, scientific calculator and reference sheet.
   - RW: highlighter and annotation on the passage, plus the scratchpad.
3. **Layout:**
   - RW shows the passage on the left and the question on the right (stacked on phones).
   - Math SPR shows the entry directions beside the question.
4. **Content fidelity:**
   - Transcribe questions exactly.
   - Rebuild tables as HTML tables, and crop figures and graphs from the source at high resolution.
   - Never change a key without flagging it.
5. **Copyright check:** a literary or poetry excerpt in an RW passage is reproduced only if the work is public domain (published before 1929). Otherwise, replace it with an original Brain & Mind passage that tests the same skill at the same difficulty, and flag the swap.
6. **Answer keys:**
   - Use the source key.
   - If there is no key, solve every question, verify each one (code for numeric answers, a second read for RW), and flag the paper "key prepared by Brain & Mind".
7. **Explanations:** every question gets a short worked explanation, and RW explanations say why each wrong choice fails.

---

## 5. Score Gap Report (Brain & Mind format)

Shown instantly after the final module, printable or saved as PDF, and listed in the student's history.

1. **Score summary:**
   - Estimated total (400–1600) and section scores (200–800 each), shown as a band.
   - Accuracy, correct per module, time used per module, and the routing path.
   - Conversion uses the source's official raw-to-scale table when there is one. Otherwise it uses a linear estimate, labelled as such.
2. **Chapter / domain-wise analysis:**
   - One pie of marks earned by domain for RW (4 domains) and one for Math (4 domains).
   - A table of correct / total / accuracy against the SAT weight.
3. **Topic / skill-wise analysis:** a card per domain with a correct / incorrect / omitted pie and mini-pies for each skill.
4. **Application-based analysis:**
   - Math: a pie of Fluency / Conceptual / Application-in-context.
   - RW: a pie of Comprehension / Analysis & Inference / Editing & Revision.
   - Each category gets its own card and pie.
5. **Difficulty and format:** pies for Easy, Medium and Hard, and for MCQ versus SPR (Math).
6. **Score gap / focus plan:** skills ranked by accuracy and marks lost (High priority / Revise / Strength), plus a counsellor note.
7. **Question-by-question review:**
   - Filters for All / Incorrect / Omitted / Correct.
   - Each entry shows the student's answer, the key, tags and the explanation.

---

## 6. Quality checks before delivery

- [ ] Counts are 27 / 27 / 22 / 22, and the domain counts fall within the ranges in section 2 (any deviation is flagged).
- [ ] RW questions appear in domain order within each module. Math questions run easy to hard.
- [ ] Every figure, table and graph renders and is legible on a phone.
- [ ] Automated run answering every question with the key gives full marks, and a mixed run gives the expected report numbers.
- [ ] Light and dark mode both work, with no horizontal scroll at phone width.
- [ ] File named `mock-dsat-practice-paper-N.html`, delivered with a short note on mode (linear or adaptive), key source and any flags.

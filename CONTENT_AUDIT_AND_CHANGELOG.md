# Content audit and change log

## Goal
Reduce generic, template-driven teaching and make each topic teach a specific concept, show an application, identify a limitation, and invite analysis.

## Coverage
- 72 topic entries across the original chapter outline.
- 68 distinct titles; repeated “Conclusions” titles account for the difference.
- 7 specialist lessons use longer, worked explanations.
- 61 other distinct titles now have topic-specific core explanation, example/application, critical limitation, learner exercise, and further-reading guidance.

## Examples of substantive changes
- Context-free grammar: formal components, derivation, coverage, overgeneration, and ambiguity.
- Unification: compatible and conflicting feature structures.
- HPSG: typed feature structures, lexical information, valence, and constraints.
- Meaning–Text Theory: clarification of the framework and warning not to conflate it with neural Transformer architecture.
- Dependency representation: a worked example and annotation-scheme caveat.
- Spanish NLP: morphology, clitics, regional variation, and experimental reporting.
- Homonymy/polysemy: sense-inventory decisions and their effect on evaluation.
- Applied systems: task-specific examples and evaluation considerations across spelling, retrieval, summarization, translation, interfaces, extraction, and generation.
- Models and theories: assumptions, empirical tests, scope, limitations, and comparisons.

## Scholarly use
Further-reading links point to starting resources including Jurafsky and Martin's *Speech and Language Processing*, the ACL Anthology, and Universal Dependencies. These are not a substitute for chapter-specific citations. Framework-specific claims should cite primary literature. Verify all bibliographic metadata, versions, licensing, and current resource status before formal publication.

## Validation status
- JavaScript parser check: passed with Node.js `--check`.
- Topic coverage check: all distinct lesson titles resolve to specialist or topic-specific content.
- ZIP integrity: checked after packaging.
- Android build: not run (no Gradle executable or wrapper available in the environment).
- Runtime/device testing: not performed.
- Independent subject-matter review: not performed.

## Known remaining limitations
1. Repeated “Conclusions” titles use a common synthesis lesson instead of chapter-specific conclusions.
2. Further-reading recommendations are directional, not complete citations attached to every claim.
3. Some historical/theoretical summaries remain introductory and should be checked by a subject-matter reviewer before academic use.
4. The content should not be advertised as peer-reviewed or as a comprehensive scholarly textbook until expert review and Android/runtime QA are completed.

## Build/app fixes (October 20, 2026)
- External links (`target="_blank"`) now open in the device browser instead of failing inside the WebView.
- Content is padded clear of the status/navigation bars, so the top bar stays tappable on Android 15 (edge-to-edge is forced at targetSdk 35).
- Workflow: 30-minute timeout and `--stacktrace` for easier debugging if a build fails.
- Gradle: lint no longer aborts a debug build.
- Re-verified: all 72 topics render without errors, all button handlers and element IDs resolve.

## 2026-10-22 — Chapter-ordered extended content and revision Q&A
- Kept the existing chapter topics and detailed lesson material in place.
- Appended matching sections from the extended study guide beneath relevant existing topic lessons where the guide contains a matching heading.
- Added a collapsible Questions & Answers panel at the end of each chapter; chapter ranges follow the supplied question bank's structure.
- Corrected question-bank parsing to retain full essay prompts and their source-provided answer outlines (notably Questions 366–390).
- Added clearly labelled suggested answers for the 12 final revision-checklist prompts, which are not answered in the source file.
- Preserved offline use; all study content is bundled in the app assets.

## 2026-10-22 — Expanded Exercises MCQ bank
- Expanded the Exercises multiple-choice bank from 14 starter questions to 311 total MCQs (14 original questions plus 297 generated across 99 core concepts).
- Coverage includes linguistic levels, NLP tasks, ambiguity, morphology, CFGs, dependency and constraint-based grammars, Meaning–Text mapping, corpora and lexicons, evaluation, data leakage, generalization, resources, and applications.
- Added previous/next navigation, random MCQ selection, saved answers while navigating, answer explanations, and a live count/progress indicator.
- All questions and explanations are bundled in the offline HTML asset.
- Validation: extracted embedded JavaScript passes `node --check`; ZIP integrity passes. Android build and device runtime tests have not been performed.

## Fixes (October 22, 2026, after the expanded MCQ update)
- MCQ generator: the 99 concept entries were written as Python-style tuples `(...)`, which JavaScript reads as a single string, so the 297 generated questions would have shown garbled text. They are now proper arrays. Verified: 99 concepts, 297 generated + 14 original = 311 MCQs, every question has 4 distinct options and a valid answer, correct answers spread evenly across A-D.
- "Which example illustrates..." questions now use other concepts' examples as wrong options instead of mismatched definitions.
- Android Back button returns to Home first and only exits the app from Home.
- Saved progress/bookmarks load safely: corrupted local storage no longer stops the app from starting.
- Question bank: supplemental items (421-432) reuse numbers 1-12, so searching a number returns only the main item, and the Random button lands on the correct card for supplemental items.
- Android build still not run in this environment; GitHub Actions performs the real build.

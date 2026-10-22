# Computational Linguistics — Android learning app

A blue-and-white mobile learning app inspired by the supplied reference screenshots. It includes all requested front-matter headings, five chapters, expanded learning notes, worked examples, key-point checklists, review questions, exam prompts, external resources, bookmarks, and local reading-progress tracking.

## Build an APK with GitHub Actions

1. Create a repository at https://github.com/new.
2. Extract this ZIP on your computer.
3. Upload the **contents** of the extracted folder to the repository root (including the hidden `.github` folder), then commit to the `main` branch.
4. Open **Actions** in your repository. If asked, enable GitHub Actions.
5. Choose **Build Android APK** and wait for a successful run.
6. Open the run and download the `computational-linguistics-debug-apk` artifact.
7. Extract the downloaded artifact to get `app-debug.apk`. Transfer it to your Android device and install it. You may need to allow installs from your file manager or browser.

You can also start a build manually using **Actions → Build Android APK → Run workflow**.

## Local build

Requirements: JDK 17 and Gradle 8.9. Run `gradle assembleDebug`. The APK will be at `app/build/outputs/apk/debug/app-debug.apk`.

## Notes

- The ZIP contains project source and a workflow; GitHub Actions compiles the APK after upload.
- This is a debug APK for testing, not a Play Store-signed release.
- Core lessons work offline. External resource links need an internet connection.
- Lesson descriptions are original educational explanations, not a reproduction of the full source book.

- The app icon lives in `app/src/main/res/mipmap-*`. `icon-512.png` in the project root is a 512 px copy for reuse (e.g. a GitHub social preview).


## Content quality improvements

This revision strengthens the educational content in selected high-priority lessons:
- Worked context-free grammar derivation, ambiguity, and limitations.
- Step-by-step feature unification, including a conflict case.
- A more precise, explicitly schematic introduction to HPSG.
- A clarification that Meaning–Text Theory is distinct from neural Transformer architectures.
- A worked dependency analysis with annotation-scheme caveats.
- A more evidence-oriented introduction to Spanish NLP, including evaluation design.
- A discussion of homonymy/polysemy and the effect of sense inventories on evaluation.
- Additional applied quiz questions and a scholarly starting-points section.

### Scope and limitations

This remains an introductory learning companion, not a peer-reviewed textbook or a substitute for primary literature. Some lesson summaries outside the expanded lessons remain concise. The examples are instructional and simplified; they should not be treated as complete formal analyses or empirical research findings. Before academic citation or publication, verify bibliographic details, the current status and licensing of linked resources, and all claims against the cited primary sources.

### Suggested next validation steps

1. Build the Android app with the repository's Gradle workflow.
2. Test navigation, lesson rendering, quiz answers, bookmarks, and progress persistence on a device or emulator.
3. Have a computational linguistics instructor review theoretical accuracy and exercise solutions.
4. Add versioned references and citations directly to each remaining substantive lesson.
5. Test accessibility, offline behavior, and external links.


## Comprehensive content revision (October 2026)

The lesson renderer now provides topic-specific instructional material for all 68 distinct lesson titles (72 topic entries, including repeated chapter conclusion headings). The 7 expanded specialist lessons are retained, and the other 61 distinct titles have dedicated core explanations, worked applications/examples, critical limitations, learner tasks, and further-reading guidance. Repeated “Conclusions” headings share a synthesis-oriented lesson; this is a known content limitation to improve by making each conclusion chapter-specific.

### Content integrity notes
- The app is an introductory learning companion, not an independently peer-reviewed textbook.
- Examples are schematic and should not be mistaken for complete linguistic analyses or empirical results.
- Links to textbooks, ACL papers, and Universal Dependencies are starting points, not citations for every claim. Primary sources should be cited for framework-specific statements.
- The online *Speech and Language Processing* manuscript is a living draft; cite the version/date actually consulted.
- The HPSG, Meaning–Text Theory, Spanish NLP, and historical-framework sections explicitly call for framework-specific sources and caution against conflating distinct approaches.
- No claim is made that the Android APK has been built or runtime-tested in this environment.

### Validation performed for this revision
- JavaScript syntax check (`node --check`): passed.
- Coverage check: all 68 distinct topic titles map to a specialist or topic-specific lesson.
- ZIP integrity check: performed on the final archive.
- Android Gradle build and on-device WebView testing: not performed because a Gradle executable/wrapper is not available in the working environment.


## Integrated offline study library

This revision adds the supplied `Computational_Linguistics_Detailed_Study_Guide.txt` and `Computational_Linguistics_350_Questions_and_Answers.txt` content to the Android WebView app as an offline study guide and searchable question bank. The original guide text is embedded without rewriting, with sections split at the supplied separator lines for navigation. The question-bank view reports the number of numbered entries and which entries contain explicit answers; it does not invent missing answers. Existing chapters, quick quiz, bookmarks, and local reading progress are retained.

The source text files are also included in `study-materials/` for convenient editing.


## Chapter-integrated extended study materials

The detailed study guide is now appended beneath matching existing topic lessons where an exact heading is available; the original lessons are retained. Each chapter card also has a collapsible Questions & Answers area at its end. Question ranges follow the supplied question file's structure, and cumulative application/definition/exam items are grouped at the end of Chapter V. If the source has no answer for an item, the app says so rather than inventing one. All material is bundled locally for offline use.

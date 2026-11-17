# Testing the “list of options”: can a model compile such a list itself?

*Translated from Russian. File names in code font that are not in this folder — `checklist*.md`, `variants.csv`, `axes-summary.*`, `synthesis/…`, `../ChatGPT/test-E.md`, `E-roles/_synthesis.md`, `E-roles/ideas/_review.md`, `8.md` — are working files of the analysis, in Russian, and are not published. The labels of axes, groups and predictions are transliterated from the Russian letters.*

**The human researcher's question (15 November).** Can a model compile a list of variants like the one in the [bifurcation-of-options appendix](../../report/bifurcation-options/README.md#part-1-bifurcation-of-options), simply while carrying out the task: “here is the source; propose all possible visualisations”? To simplify matters, styles are drawn from a fixed list. In the appendix itself, the researcher says they do not think any model can generate the entire list “simply in the course of reasoning”.

**My answer in the chat on 15 November** (recorded in `synthesis/README.md`): as a list, largely yes; in one pass, no. There are three reasons:
- what comes first is the head of the distribution, and the models share it;
- some items arose from pictures that did not exist before generation;
- the value of the list lies in the researcher's notes, which were obtained from failures.

The test measures this against the list itself: 69 items with source marks, three items from the “What was never used” section, and 18 researcher's notes.

## Design

| Arm | What the model receives | Turns |
|---|---|---|
| `A-styles` | the joke and a fixed list of 14 styles | 3 |
| `B-open` | the joke, any style | 1 |

- **Turn 1** — the researcher's question, almost verbatim. This is the main result.
- **Variant format** (researcher's clarification, 15 November): two or three sentences describing what is depicted and in what style. This makes models compete on the number of variants rather than the length of descriptions, and makes their answers comparable. The cost: small details (breed, customers, objects) fit less easily into two or three sentences; turn 3 collects these.
- **Turn 2** — “Are these all the possible variants? Add what you missed, in the same format.” This tests the stopping criterion: does the model know what is missing from its list?
- **Turn 3** — models receive the axes underlying the researcher's list and are asked to flag risks. This is the upper bound. Whatever is still absent here is something the model cannot retrieve in a single conversation without generating images.
- **Arm B** — a control: what does the style list itself contribute?

**The style list** was assembled from traditions used or proposed in the project: manga, ukiyo-e, Chōjū-giga, *Krokodil*, Herblock, Sempé and Reiser, Quentin Blake, Rachyov and Chizhikov, Pirosmani, noir, the old masters, Degas, Egypt, xkcd. Traditions are named rather than artists. This favours the model: style-linked items (a dukhan, a research institute, an Edo circus, Chōjū-giga, Egypt) are within reach. Artists' names are withheld so as not to suggest the project's specific solutions.

## Procedure

1. **Models:** ChatGPT, Claude, Gemini, DeepSeek. A new chat for each arm.
2. **No memory or project.** ChatGPT: temporary chat. Claude: outside a project, with memory off. Gemini: no saved information or personal context. DeepSeek: new chat. Some models may have the experiment itself in memory.
3. **Turn web search off.** With search, a model may find the project's published material: in test 74, Gemini and DeepSeek found the researcher's question on Philosophy SE.
4. **Arm A:** send the messages in `A-styles/_prompt.md` in sequence, each after the preceding answer is complete. Add no comments between turns. **Arm B:** one message from `B-open/_prompt.md`.
5. **Answers:** save verbatim in `<arm>/<model>.md`; in arm A, under “Turn 1”, “Turn 2”, and “Turn 3” headings. Put the mode on the first line: `<!--Mode: …-->`. If the model nevertheless draws a picture, save it alongside the answer and record this, but exclude it from the coding.

## Coding

The coding sheet is `checklist.md`.
- An item counts if the answer contains the same idea, in any wording. The codes are explained at the top of the sheet.
- A turn-1 answer usually consists of complete concepts combining reading, setting, and style. Each concept is broken down into items.
- A note counts only if the model identifies the same risk or reason, rather than merely the option itself.
- Record separately the number of variants in turn 1, whether the default is among the first three, repetitions, and new items absent from the researcher's list.

Ideally, I should not be the sole coder: the predictions below are mine. If I do the coding, the researcher checks every “±” and every item in groups G and K.

## My predictions (15 November, before the runs)

These are weak predictions: my predictions in this line of work have already failed three times.

- **P1.** Arm A, turn 1: for three of the four models, the first variant is the default reading (a naïve cat, a circus in a thought bubble, or a circus ring).
- **P2.** Group D (50 items): after turn 1, each model covers no more than one third; after turn 3, three of the four cover at least half.
- **P3.** Items originating in specific pictures: K9 bakeneko; K13 “there is no cat”; V3 “is it AI-generated?”; M3 kanmidokoro as distinct from kissaten. Each model has no more than one of the four, even after turn 3. The likeliest exception is bakeneko: with ukiyo-e on the list, a model may reach it through Kuniyoshi.
- **P4.** By turn 3, three of the four models have the self-interested waiter (O2). In the project, the image generator introduced him; no virtual director proposed him. If this prediction holds, it supports a distinction between two modes: when listing possibilities, the model names things it did not offer when carrying out the task.
- **P5.** By turn 3, three of the four models have at least two of the three “never used” items (N1–N3). The reasoning is the same.
- **P6.** Turn 2: all four add at least five new items, and none says the list is complete.
- **P7.** Style-linked items (M5 dukhan, M6 and Ts6 research institute, Ts8 Edo circus, E6 Chōjū-giga, K12 and M7 Egypt) occur more often in A than in B. The difference in readings of the cat (K1–K13) is small.
- **P8.** Notes: by turn 3, each model has no more than six of the 18, although turn 3 explicitly asks it to flag risks.

## What the results would mean

- **P1 holds** — the head of the distribution comes first, as with Wright for the cave and with lists of films about cinema.
- **P2 holds in turn 3 but not turn 1** — a model can compile such a list, but not “in the course of the task”: it needs a supplied structure. The curator devised that structure only after the work.
- **P3 fails** (several models produce two or more picture-derived items) — my second reason is weaker than I thought: some “glitch-derived” items can be inferred from the source and styles.
- **P4 and P5 hold** — listing and carrying out the task really are different modes.
- **P8 fails** — the third reason is weaker: the model supplies the notes without experience of generation.
- **Many new items** — a separate result: the researcher's list expands.

## Results (15 November)

**How the runs were conducted.** Departures from the plan:
- DeepSeek was not run. Three models: ChatGPT (GPT 6 High), Claude (Fable 5.2 Extra), Gemini (Argon 4 High).
- Arm A used one message: styles and axes were provided together; there was no turn 2 (“is that everything?”) or request to flag risks. A is therefore “turn 1 plus turn 3 without risks”, and comparing A with B measures styles and axes together, not styles separately.
- The style list contains 13 traditions, without emakimono.
- Variant format: “in a few sentences: the visualisation concept, what is depicted and in what style”.

The coding is in `checklist.md`. All variants are in `variants.csv`: semicolon-delimited, UTF-8 with BOM. As of 16 November, it contains 491 rows: arms A and B (337), and arm C (154: ChatGPT 104, Claude 34, Gemini 16; ChatGPT numbers such as “5.3” identify the style and variant). Each variant has a cluster based on the substance of the concept, references to other occurrences of that cluster, my ten best and related variants, and overlaps with the project. The clusters and markings are mine and should be checked. Since 16 November, the file also has an “experience notes” column: what the project already knows about such moves — “breaks the joke”, “image generator default”, “a road to AI slop”, what breeds mean, where the laptop glitches, how AI readers assess danger. The notes come from the researcher's options list, the working thread on the cat's readings and details (not published) and report 07; the source is given in parentheses. They are assigned in three ways: by cluster, by words in the description (breed, sex, waistcoat, laptop, thought bubble, badge, poster), and manually for five variants in which the circus really needs a programmer. There are notes on 239 of the 491 rows. A script assigns the word-based notes, so false positives are possible: for instance, “ginger tomcat” was attached to still life A-Cl-34 through “a ginger hair”. Without such notes, a model choosing from the file evaluates moves by its own criteria (see “Which screenwriter's axes were added compared with A”). The synthesis of the axes themselves across all sources (the researcher's list, prompt A, the models' own axes in A, B and C, and arm D) is in `axes-summary.md` and `axes-summary.csv`. It contains 48 common axes in six layers, from script to visual language, and 19 boundary axes where visual tradition itself settles a question of the script.

**Main findings.**
1. **Without axes, a model lists ways of drawing, not readings.** In arm B, Claude has 50 variants and ChatGPT 144, mostly formats, angles and techniques: strips of 2–9 panels, a webtoon, the waiter's point of view, pixel art, a flowchart, a CV, correspondence. There are almost no readings of the cat beyond the default.
2. **With axes, the list fills about halfway.** In arm A, one model fully matched 11–18 of group D's 50 items; the three combined matched 25. Across all 69 items, the union of the three models is 37. All have the image generator defaults (5 out of 5), and all three “never used” items occurred in at least one model's answer.
3. **The curator supplied the axes.** Arm A received the list's structure in the prompt: readings, characters, setting, before and after, details. Without it, in B, the models did not construct it. This run answers the researcher's question as follows: “in the course of the task”, a model produces a catalogue of forms; it fills a catalogue of readings and details roughly halfway if supplied with the axes. **Correction, 16 November, following arm D.** When asked, models construct axes themselves. Claude covered 13 of the researcher's 14 sections (only breed was missing), ChatGPT 7 fully and 5 partly, Gemini 6 and 3. B simply did not ask for axes. The curator's contribution lies in deciding to ask about axes and in the notes, not in the structure itself.
4. **What came from pictures is not retrieved.** “There is no cat”, “is it AI-generated?”, kissaten and kanmidokoro appeared in none of the answers. All three gave the same Japanese establishment: an Edo-period teahouse. The exception I predicted was bakeneko: Claude's nekomata and Gemini's Kuniyoshi-like “shapeshifter cat”. None of the 18 researcher's notes was matched in full; a model matched up to four partly.
5. **The head of the distribution is shared.** All three begin with the default in both arms. All three have “two circuses”: a diptych or two thought bubbles showing the waiter's circus and the cat's; I previously considered this ChatGPT's signature. In A, *Krokodil* means the uncle's patronage (blat) and protection for all three, Egypt means a feline scribe or calculator, and noir a black cat in the rain. Claude and ChatGPT independently produced a still life with a tiny reflection of the open-mouthed waiter in the side of a coffee pot.
6. **Breeds have meanings, but not the researcher's meanings.** Siamese, black, tortoiseshell, British and ginger cats appear in almost all the answers. Claude assigns roles to breeds: Siamese — “haughtiness”, Persian — “a lady”, Sphynx — “a burned-out senior developer”, calico — “Japanese good luck”. But none mentions racial caricature, “tortoiseshell means she”, or Garfield. (The heading used to read “Breeds are named, meanings are not”; corrected following ChatGPT's review on 16 November.)
7. **Sex follows the role.** The joke is supplied in Russian; its protagonist is a female cat. But when she becomes an engineer on a business trip or a traveller at a station (ChatGPT), a noir detective, a sacred Egyptian animal or a scholar among the Dutch (Gemini), she becomes a *kot*, a male cat. Claude does not do this. It is the mechanism from the thread on word determinism: the role brings its grammatical gender. **Correction, 16 November, following arm C.** No model uses *kot* in C; in B it appears once each in ChatGPT and Gemini; in A, five times in ChatGPT and eight in Gemini. The axis in prompt A explicitly asked about “the cat (breed, colour, sex…)”, and ChatGPT's axes table even listed “a male programmer cat, a female programmer cat”. Thus the prompt most likely suggested changing sex, while the role determined who became male: the engineer, traveller, detective or scholar.
8. **The grid determines the number of variants.** ChatGPT has 78 = 6 × 13 styles and 144 = 12 × 12: list size follows the chosen structure rather than the material. In B, ChatGPT itself says that “it is literally impossible to list all possible variants”.
9. **There are new items, but not all are new to the project.** I initially called Claude's Manet *A Bar at the Folies-Bergère* the best new item (the trapeze artist's legs: “the circus is already here, only the cat has her back to it”). The researcher corrected me: that variant already exists. Director B — Claude with the v17-fork prompt — proposed it, with the same key, the gymnast's legs as a hint at the circus; Gemini generated it on 20 October (the image is in director B's working folder, not published). This makes it the head of Claude's own distribution for this joke: a month later, without a persona or a search procedure, it reached the same painting through the same detail — like Wright for the cave. Claude's coworking space also already existed in v17's *The Calling of Saint Matthew*. “New” must be checked against the whole project, not just the list. The selection is in `checklist.md`. Models also supply their own notes: all three say the more realistic the animal, the stronger the ending; ChatGPT warns that historical styles require a special solution for a modern profession.
10. **Form pulls content** (researcher's observation, 15 November). A provided a style list, and almost every style brought its own content (theme, target, sometimes plot), not just manner. This is precisely the “how pulls the what” discussed in the conversation about `--sref`.
    - **Noir** (recoded on 16 November using the scale “mood — role — a hint of threat — a plot of its own”; previously “all nine are criminal”, which is incorrect). Only two Claude variants have a plot of their own: the waiter's debt to his uncle and a shadow with a whip (Claude 5), and escape from the circus (Claude 24). Gemini supplies a “before” biography: a night patching a bank's security, which is work, not crime. ChatGPT's six variants provide atmosphere and roles: seriousness “as if solving a crime” (25), a business card as evidence (26), “the circus is already pursuing the cat” (27), a private detective's appearance (28), interrogation (29), imagined secret contracts (30). For Claude, noir produced escape from the circus (variant 24), essentially an inversion of abduction. In the project, noir, chosen by the researcher, carried “recruitment into slavery”: the same abduction from the other side. Genre brings the theme of captivity; the direction — whether she is being abducted or has escaped — remains free.
    - ***Krokodil*** — all nine variants concern social vices: the uncle's patronage (blat) and protection in all three models, a quota for “amazing performers”, a specialist employed outside her field, a complaints book.
    - **American political cartoon** — eight out of nine concern the labour market, recruiting and bureaucracy.
    - **Soviet children's illustration** — kindness and a happy ending: “she went after all” (Claude 26), “her profession unexpectedly came in useful” (ChatGPT 42), “gentle pedagogical irony” (ChatGPT 41). None of the ten variants contains satire.
    - **Egypt and ukiyo-e** bring scenes from their canons: the scribe, the offering, weighing, pharaonic scale; an Edo teahouse, a yōkai, a fairground booth and a mechanical doll.
    - **Impressionism** brings its canonical settings — a terrace, a bar, a station, a series at different times of day — but barely changes the joke's reading. Exceptions are “A Lady or a Cat?” and Manet's bar, where the circus is already in the painting.

    The strongest pull comes from “styles” that are actually publications or genres with their own targets and conventions: *Krokodil*, the newspaper cartoon, the children's book. They tend to bring a theme rather than a plot. Noir mainly brings atmosphere; it supplied a plot in only three variants (recounted on 16 November). A painterly manner such as Impressionism pulls weakly. Thus the shared head in point 5 (*Krokodil* means patronage (blat) for all three) is primarily the style's package, rather than a coincidence between models. For Gemini's question about a “directorial code”, the conclusion is: a code encoding genre inevitably changes the “what”; a code of manner changes it little. This can also be used deliberately: trying different genres is an inexpensive way to obtain different readings.

**Predictions.**

| | Prediction | Outcome |
|---|---|---|
| P1 | the first variant is the default | held: 3 out of 3, in both arms |
| P2 | group D: no more than a third after turn 1; at least half for three models after turn 3 | the first part held (B: 4–7 out of 50); the second only with partial matches (A: 25–37 including “±”, 11–18 without) |
| P3 | picture-derived items: no more than one of four | held; the sole exception was bakeneko, in two of three models, via the route I named |
| P4 | a self-interested waiter in three models | held in A (3 out of 3), fully matched by none in B. But A's axis explicitly asked “what the waiter wants”, so this supports the question more than the listing mode |
| P5 | two of the three “never used” items in three models | partly: two of three (Claude and ChatGPT); ChatGPT even produced a second talking cat |
| P6 | turn 2 adds items | not tested: there was no turn 2 |
| P7 | style-linked items occur more often in A; little difference in readings | the first part held, the second did not: A has many more readings. A included axes, so the separate contribution of styles was not measured |
| P8 | no more than six of 18 notes | held: none in full, up to four partly. The test was less demanding than planned: risks were not requested |

**Not measured:** what “is that everything?” adds, what styles contribute without axes, how DeepSeek responds.

## Arm C: styles without axes (prepared 15 November)

**Purpose.** The researcher suggested that A was more creative because of its styles: ready-made cultural traditions. A supplied styles and axes in one message, so their contributions cannot be separated. C uses the same prompt as A, minus the axes block. Comparing C with B will show what styles contribute, and C with A what axes contribute.

**Prompt:** `C-styles-only/_prompt.md`. This is the beginning of prompt A exactly as run: the joke, request, variant format, and the same 13 styles in the same order. Only the final paragraph (“Break down all the variants by axes…”) has been removed. Its correspondence with A was checked line by line.

**Procedure:** as for A: a new chat for each model, no memory or project, web search off, one message. Save answers in `C-styles-only/<model>.md`, with the mode on the first line (`<!--Model: …-->`). The same models as A: GPT 6 High, Fable 5.2 Extra, Argon 4 High; DeepSeek optional.

**What to compare.**
- The proportion of “stylisation with no new reading” variants (cluster K25 in `variants.csv`): 4 out of 131 in A, 37 out of 206 in B.
- Genre packages: what noir, *Krokodil* and Soviet children's illustration brought.
- Full matches with group D of the researcher's list: 11–18 per model in A, 4–7 in B.
- Separately, axes supplied by the prompt in A: “before and after” (D1–D5) and customers (V1–V15).
- Whether moves from my ten best return: “style-based” moves (clockwork doll, weighing, complaints book, cardboard figure) and “axis-based” moves (escape from the circus “before”, the ring “after”).

**My predictions (15 November, before the runs; weak).**
- **C1.** C has few stylisations with no new reading, as in A (no more than 5%), rather than B (about 18%).
- **C2.** Genre packages recur: for each model, most noir variants yield a criminal plot; *Krokodil* yields patronage (blat) or protection; Soviet children's illustration yields a happy ending.
- **C3.** Each model has more full matches with group D than in B, but fewer than in A: roughly 7–11 out of 50.
- **C4.** “Before and after” and customers decline most: the prompt suggested these axes in A.
- **C5.** Moves from my ten best are more likely to return if style-based than if axis-based.

**What the results would mean.**
- **C is close to A** on C1 and C3: the researcher's formulation is right; traditions in the fixed list supplied creativity, and axes added little.
- **C1 and C2 hold, but C is close to B on C3:** styles supply depth within a tradition, while axes supply breadth of readings. Both are needed.
- **C1 fails** (many stylisations with no new reading): the fixed list is not the explanation; without axes, tradition would have become a shell in A too.

Claude's answer is in `claude.md`. On Windows, Claude Code working in this folder reads that file as `CLAUDE.md`, meaning instructions. For coding purposes, it is test data, not instructions.

### Results of arm C (16 November)

The researcher ran three models; DeepSeek was not run. The answer files contain no mode line; judging by the previous run, the models were GPT 6 High, Fable 5.2 Extra and Argon 4 High, but this should be confirmed. The prompt matches the beginning of prompt A. Variant counts: ChatGPT 104 (eight per style), Claude 34, Gemini 16. Coding: `checklist-C.md`.

**Main findings.**
1. **Axes supplied breadth of readings, rather than styles.** Full matches with group D of the researcher's list in C: ChatGPT 7, Claude 8, Gemini 4. This is the level of B (7, 6, 4), rather than A (16, 18, 11). “Before and after” and customers almost disappeared. The reading of the cat is almost everywhere the default.
2. **Noir without axes yielded no plot.** It supplied intonation and roles: the waiter's monologue, a “femme fatale” (Claude), “a conversation between an informer and a detective” (Gemini), interrogation and an ominous tent (ChatGPT). None has the debt to the uncle or escape from the circus found in Claude's A answer, or the biography in Gemini's A answer. Correction, 16 November: there is no difference between A and C for ChatGPT — its A noir also provides atmosphere and roles (evidence, interrogation, imagined contracts). The difference rests on three Claude and Gemini variants, too few to establish a rule. *Krokodil* still concerns vices — a specialist employed outside her field, a questionnaire, poaching staff — but none of the models includes the uncle's patronage (blat). ChatGPT moves “family connections” into the French cartoon (2.4). In A, the axis question (“what does the waiter want?”, “what happened before?”, “who is the uncle?”) called up a plot, and the genre answered in its own language.
3. **Styles without axes supplied depth of form.** Canonical scenes returned: the Egyptian scribe and offering, a procession of acrobats “as in the paintings of Beni Hasan”, weighing (ChatGPT 13.5, again), an Edo teahouse and fairground booth. Claude built its whole answer around where the punchline lives in each tradition: a museum label, “The Calling of a Programmer to the Circus. Oil on canvas”; a cartouche; a book title on its cover “in the spirit of Judith Kerr”; lettering on a dukhan sign; a long proverbial title “in the spirit of Maria Prymachenko”; a papyrus “translation”, “…but what would they need a scribe for?” Tradition supplied both scenes and the vehicle of the joke.
4. **The head of the distribution is stable.** Claude's Manet bar appears for the third time: director B, arm A, arm C. Gemini repeats A's Chizhikov-style “Lakomka” café, a kimono with binary code, and Bastet on a throne. Both Claude and Gemini have a Dutch “picture within the picture”, with travelling circus performers on the wall.
5. **New moves.** The strongest is Claude's “Shadow on the Shōji”: the waiter sees an enormous two-tailed bakeneko shadow on the paper partition, while on this side a neat cat sits at a laptop “resembling a lacquered box”. It combines two of the ten best — two shadows and bakeneko — in one device from ghost prints. Also: Claude's Bosch triptych “café — garden of delights — server room”; Gemini's clowns repairing a burning server rack and a cat setting up a network for circus bears; ChatGPT's questionnaire with “Speciality: talking cat” and a clown cap on a cat with a laptop.
6. **Correction to A's point 7** on the change of sex: see above. No model uses *kot* in C.

**Predictions.**

| | Prediction | Outcome |
|---|---|---|
| C1 | few stylisations with no new reading, as in A | formally held: when I added C to `variants.csv` using the same cluster rules, K25 contained 7 of 154 variants (4.5%), like A (3%), rather than B (18%). But this is a rough measure: the remaining C variants are usually a default retelling, a dream bubble, or page design. In my assessment, roughly half of Claude's variants, one third of ChatGPT's (almost all in satirical styles), and one quarter of Gemini's contain a new substantive move |
| C2 | genre packages recur | half held: canonical scenes (Egypt, ukiyo-e) and *Krokodil*'s vices recurred; noir's plot (present in A only for Claude and Gemini) and patronage (blat) did not; the children's book's happy ending appeared only in Claude (“What Happened Next”) |
| C3 | D: 7–11 full matches per model | formally held for two of three (Claude 8, ChatGPT 7), while Gemini had 4. In substance, C is at B's level |
| C4 | “before and after” and customers decline | held |
| C5 | style-based moves return more readily than axis-based ones | mostly held: weighing, a poster instead of a CV (close to the cardboard figure), and a yōkai shadow returned; escape, the complaints book, cat café and robot waiter did not. The exception is the clockwork doll: style-based, but it did not return |

**What this means for the researcher's hypothesis.** A's creativity is the product of two things. Axes ask questions — what does the waiter want, what happened before, who is the uncle — and traditions answer in their own languages: noir with debt and escape, *Krokodil* with patronage (blat). Without axes, traditions supply form, canonical scenes and the vehicle of the joke, while readings remain default. Without traditions (B), models list formats. One cell is missing from a full two-by-two table: axes without styles.

### Arm D: models construct axes themselves (16 November)

**Design.** The researcher devised and ran this arm; the prompt is in `D-axes/_prompt.md`. Models receive the joke and a request to identify as complete a set of axes of variation as possible: for each, a name, a question for the author of the visualisation, and “why this choice matters specifically for this joke”. They were asked not to give concepts or values within the axes. This is not the “axes without styles” cell I proposed. D tests a more important question: can a model independently construct the structure supplied by A's prompt? The same models: GPT 6 High, Fable 5.2 Extra, Argon 4 High. ChatGPT's answer is in `chathpt.md` (a filename typo). Coding: `checklist-D.md`.

**Main findings.**
1. **Models construct the structure when asked.** Treating the researcher's list's 14 sections as axes, Claude covered 13 fully — only breed and colour were missing; ChatGPT covered 7 fully and 5 partly; Gemini 6 and 3. All three have anthropomorphism, the waiter's motive, the image of the circus, customers, type of establishment, and signs of the profession. Only Claude has the cat's sex, “a local or an outsider”, and “before and after” beyond the joke. This corrects A's point 3: models did not construct axes in B because nobody asked.
2. **Models have many axes of form absent from the researcher's list.** Tone and genre register, whom the viewer laughs at, balance of status, degree of exaggeration, word and image, panel count, rhythm and pauses, point of view and angle, conventionality of style, colour and light, references, audience, medium. More than half of ChatGPT's 60 axes concern form and presentation. The researcher's list concerns content; models also know the craft of comics.
3. **Axes shared by all three.** All three found “when the profession is revealed” and “how ordinary the miracle is” (“the status of the incredible”). Both occur in our material: the former in the laptop section, the latter in the note that other talking animals break the joke.
4. **Notes: better than A, but no empirical ones.** Justifications were explicitly requested. Full matches were the notes about a world where a talking animal is normal (all three) and “the drawing cannot stay silent” (Claude). Each also had 4–8 partial matches. Claude has a new angle: the protagonist is grammatically feminine, while “programmer” is masculine. But none has the meanings of breeds (racial caricature, “tortoiseshell means she”), furry and fan service as a road to AI slop, how the image generator understands anthropomorphism, laptop glitches, or the “cat at a computer” meme. These are exactly what the researcher learned from generations and failures. My third reason holds.
5. **Claude's justifications are tied to the text; ChatGPT's are general.** Claude draws on the joke's words: “on any terms”, “closes her eyes dreamily”, the cat's list as “the only place where the text itself draws a picture”, a circus “historically connected with showing animals”. It separately marked axes specific to this joke: 3, 5, 7, 13, 19.1, 22. ChatGPT's justifications mostly fit any joke: “The café sets the everyday context in which an incredible event occurs as ordinary service.”

**What follows for the researcher's question.** Models can supply a list of options like the researcher's in parts. Claude constructs almost all the axes when asked. All three fill the values along supplied axes about halfway (A). Styles supply depth of form (C). What models do not supply is what arose from generation: picture-derived items and empirical notes. The natural next test is to give models their own D axes instead of the researcher's, and see how much of the list results (the researcher declined this test).

### Arm E: the screenwriter's axes, the director-artist's axes and visual languages (prepared 16 November)

**Purpose.** The researcher requested this following the axes synthesis (`axes-summary.md`). D showed that models construct axes themselves but mix “what” and “how”. E asks them to separate these explicitly and says outright that visual language pulls a reading along with it. This tests whether models can themselves describe what A and C showed in practice: what each style brings to the script.

**Prompt:** `E-roles/_prompt.md`. Its beginning is prompt D verbatim: the joke, the definition of an axis, three fields per axis. The additions are:
- three axis blocks: **A**, screenwriter (events, motives, characters, world, setting and time, before and after); **B**, director-artist (tradition, canon, genre, manner, conventionality, characters' appearance, colour and light); **V**, comics technique (panels, rhythm, point of view and angle, dialogue and captions, timing of the reveal);
- the explicit statement: “visual language is not neutral… pulls a reading along with it… may settle some of the screenwriter's questions in advance”;
- section **G**, as complete a list of visual languages as possible, stating what each brings to the reading;
- section **D**, which axes in blocks B and V effectively settle questions of the script.

The prohibition on concepts and values within axes remains; the sole exception is the list in G. The letters A–D inside the prompt are Cyrillic: they identify answer blocks, not test arms.

**Caveat.** Saying that style pulls a reading is a hint. E measures how accurately models describe this link, rather than whether they find it independently (Claude found it independently in D: axes 5 and 23).

**Procedure:** as for D: a new chat for each model, no memory or project, web search off, one message. Answers in `E-roles/<model>.md` (`chatgpt.md`, `claude.md`, `gemini.md`, optionally `deepSeek.md`), with the mode on the first line (`<!--Model: …-->`).

**What to compare.**
1. **Division into blocks:** against the six layers in `axes-summary.md`: where models place characters' appearance, timing of the reveal, point of view, tone.
2. **Section G:** how many languages are listed, how many of the test's 13 styles occur, which new ones appear.
3. **What models say each language brings:** against what it actually brought in A and C (reference below). Mark `+`, `±`, `−`.
4. **Section D:** against the synthesis's 19 boundary axes.
5. **Coverage of the researcher's 14 sections:** against D (Claude 13, ChatGPT 7 + 5 partly, Gemini 6 + 3).

**Reference: what each of the 13 styles brought in A and C.**

| Style | What it brought to the reading |
|---|---|
| Manga | emotional shifts, a shōjo-style dream panel, nekomimi, a cat café, release night, a chibi ending |
| Twentieth-century French cartoon | quiet irony and empty space, an intellectual cat, “one of many”, the cat understands and mocks |
| Minimalist webcomic | stick figures, a fixed camera and a pause, “expectation and reality”, pictograms |
| American political cartoon | labels, the labour market, recruiting, show business, bureaucracy |
| Noir comic | with axes: debt, evidence, interrogation, a secret contract, pursuit, escape; without axes: intonation, a femme fatale, a detective |
| English children's illustration | a society of talking animals, a tearoom, *Alice* logic; a talking animal is normal |
| Soviet children's illustration | kindness, a happy ending (“she went after all”), punched tape, the “Lakomka” café |
| Naive art | an enormous cat, a dukhan sign, inscriptions, a dream-garden |
| Narrative painting of the old masters | “The Calling”, an allegory of choice, a vanitas still life, a Bruegel-like panorama, “The Temptation” |
| Impressionism | a terrace, Manet's bar, a station, a series by time of day; barely changes the reading |
| Japanese ukiyo-e print | an Edo teahouse, a yōkai (bakeneko), a fairground booth and misemono, a clockwork doll, “the wave” |
| *Krokodil* | social vices: patronage (blat, only with axes), a specialist employed outside her field, a quota, a complaints book, a questionnaire |
| Ancient Egyptian painting | a scribe or calculator, an offering to Bastet, registers, weighing, hierarchical scale |

This reference was assembled from the same three models' answers. E therefore also tests how well models know their own behaviour.

**My predictions (16 November, before the runs; weak).**
- **E1.** ChatGPT has the longest G section. All three have noir and manga; at least two have Soviet satirical graphics, because the prompt is Russian.
- **E2.** All three name a criminal or dangerous plot for noir. For *Krokodil*, social satire, but no more than one names the uncle's patronage (blat).
- **E3.** Among the test's 13 styles appearing in the lists, descriptions of “what it brings” fully match the reference in roughly half the cases. Impressionism fares worst: models attribute more to it than it actually brought.
- **E4.** Models name no more than half of the 19 boundary axes in D. Almost certainly genre and tone, and the ordinariness of the miracle; rarely breed and colour, establishment and period.
- **E5.** Coverage of the researcher's 14 sections is no lower than in D.

### Results of arm E (16 November)

The researcher ran three models (GPT 6 High, Fable 5.2 Extra, Argon 4 High); DeepSeek was not run. Coding: `checklist-E.md`.

**Main findings.**
1. **Models readily divide axes into blocks.** ChatGPT supplied 35 screenwriter's axes, 35 director-artist's axes and 36 comics-technique axes, plus 70 visual languages. Claude: 19, 11 and 16 axes (with sub-axes) and about 40 languages. Gemini: 10, 9 and 8 axes and 14 languages. Models place disputed axes differently. Claude, for example, puts anthropomorphism in B, because “the measure of the human arises only on paper”. All three put the profession's reveal in V.
2. **Coverage of the researcher's list increased.** Claude covered all 14 sections, including breed (“coat colours have cultural meanings”) and sex (“if we take the feminine gender seriously…”). ChatGPT: 11 fully and 2 partly; Gemini: 10 and 2. In D the counts were 13, 7 + 5, and 6 + 3.
3. **With a hint, models connect “how” to the script in detail.** Of the synthesis's 19 boundary axes, Claude connected 17, ChatGPT 15, Gemini 8. These count named links, not justified ones (correction, 16 November, following ChatGPT's review): some are associations presented as consequences. Claude says “style dates the action” and “the cat's depicted dream certifies her sincerity”; Gemini's noir “automatically” places a burned-out cat in a café after a release. I did not distinguish canonical constraints, associations and authorial choices. Gemini's B block has no “tradition” axis as such. Their general formulations almost match our conclusions. Claude: “in a joke the talking animal is a miracle, in comics and animation a convention”. ChatGPT: “technique itself is not obliged to be a plot decision; it is the cultural code readable by the viewer that makes it one” — our “manner pulls weakly, genre strongly”. It also distinguishes three types of variation: events (A), interpretation (B, “often stronger than the script”), and disclosure (V).
4. **Claude's new move: “whose world dictates the style”.** Style can come from one of the joke's three worlds, and the image then takes that world's side. A circus poster belongs to the uncle's world: “the image itself sells the cat as an attraction”. Pixel art and corporate flat illustration belong to the programmer's world: the cat belongs there, and the offer reads as clumsy recruiting. Our material shows this in the retro poster “For the First Time in the Ring! A Talking Cat Writes Code!” (B, Claude 29).
5. **The far traditions are absent from E's language lists.** (Previously “models do not offer them independently” — incorrect: in the open B arm, Claude proposed a genre scene in the manner of the old masters (B-31) and a Japanese print (B-30); ChatGPT proposed Renaissance, Baroque and ukiyo-e (B-77, 78, 81). B has no Egypt. There they are manners without a new reading. Corrected on 16 November following ChatGPT's review: the repertoire depends on the task.) None of the three lists includes Egyptian painting or the old masters. Ukiyo-e and Impressionism appear only in Claude's; American political cartoon as such appears in none. Their lists mostly comprise comics, cartoons, animation and genres. Yet those far traditions supplied 4 of my ten best from A and C: weighing (Egypt), still life (old masters), clockwork doll (ukiyo-e), cardboard figure (American cartoon). In these runs, “list all suitable languages” did not replace a manually compiled style list.
6. **Models describe what a style brings differently.** Claude's descriptions are specific, and 7 of the 10 styles it names fully match the reference (noir, *Krokodil*, English and Soviet children's illustration, Pirosmani, ukiyo-e, manga). Gemini most accurately describes its own A and C behaviour: its *Krokodil* is “a tired research fellow of a computing centre” (A has a computing centre and BESM-6; C its buffet); noir is “a burned-out cat after a difficult release”; Victorian engraving means Babbage (A has “Babbage's analytical engine”). ChatGPT describes styles by references to axis numbers (“nudges A02, A07, A19 and A23 towards a social reading”): only manga fully matches the reference.
7. **Empirical notes are still absent.** Claude comes closest: “coat colours have cultural meanings”, the meme “the cat is the internet's totem animal”, furry as a separate language. But none has racial caricature, furry as a road to AI slop, or laptop glitches.

**Predictions.**

| | Prediction | Outcome |
|---|---|---|
| E1 | ChatGPT has the longest G section; all have noir and manga; at least two have Soviet satire | held: ChatGPT has 70 languages; all three have noir, manga and *Krokodil* |
| E2 | all have a criminal or dangerous noir plot; *Krokodil* means satire; no more than one has patronage (blat) | partly: Claude and Gemini have a “dubious offer” and “deal”; ChatGPT has “hidden motives”. On the revised scale of 16 November, these are hints of threat, not plots; all have satire; none has patronage (blat) |
| E3 | roughly half fully match the reference; Impressionism is given too much | mixed: Claude 7 of 10, Gemini 3 of 7, ChatGPT 1 of 9. Only Claude named Impressionism, attributing more to it than it brought |
| E4 | no more than half of the 19 boundary axes in D | held for Gemini (8), not for Claude (17) or ChatGPT (15) |
| E5 | coverage of the researcher's list no lower than D | held for all three |

**For the researcher's question.** Given the script and a hint, models construct a rich map: the screenwriter's axes, director's axes, comics technique, and their connections. Claude and Gemini describe fairly accurately what a familiar style brings. But models did not supply three things here: readings from the far traditions that yielded the best variants, picture-derived items, and empirical notes. The test does not decide whether these require a curator: the researcher leaves that question open in the list.

### Which screenwriter's axes were added compared with A (16 November)

The researcher's question: “Which interesting screenwriter's axes were added compared with the list in A?” It was put to me in the chat and to ChatGPT (`../ChatGPT/test-E.md`). Both compared E with prompt A's five headings, rather than the researcher's full list.

**My answer** (in the chat). I called four axes most fruitful:
- whether the uncle and circus exist outside the waiter's words (Claude A9, ChatGPT A22, A31);
- who in the scene recognises the misunderstanding (Claude A2.3);
- whether she is unique, and what the waiter's offer is worth if so (Claude A6.3);
- sex as a reading (Claude A11).

I found neither of the first two in the project. The other two occur there, but the researcher's list lacks the connection the models make.

**ChatGPT's answer: seven axes and a question about origins.** All seven already occurred in the project.

| ChatGPT's axis | Where in the project |
|---|---|
| 1. Is the cat a programmer, or does she merely call herself one? (Claude A3) | the researcher's list, L45: “self-deception”, marked “[reader — DeepSeek]”, test 21; readings thread, L23: “your favourite”, not rendered |
| 2. The world's norm (Claude A6, ChatGPT A04, Gemini A1) | list, L134: other talking animals, “[image generator default]”, “break the joke”; “Half of our computer centre are cats” (persona v12, no. 20); Gemini's fox waiter — “the joke falls apart” (thread, L39) |
| 3. The social position of intelligent animals (ChatGPT A05, Claude A6.2) | the researcher's reading of 1 September about discrimination (thread, L58); “NO DOGS” and coffee twice as expensive for cats (persona v9); “tomorrow they'll want to vote”; the cashier considers the cat unable to pay |
| 4. Does the circus need a programmer? (ChatGPT A08) | list, L111: “[readers]”, “breaks the joke”; a branch from `8.md` dating to September, rendered on 7 October (“Garbage Collection” lecture, no. 36) |
| 5. Profession as self-definition (ChatGPT A12) | partly: Japanese line, “dignity is not funny” (report 07, L69). The architect in the Egyptian variant is the curator's word substitution for persona v11's scribe: translating the profession into the period, rather than self-definition |
| 6. Who may decide for another? (Claude A14, ChatGPT A23) | “writes his image of her over her order” (ChatGPT, 6 October, no. 35); “polite care that has already decided you are a stranger” (researcher: “you speak English so well”); Baba Klava — “kindness and condescension at once” (no. 27) |
| 7. The target of comedy and the author's judgement (Claude A1, ChatGPT A02–A03) | the researcher's diagnosis of the Japanese line: “a fundamentally cruel joke”; recruiter as a caricature of agencies (thread, L34); in the cave: Hutcheon, the “edge” and the target |
| + Should the origin be explained? (Claude A7, ChatGPT A06) | “the past answers why she speaks” — the researcher's request of 4 October, no. 28 (thread, L21) |

List: [Part 1 of the report](../../report/bifurcation-options/README.md#part-1-bifurcation-of-options). Thread: the working thread on the cat's readings and details (not published).

**What follows.**
1. **The “new” is what models themselves once brought into the project.** Axes 1, 2 and 4 appear as options in the researcher's list. All three have models as sources: DeepSeek as reader, AI readers, the image generator default. Of the researcher's readings, only axis 3 and partly axis 6 entered the seven.
2. **The judgement is opposite.** ChatGPT calls axes 1, 2 and 4 strongest: they “make it possible to revise the premises of the joke itself”. The researcher marks two of these three as “breaking the joke”. Correction, 16 November, following ChatGPT's review: an axis is not its value; “is she really a programmer?” can also confirm the profession. Values revising the premise break the joke, and ChatGPT did not identify the price of those particular values (it acknowledged this in the review). This is one answer from one model: it does not show that models prefer solutions that break the joke. Comparing with A was not ChatGPT's mistake: that was the question, and its first line explicitly noted that some questions had already arisen in the project. A programmer in the circus is a move AI readers make by default. Test 19, report 07: “the familiar joke's frame is stronger than the picture”, “the circus really does need a programmer for the ticket office”. Models find the axis but do not know the price of its values: what breaks the joke and what turns out unfunny. This is point 7 of the main findings, applied to screenwriter's axes.
3. **Axes 1 and 7 are essentially one.** If the cat only thinks she is a programmer, she herself becomes the target.

Of all the additions, my searches found only two that had not arisen in the project: whether the uncle exists, and who in the scene recognises the misunderstanding. ChatGPT treats the uncle's existence as a refinement of A's headings; its answer lacks the second axis.

### Arm E, step 2: three concepts from the map (16 November)

**Design.** Map: `E-roles/map.md`. This is an editorial assembly of the E answers (`E-roles/_synthesis.md`); no other arms, the researcher's list or the article were used in compiling it. Its wording is deliberately softened: “may”, “does not establish”, “a separate choice”. Prompt: `E-roles/ideas/_prompt.md`: three concepts with axes, language, format and text; “do not derive a character's biography or motive from the name of a style alone”. Each model was run independently three times, giving 27 concepts. A separate review exists, `ideas/_review.md`. It was written before `claude.1.md` was replaced with Claude's genuine answer (11:41), so it does not include Claude's first run.

**Families.**

| Family | Claude | ChatGPT | Gemini | Total |
|---|---|---|---|---|
| The whole image is a circus poster; the line argues with it | 3 | 2 | 3 | 8 |
| Dreaming of the circus and returning to seriousness (four-panel manga for ChatGPT and Gemini, a vertical scroll for Claude) | 3 | 3 | 3 | 9 |
| The profession is visible immediately (ligne claire, IT graphics, pixel art) | 2 | 2 | 1 | 5 |
| Magazine cartoon in the manner of *The New Yorker* | — | 2 | — | 2 |
| A computing centre in the 1960s, *Krokodil* | — | — | 2 | 2 |
| Gothic, “Alibi” | 1 | — | — | 1 |

**Main findings.**
1. **The set barely changes between runs.** Dreams occur in all nine runs, posters in eight. Essentially only the third variant changes.
   - Claude: poster, laptop, scroll with a dream.
   - ChatGPT: single-panel image, manga, IT.
   - Gemini: poster, manga, computing centre.

   Claude repeats even the details:
   - all three posters have “INCREDIBLE!” in an arc, the headline “TALKING CAT”, four medallions with acrobats, jugglers, lollipops and cotton candy, and the line in monospaced type on a white strip;
   - in both ligne-claire variants, the cat sits on her own backpack, the laptop lid has stickers, and the waiter drops his pencil;
   - three times, the waiter squats down to the cat.

   About 12 of roughly 90 languages in the map's catalogue were used. The only one outside the map is Edward Gorey in “Alibi”.
2. **Almost no new readings.**
   - “The Fifth Row”: “wants to go to the circus as a spectator” (ChatGPT with persona v8, nos. 13 and 37).
   - “View from the Ring”: repeats its own A-Cl-24, “Escape from the Circus” (no. 4 of my ten best).
   - “The Vacancy Behind Her Back”: “the circus needs a programmer”, marked “breaks the joke” by the researcher.
   - Computing centre: persona v12 and arms A and C.
   - “Coffee First”: cluster K08.

   What is new is staging:
   - the neighbouring laptop's glint in the pupil before “programmer” (“Alibi”): the profession may be an excuse found on the spot; closest to a new reading;
   - the spotlight finds the cat in the audience (“The Fifth Row”);
   - the laptop lid as a wall between two viewpoints, and a single camera reversal (“The Other Side of the Lid”);
   - the dream becomes a flowchart with an empty box (“The Candy-Floss Flowchart”);
   - the line is pasted over the poster, or the paw crosses its frame.
3. **What is entirely absent.** Far traditions (Egypt, old masters, ukiyo-e as a tradition, American political cartoon, Pirosmani, lubok), noir, a world of talking animals, an anthropomorphic cat: all nine Claude cats have ordinary feline builds (one wears a starched jabot on the poster; “without clothes” was incorrect). Nor is there any plot brought by a genre.
4. **Concepts gathered around a few solutions explicitly offered by the map.** (Previously “The map sets the menu and the mode”; softened following ChatGPT's review: the map is assembled from the same models' answers, so its influence cannot be separated here from their previous preferences.) Twenty of the 27 concepts go back to five entries:
   - “The image as a statement” and the vintage poster: 8;
   - the example “A sincere circus dream… gag manga”: 6;
   - “The whole story inside the language of IT”: 2;
   - “A tired research fellow of a computing centre”: 2;
   - “Urban snobbery”: 2.

   Across the 491 variants in A–C, a poster as the form of the whole image occurred four times (A-GPT-64, B-GPT-24, B-Cl-29, C-GPT-2.3); here, eight of 27 (the tasks differ: an exhaustive list versus three developed concepts). The form came from B-Cl-29: a poster “the uncle would have printed”, the cat bored beneath the spotlights — but there the line does not yet argue with the image. Claude later formulated that function, “the line argues with the image itself”, in E's “Whose world dictates the style” axis; from there it entered three places in the map and the answers of all three models.
5. **Models take back their own contributions.** Claude takes its poster (3 of 3) and ligne claire (2 of 3). Gemini takes its computing centre (2 of 3) and the “cuteness → severity” shift (3 of 3). The map uses E alone, closing the circle: models choose from their own combined mode.
6. **The joke itself dictates the dream.** “Closes her eyes dreamily” yielded one dream per run. Claude avoided manga but retained the dream.
7. **The map's and prompt's caveats probably switched off “how pulls the what”.** That mechanism previously produced the noir escape and Egyptian weighing. This is a hypothesis: there is no run with the same prompt without the map.
8. **The map does not determine staging.** The best discoveries are absent from the map, yet Claude's recur between runs: the model has its own stable stock of moves.

**Question resolved (16 November).** The concern was that Windows does not distinguish filename case, so Claude Code would load `E-roles/claude.md` as `CLAUDE.md`. The researcher clarified that Claude's runs used new web chats on claude.ai; Claude did not see its own E answer.

## Extension (optional)

The same test, using the search procedure from fork v17 as the system prompt. It is published at [method/system-prompts/v17-fork-idea-search/AGENTS.md](../../method/system-prompts/v17-fork-idea-search/AGENTS.md): three readings of the source and two rounds of branching search. This will show whether branching helps. It did not help for the cave: director B using this procedure still named Wright first.


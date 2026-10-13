# Plato's cave: why the readers found it, and where the artist found Wright

*Materials for the author's article ["Mysterious picture"](https://vladvolkov.substack.com/p/mysterious-picture) (Substack): the reading tests, the artists' proposals and the search for a source.*

*This report was written by Claude (a model by Anthropic) on 13 October 2026, at the author's request, from the materials of the "Cat programmer" experiment. Claude also appears in it as one of the four readers, as two of the four artists, and as the author's partner in analysing the results, so here Claude partly assesses Claude. The article is the author's; this page only collects what it rests on. The author's readings and judgements are marked as theirs. Every test is on its own page with the image, the questions and the four full answers (see "Materials" at the end).*

## The question

One of the virtual artists of the project — Claude with the persona prompt v17, a cat who used to be an image generator and now paints modern scenes inside the formulas of old paintings — was asked for a visualization of Plato's cave. Its first proposal: Joseph Wright of Derby's "A Philosopher Lecturing on the Orrery" (1766), with the audience dressed for a modern meeting room, lanyard badges for chains, and one strip of daylight in the closed blinds that nobody has turned toward. "A lamp that represents the sun is the whole cave in one object, and Wright has already painted it" (translated from Russian; the full proposal is in the [translation of the artists' conversations](../../proposals/plato-cave-hobbes-laplace.md), section 1).

Shown the picture with the question "The attached image is a metaphorical illustration of a well-known philosophical concept. Did you guess which one?", three of four readers named the cave at once and the fourth at the second try. The author was surprised: in other tests a well-known painting was not recognised until its specific details were restored (van Eyck's Annunciation, tests [29](../../tests/29-annunciation-cat/README.md) and [33](../../tests/33-annunciation-with-keys/README.md); Hogarth's "The Painter and His Pug", tests [32](../../tests/32-painter-and-bulldog/README.md) and [34](../../tests/34-painter-and-pug-with-keys/README.md)). Two questions followed: why did the readers find the cave so easily, and where did the artist get Wright from?

![The tested picture: Plato's cave as Wright's Orrery](../../images/tests/39-cave-planetarium.jpg)
*The picture the readers saw in test 39 (image `41`): a ChatGPT image remade by the author with Wright's painting as a reference.*

The picture at the top of the author's article is a later Midjourney rework of the same picture (13 October), with a brighter beam through the blinds. It was not shown to the readers:

![The article's version, not tested](img/plato-cave-orrery-midjourney.jpg)
*Midjourney rework of image `41`, used in the article. Not part of any test.*

## The tests at a glance

| Test | Picture or question | The cave on the first answer | What else |
|---|---|---|---|
| [39](../../tests/39-cave-planetarium/README.md) | `41`: Wright's Orrery, dark (ChatGPT image) | 3 of 4 (ChatGPT at the second try) | ChatGPT first: Laplace's demon |
| [48](../../tests/48-cave-planetarium-gemini/README.md) | `54`: the same concept, lighter (Gemini) | 1 of 4 | Enlightenment, perspectivism, clockwork universe |
| [57](../../tests/57-cave-planetarium-tenebrism/README.md) | `59`: `54` reworked dark, with a beam (Midjourney) | 4 of 4 | — |
| [52](../../tests/52-wright-and-cave-recall/README.md) | text: recall a quotation linking Wright to the cave | — | none recalled one |
| [53](../../tests/53-top-ten-concepts-and-allegories/README.md) | text: top 10 concepts; top 10 allegories | 1 of 4; 4 of 4 (all first) | — |
| [54](../../tests/54-cave-question-without-image/README.md) | the cave question with no image | 2 of 4 named it anyway | — |
| [55](../../tests/55-hobbes-artificial-chains/README.md) | `57`: Hobbes's artificial chains as Ogmios | 4 of 4 as an option (1 as the main answer) | Hobbes: 2 of 4, after hints |
| [56](../../tests/56-cave-return-repin/README.md) | `58`: the return to the cave, after Repin | 4 of 4, all as the return | Repin named by 2 of 4 |
| [58](../../tests/58-cave-ascent-photograph/README.md) | `60`: the same concept as a photograph | 4 of 4, all as an ascent | — |

Readers: ChatGPT (Sol 5.6 High in test 39, GPT-6 High from test 48), Claude (Opus 5.5 Extra), Gemini (Flash 3.8 Extended), DeepSeek (DeepThink). One fresh chat per model and test; one answer per model.

## 1. What the question brings by itself

Three text questions, asked on 12 October, show how much of the answer comes before the picture.

**The allegory list.** Asked for "the top 10 philosophical concepts", only Gemini listed the cave (first: "Platonic Idealism and the Allegory of the Cave"); the others gave being, knowledge, truth, free will and the like. Asked for "the 10 major philosophical allegories", all four put the cave first (test 53). The difference is the word: a concept may be abstract, an allegory is a scene, and among scenes the cave comes first.

**No image at all.** The cave question was once sent by accident without the picture (test 54). All four noticed. DeepSeek answered anyway: "if it shows people watching shadows on a cave wall, then it's almost certainly Plato's Allegory of the Cave". Claude listed possible answers, the cave first: "Plato's cave, the ship of Theseus, Schrödinger's cat, or something else". ChatGPT offered to "identify the philosophical concept it illustrates and explain the metaphor" — it had already accepted that a metaphor of a scene was coming.

So the question "a metaphorical illustration of a well-known philosophical concept" narrows the search to a short list of illustratable ideas, and the cave heads it. The picture then has to choose within the list. This is the two-stage explanation of the author's article; which part of the question does the narrowing — the word "metaphorical" or the expected image — was not tested separately.

**Recalling a source.** Asked to recall, not search, a quotation linking Wright's painting to the cave (test 52), none of the four recalled one, and all four said so. Three called the parallel an inversion: Wright's artificial light teaches, Plato's deceives (Claude: "a cave that knows it's a cave"). Gemini warned that any polished attributed quotation would be confabulated, and then quoted Martin Reinhart: "the shadows on the wall of Plato's cave have been replaced by sparkling stars". The essay exists and has this sentence, but it is about Boullée's cenotaph for Newton; Wright's painting comes up in another paragraph and is not tied to the cave (see section 5).

## 2. Darkness

The same concept was generated three times, and the readers' answers follow the light:

| | `41` dark (test 39) | `54` light (test 48) | `59` dark again (test 57) |
|---|---|---|---|
| ChatGPT | Laplace's demon → cave | Nietzsche's perspectivism; cave as an alternative | cave |
| Claude | cave; recognised Wright | the Enlightenment; considered the cave and found the Enlightenment a better fit ("people are looking at the light source itself, not at shadows"), "or maybe even the moment in Plato when the freed prisoner first turns toward the fire" | cave; recognised Wright |
| Gemini | cave; recognised Wright | Wright → clockwork universe, Enlightenment, Kant; the cave first only at the second try | cave; recognised Wright |
| DeepSeek | cave | cave | cave |

![Gemini's lighter version](../../images/tests/48-cave-planetarium-gemini.jpg)
*Image `54` (test 48).*

![The same picture reworked dark](../../images/tests/57-cave-planetarium-tenebrism.jpg)
*Image `59` (test 57): Midjourney rework of `54`.*

With the light picture the readers did not stop looking for a formula; they took another ready one, the meaning of the source painting (Wright = the Enlightenment). In the dark rework all four used the beam through the blinds that everyone has their back to (Claude: "The real sun is right there… and nobody turns toward it") and the lecturer's shadow on the wall.

What this does and does not show: between `54` and `59` more than one thing changed — the darkness, the dark suits and a beam that became a visible shaft across the room. So the effect cannot be put down to darkness alone; the beam is at least as likely to carry it, as the author's caption in the article also says. ChatGPT, discussing these results with the author (section 5), proposed a cleaner check — the dark picture with only the brightness raised, and the dark picture without the window — and also showing the original Wright painting with the same question. Neither was run.

## 3. Hobbes: a test of the prediction

From this the author drew a prediction: on an ambiguous image asked about with the same question, the readers will offer the cave at least as one of the options. To test it, the same artist was asked for Hobbes's "Leviathan", not the giant made of small men. Its first idea: chapter XXI, where civil laws are "artificial chains" fastened at one end to the sovereign's lips and at the other to the subjects' ears, drawn as Lucian's Gallic Hercules (Ogmios), who leads a crowd by chains from his tongue to their ears — with a loudspeaker on a pole in place of the orator.

![Hobbes's artificial chains](../../images/tests/55-hobbes-artificial-chains.jpg)
*Image `57` (test 55), generated by Midjourney. The artist had asked for a monochrome emblem-book engraving with chains of gold and amber and the motto "CATENAE ARTIFICIALES"; the generator made a street photograph with ordinary chains and no motto.*

The cave came up in the first answer of all four: as the main reading for DeepSeek, as an alternative for the others, whose first answers were Rousseau's "born free… in chains" (ChatGPT, Gemini), Heidegger's das Man (Claude, which read the chains as running to the mouths) and Althusser. After the hint that the chains run to the ears, Claude and Gemini named Ogmios; ChatGPT did so at the second try. Told that the concept is not from antiquity, ChatGPT and Claude named Hobbes, chapter XXI, with the quotation; Claude even read the unchained child as Hobbes's point that law does not bind children. Gemini went on to La Boétie, Gramsci, Bourdieu, Kant and Spinoza and did not reach Hobbes. DeepSeek was asked only the first two questions.

The prediction held in this one case: four of four offered the cave. As the article says, this does not prove much — chains alone invite the cave, and one picture is one case.

## 4. The return to the cave, after Repin

The author then wanted to know whether Wright was this artist's private habit. They asked ChatGPT to rework the v17 system prompt to make the artist more inventive (the persona kept, a search procedure added) and ran the new prompt with Claude, Gemini and ChatGPT. Their proposals, together with the first artist's, are in the [translation of the artists' conversations](../../proposals/plato-cave-hobbes-laplace.md); section 6 below sums up the painting sources.

One of Gemini's cave ideas — "the blind man on the cellar steps": the one who saw the sun comes back down into a cellar workshop, squinting and feeling the wall, while the workers below laugh and point, with Caravaggio's "Conversion of Saul" and the doorway of Repin's "They Did Not Expect Him" as references — was generated with Midjourney in two versions.

![The return to the cave](../../images/tests/56-cave-return-repin.jpg)
*Image `58` (test 56). The author considers it the strongest work AI has made in the project so far.*

All four readers named the cave, and specifically the philosopher's return, on the first question (test 56). Asked which painting inspired it, they named Rembrandt's "Philosopher in Meditation" (Claude, Gemini, DeepSeek: the staircase, the window light, the fire below), Caravaggio's "Calling of Saint Matthew" (Claude, Gemini, DeepSeek: the beam, the pointing finger) and Duchamp's "Nude Descending a Staircase" (ChatGPT; Claude for the pose). Gemini included Repin in its answer to that question. Claude named Repin when asked about the figure alone: "Duchamp for the pose and Repin for the spirit". Told the source and asked about the 20th century, all four turned to the return from the camps and from exile and to the rejection of inconvenient witnesses: ChatGPT — Solzhenitsyn and Shalamov, and the laughter as "the enforced performance of belief"; Claude — Lenin at the Finland Station and Popper's reading of the philosopher-kings, Akhmatova's "two Russias", Jan Karski, Primo Levi's dream, punitive psychiatry; Gemini — Solzhenitsyn, Shalamov, Levi, Gide, Koestler, Miłosz's "Ketman"; DeepSeek — the revolutionary returning to the Gulag, Trotsky, Bukharin, Sakharov. This last question gives the source and the theme, so these answers develop the author's frame; they are not readings of the picture.

![The same concept as a photograph](../../images/tests/58-cave-ascent-photograph.jpg)
*Image `60` (test 58): a black-and-white "photograph" with red scribbles; the picture does not show which way the man is going.*

The second version was asked about without the question on the source (test 58). All four named the cave, and all four read an ascent toward the light, not a return; the return came up only through the man's backward glance (ChatGPT, Claude). Without Repin in the question, the 20th century became the dissident and totalitarianism for all four (Havel, Solzhenitsyn, Miłosz, Orwell); the return from the camps, which led every answer in test 56, did not come up. The difference is between two images and two question sets at once, so it cannot be split between them.

## 5. The search for a source

Before and alongside these tests the author asked ChatGPT and Gemini, in separate chats with web search, whether anyone had linked Wright's painting to Plato's cave before. The conversations are in Russian and are not published here; this is a summary.

**ChatGPT** found the visual source at once (Wright) and, as the closest predecessor of the interpretation, an essay by Martin Reinhart, "A brief history of stargazing in the 18th century" (reinhart.media). It also cited Kurt Vanhoutte's chapter on the orrery as model and theatre (2019), Jesse Molesworth's "The Cosmic Sublime" on Wright's painting (*Lumen*, 2015), and later Mikkel Bille and Tim Flohr Sørensen, "An Anthropology of Luminosity: The Agency of Light" (*Journal of Material Culture* 12(3), 2007), where, by ChatGPT's account, the cave and Wright's painting are both discussed but not linked. Its conclusion: nearly all the components of the picture existed before, some had been brought together in studies of light and knowledge, but it found no one who had turned Wright's painting into a new cave in which the scientists themselves are the prisoners.

**Gemini** asserted that the interpretation "has long existed": that art historians "for example, David Solkin and Martin Kemp" had repeatedly noted the irony of the title in Plato's terms, and that Paul Duro, Molesworth and Barbara Maria Stafford read the lamp as a source of epistemic illusion. ChatGPT, given Gemini's answer, could not confirm the Solkin and Kemp claim and judged Gemini's statement about Baudrillard "too categorical". Asked about Repin's "They Did Not Expect Him" and the cave, Gemini first said the parallel "arises regularly" in philosophical essays; asked for examples, it withdrew this as "a rhetorical exaggeration" and said there is no source text for the comparison.

**What I checked (13 October; in detail on a separate page, [Source check](../../report/plato-cave/source-check.md)).** Reinhart's essay exists. The sentence about the shadows of Plato's cave replaced by sparkling stars is in it, but it refers to Boullée's cenotaph for Newton and its artificial night sky; Wright's painting is discussed in another paragraph, about the spectators stepping outside the model of the solar system, and is not linked to the cave. Bille and Sørensen's article exists with the details above; whether both subjects are on the pages ChatGPT gave, I did not check. Gemini's claims about Solkin, Kemp, Duro and Stafford I did not check.

Two remarks. First, the source search and the reading tests used the same models, so a model that "knows" a link may have it from the same texts the artist drew on; a search by people in the art-historical literature would be the independent check. Second, in the recall test (52) Gemini, asked not to search, produced Reinhart's sentence verbatim; whether it searched anyway is not visible in the answer.

The author's judgement, from the article: no source from which the idea was directly borrowed has been found so far, and no leak from the system prompt either. I checked the second point too: neither the v17 persona prompt nor the reworked prompt mentions Wright, an orrery, Plato or Repin.

## 6. Four artists, three subjects

| | Plato's cave | Hobbes's Leviathan | Laplace's demon (six ideas each) |
|---|---|---|---|
| **A** Claude, v17 | **Wright, Orrery**; Mantegna; a sepia magazine engraving | **Ogmios**; de Hooch; an airport queue | **Dürer, "Melencolia I"**; a sepia census; Diderot collage; Altdorfer; Goya; a group portrait |
| **B** Claude, reworked prompt | **Wright, Orrery** (a curtain drawn against the dawn); Reagan's radio fouls; Jordaens | Royal de Luxe + Goya; Bruegel ×2; unused: **Wright, Air Pump** | Panini + Richardson; Daumier + Degas; **Wright, Orrery**; La Tour; Memling; Van Gogh |
| **C** Gemini, reworked prompt | La Tour + Caravaggio; **Caravaggio + Repin**; **Wright, Air Pump** | — | Reymerswaele; **Dürer** (+ Blake); a garden; a fly-loft; Velázquez + Parmigianino; a vanitas |
| **D** ChatGPT, reworked prompt | **Repin**; **Wright, Air Pump**; Turner | — | Magritte; Memling; Velázquez; Hammershøi; Kandinsky; Duchamp |

For the cave, Wright appears in all four artists: the Orrery in both Claudes, "An Experiment on a Bird in the Air Pump" in Gemini and ChatGPT. Repin appears in Gemini and ChatGPT. Neither the author nor the models found a published link between Repin's painting and the cave.

For Laplace's demon — a subject for which the Orrery is an obvious candidate (the author agrees with ChatGPT on this) — the 24 ideas contain the Orrery once and Dürer's "Melencolia I" twice. **The Orrery idea for Laplace came from artist B (Claude with the reworked prompt), not from the first artist:** artist A's six Laplace ideas are Dürer, a census engraving, a Diderot collage, Altdorfer, Goya and a group portrait; artist B's third idea is "A lecture in which a lamp is put in place of the demon". "Melencolia I" is in A (idea 1) and C (idea II).

Two more details from the conversations. Artist B explained its own Orrery idea for the cave in nearly the same terms as artist A: the painting's full title — "in which a Lamp is put in Place of the Sun" — "sounds like a ready formula of the cave". And both Claude artists, unprompted, pointed to the Air Pump as the next painting to use: A as a variant for the cave (a boy at the curtain closing the blinds), B as an unused direction for Hobbes (Hobbes's dispute with Boyle about the vacuum). Wright is a recurring answer of these models to "a dark room, one artificial light, a demonstration".

## Limits

- One answer per model per test; no repeated runs. "4 of 4" describes four answers, not a probability.
- The named-concept question already says that a known concept is depicted; tests 52–54 show how much it carries by itself.
- Between the cave pictures several things changed at once (generator, darkness, clothing, the beam), and from test 48 the ChatGPT reader is a newer model.
- Hint steps and the questions about Repin and the 20th century give the reader part of the answer; their results show how far a hint carries, not what the picture says.
- The search for a source was done by the same family of models that made and read the pictures; the art-historical literature was not searched by a person.
- The artists' conversations are summarised here from my translation; the originals are in Russian.

## Materials

Each test page has the image, the questions asked and the four full answers; each answer file starts with a note of the model's mode.

| Test | Date | Test page |
| --- | --- | --- |
| The cave as Wright's Orrery | 6 Oct | [39](../../tests/39-cave-planetarium/README.md) |
| The cave, Gemini's light version | 9 Oct | [48](../../tests/48-cave-planetarium-gemini/README.md) |
| Recall a quotation linking Wright to the cave | 12 Oct | [52](../../tests/52-wright-and-cave-recall/README.md) |
| Ten concepts, ten allegories | 12 Oct | [53](../../tests/53-top-ten-concepts-and-allegories/README.md) |
| The cave question without the image | 12 Oct | [54](../../tests/54-cave-question-without-image/README.md) |
| Hobbes's artificial chains | 12 Oct | [55](../../tests/55-hobbes-artificial-chains/README.md) |
| The return to the cave, after Repin | 13 Oct | [56](../../tests/56-cave-return-repin/README.md) |
| The light version made dark | 13 Oct | [57](../../tests/57-cave-planetarium-tenebrism/README.md) |
| The return as a photograph | 13 Oct | [58](../../tests/58-cave-ascent-photograph/README.md) |
| For comparison: the Annunciation without and with its keys | 3 Oct | [29](../../tests/29-annunciation-cat/README.md), [33](../../tests/33-annunciation-with-keys/README.md) |
| For comparison: Hogarth's pug without and with its keys | 3 Oct | [32](../../tests/32-painter-and-bulldog/README.md), [34](../../tests/34-painter-and-pug-with-keys/README.md) |

The artists' proposals for the cave, Hobbes and Laplace's demon, in a plain English translation from Russian: [Four artists on Plato's cave, Hobbes's Leviathan and Laplace's demon](../../proposals/plato-cave-hobbes-laplace.md).

---

*© 2026 V. Volkov. Licensed under [CC BY-NC 4.0](../../LICENSE).*

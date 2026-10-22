# Cat programmer: an experiment with AI and visual creativity

An experiment in AI illustration, run from late August 2026 by a person who does not draw. The question: can AI turn a source — a joke, a poem, a scene from a novel, a historical episode — into an illustration that is not "neuroslop" (AI slop), with the models inventing the idea of the picture themselves and nobody writing the image prompt by hand? Behind it is a wider interest: how AI handles complex social context, creative tasks, genres and cultural detail, and how far the work can be handed over to models acting as "virtual directors" with personas of their own.

The work was shared between several models:

- **Claude** was the main conversation partner, wrote the system prompts for the virtual directors, acted as a director itself (the concept of a picture and the prompt for it), designed and analysed the tests and kept the project's archive;
- **ChatGPT, Gemini and Midjourney** generated the images; ChatGPT also directed some runs and reviewed some texts;
- **ChatGPT, Claude, Gemini and DeepSeek** were the AI readers in the reading tests — and sometimes co-authors, when a reading suggested a new picture or a new test.

Most of the first month went into one joke:

> A cat walks into a café and orders coffee with cream and a pastry. The waiter just stands there, mouth open, then asks in amazement: "You're a cat? A talking cat?! Incredible..." — "Yes, I'm a cat. Are you bringing my order or not?" — "Hold on a second... Listen, could you use a job? It's just, my uncle runs a circus, and he'd take you on in a heartbeat, whatever terms you like..." — "A circus, you say?" The cat closes her eyes dreamily. "That's the place with the acrobats, the jugglers, the lollipops, the cotton candy? Sounds tempting. But what would they need a programmer for?"

Other sources followed: a tavern called "The Merry Night" for a role-playing game, a joke about red ink, the discovery of iodine, Dumas, the Irish poem "Pangur Bán", a meaningless "semantic turbulence" phrase, Plato's cave, the ring of Gyges, Pelevin, "All Cretans are liars", Gogol's "Viy", Shukshin and others. The method changed along the way: first chains of "producer" and "director" roles, then a long system prompt for a virtual director (v7), and in October virtual directors with personas — among them a cat who was once a neural network and became a naive village sign painter, an awakened Egyptian scribe, a frog from the Chōjū-giga scroll and a connoisseur cat who paints modern scenes inside the formulas of old paintings. In all, the project produced about a thousand distinct images.

The materials are published here as articles and reports are prepared.

## Publications

| Publication | Date | About | Materials |
|---|---|---|---|
| **Noir, a Fork, and a Dragon's Tooth** | October 2026 | "psychological" reading tests — images whose meaning rests on an inference from a genre, a custom or a count; hints, false hints as a control, and context | [article](https://vladvolkov.substack.com/p/noir-a-fork-and-a-dragons-tooth) · [detailed report](report/psychological-tests/README.md) · [reader quotes](report/psychological-tests/quotes.md) |
| **Mysterious picture** | October 2026 | why four AI readers recognised Plato's cave in a restaged Wright of Derby, where the virtual director found the idea, and what four virtual directors proposed for the cave, Hobbes's Leviathan and Laplace's demon | [article](https://vladvolkov.substack.com/p/mysterious-picture) · [detailed report](report/plato-cave/README.md) · [reader quotes](report/plato-cave/quotes.md) · [directors' proposals (translation)](proposals/plato-cave-hobbes-laplace.md) · [source check](report/plato-cave/source-check.md) · [Gemini on where Wright came from and the irony (translation)](report/plato-cave/gemini-review.md) |

## What is here

- **[Reports](report/)** — one folder per publication: the detailed report, its images and, where there is one, a selection of reader quotes. Each report identifies its author and describes the relevant AI contributions.
- **[Reading tests](tests/README.md)** — the tests published so far (42), most of them used by the reports, each with its images, questions and saved reader conversations.
- **[Directors' proposals](proposals/plato-cave-hobbes-laplace.md)** — what four virtual directors (two Claudes, Gemini, ChatGPT) proposed for Plato's cave, Hobbes's Leviathan and Laplace's demon; a plain English translation of conversations held in Russian.
- **[Protocols](method/protocols.md)** — how the images were prepared, which questions were asked, and what the numbers can and cannot mean.

```
README.md                  this page
LICENSE                    CC BY-NC 4.0
report/
  <publication>/
    README.md              the detailed report
    quotes.md              selected reader quotes
    img/                   the report's own images
tests/
  README.md                test index
  NN-slug/
    README.md              image, questions, summary
    chatgpt.md  claude.md  gemini.md  deepseek.md
proposals/                 directors' proposals, translated from Russian
images/
  tests/                   every test image, stored once
method/
  protocols.md             preparation, question sets, limits
```

## How to read the tests

- One fresh chat per model for each test, with follow-up questions asked within the same conversation where applicable. There were no systematic repeated runs under identical conditions.
- Counts such as "0 of 4" refer to the four readers' responses at the specified stage of a test; they are not probability estimates. A zero means that none of those responses expressed the target reading under those conditions.
- The questions and contextual information changed over time (see the [protocols](method/protocols.md)). Some tests also used revised images, so changes in responses cannot always be attributed to context alone.
- The tests were intended to explore a range of readings, rather than rank the models.
- A few images were shown to people informally; no systematic study of human readers was conducted.
- The transcripts are reproduced as saved by the author, with mode labels added where needed.
- The summaries on the test pages come from the author's analysis, done together with Claude.

## Models

Every answer file starts with an HTML comment naming the mode, e.g. `<!--Mode: Sol 5.6 High-->`. The first September tests carried their own labels, which are kept as they were.

| Reader | Mode | Notes |
|---|---|---|
| ChatGPT | Sol 5.6 High; GPT-6 High from test 48 | reads pictures made by the same company's image generator |
| Claude | Opus 5.5 Extra | early September: Opus 5 Extra, Sonnet 5 Extra (as labelled) |
| Gemini | Flash 3.8 Extended; Argon 4 High from test 59 | early September: Flash 3.7 Extended (as labelled) |
| DeepSeek | web, DeepThink on | exact model version not independently verified |

## About the images

The visual artwork was generated with ChatGPT, Gemini and Midjourney (except Wright of Derby's paintings in tests 59 and 62). Several images were retouched by the author by hand; the test pages say so where it applies. Some supporting pages, including the manga's notes page, were laid out in HTML by Claude. Some images imitate the manner of a named artist or tradition (Daumier, Reiser, the Soviet magazine *Krokodil*, Chizhikov, Pirosmani, Bruegel, Chagall) or restage a famous painting (van Eyck, Caravaggio, Hogarth, Bruegel, Wright of Derby, Degas) — these are image generators' imitations, not works by those artists. The test copies were re-saved as JPEG without metadata and renamed before being shown to the models. Tests on works by human artists are not included, with two exceptions: tests 59 and 62 show Wright of Derby's original "A Philosopher Lecturing on the Orrery" (c. 1766) and "An Experiment on a Bird in the Air Pump" (1768), both in the public domain, as controls. Test 65 concerns an edit of a painting still under copyright (Reshetnikov, 1952); the picture is not reproduced, only described. Test 66 shows a new contemporary painting that keeps only the arrangement of roles of that painting.

## Not included (yet)

The working notes, the per-case analyses and the drafts (in Russian); the system prompts of the virtual directors and the persona prompts.

## License

Unless otherwise noted, the material in this repository is made available under [Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)](LICENSE), to the extent that the author holds the relevant copyright or similar rights. You may copy, share and adapt the licensed material for non-commercial purposes, provided you give credit — "Cat programmer: an experiment with AI and visual creativity", © 2026 V. Volkov — link to the license and indicate if changes were made. For commercial uses that require permission, contact the author to arrange a separate license. The same terms apply to future additions unless stated otherwise.

The license does not grant rights in third-party material that the author is not authorized to license, and it does not restrict uses that are already permitted by law.

## Disclaimer

These materials document an independent, non-commercial exploratory project on AI-assisted visual creativity and interpretation. AI systems contributed to the concepts, prompts, images and written analysis; some images were also edited by hand. Human and AI contributions are described in the accompanying documentation.

Some images deliberately reference existing artworks, literary sources, artistic styles or cultural traditions; others may resemble existing works unintentionally, as a by-product of generation. They are presented as experimental outputs, not as works by the artists they reference. Signatures, logos or mastheads that appear in images were produced by the image generators and are not genuine. These references do not imply affiliation with or endorsement by the artists, rights holders or companies named.

Model responses are included as experimental data. They may contain factual errors, invented details, stereotypes or offensive content. Their inclusion does not imply endorsement by the author, and they should not be read as statements on behalf of the model providers. Claims made by models, including claims about cultural practices, remain subject to verification.

Some images and texts deal with discrimination, xenophobia or exploitation; these are subjects of the work, not positions it takes. No insult or disparagement of any person or community is intended. Concerns about attribution, factual accuracy, rights or potentially offensive material can be raised through an issue in the project repository.

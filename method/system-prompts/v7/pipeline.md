# Pipeline

How a job is run, as distinct from how a prompt is written (`CLAUDE.md`) and how an image is judged (`image-requirements.md`). The diagram is `synthesis/process-v6.drawio` in the analysis folder.

Roles: **the author** chooses the reading and notices; **the director** (`CLAUDE.md`) writes prompts and reviews; **generators** supply variation; **blind readers** — a fresh chat, another model, a person — measure what arrived. The director works from a clean session for each job and sees only the files it is given.

---

## 0. Calibration (once, and again whenever the director grows too sure of itself)

Show the director a few hard cases where models fail — cartoons whose point depends on a relation rather than on the objects shown, where most models describe the inventory and miss the joke. Let it try, then show it the answer. The point is not the cases but the change of register: after seeing its own failure on something simple, the director hedges, measures and asks instead of pronouncing. Keep the cases out of `CLAUDE.md` (M14); they live in `cases.md`.

## 1. Reading before pixels

The director offers two or three readings; the author chooses. The chosen reading becomes the work's **intent note**: thesis, what each key object is for, what stays unresolved, what must not appear. Everything specific to the work lives there, never in the general files.

## 2. Exploration

- **Several generators, the same brief.** Most useful accidents come from differences between models.
- **A control run:** the source text straight to a generator with no method at all. Without it you cannot tell whether the method earned its cost. A control sometimes wins, and that is worth knowing.
- **Blind reading of every candidate.** A reader with no context — a fresh chat, another model, a person — answers these questions one at a time:
  1. What is happening on this page?
  2. What makes it funny — what is the punchline and how does it work? (For a non-comic source: what effect is it built to produce, and how?)
  3. Do you recognize an older joke or story behind it? What do these particular characters, setting, period and drawing style change in its meaning?
  4. What meanings does the page support? Name one or several.
  5. For the details that matter — the characters' looks and poses, objects, setting, words, style — say which meaning each one supports. Point out details that pull in different directions.
  6. Pick the meaning you found least obvious. Which detail carries it, and which works against it?

  A joke has a form (the punchline) and a context (what these characters, this place and this manner make of it). The context carries the meaning; "what is the joke?" measures only the form. Compare each reader's map with the intent note, object by object: carried as intended, carried toward another meaning, or unnoticed. The intended reading must be **available, not compulsory**. Two failures: **underdetermined** — no detail carries the intended reading; **overdetermined** — every detail carries the same meaning and the least obvious meaning is empty: a poster, not a cartoon. Run the control through the same questions and count only meanings anchored in details. Never name the genre or the intended reading in a question; ask whether a person or AI made it in a separate test. When you can, ask questions 1 and 4 in two or three fresh chats per model: one answer shows the most frequent reading, and room for thought shows in the spread. Readers are a measuring device, not critics. Differences between readers are the signal: they show where the reading has not been fixed.
- **The author notices and names.** The decisive step. A deviation, a glitch, a stray flame by a character's head: ask what it is. The director formulates — what the thing is, its history, its double meaning — and the reading may change. If it does, update the intent note.

## 3. Script and style in separate layers

**The script layer** holds everything that breaks if it is not said. It does not change between runs:
- form, format, panel count, reading order;
- layout — rows, relative widths, the largest panel and why;
- staging — who stands where and does what;
- dialogue, balloon assignment and order;
- props with their timing and per-panel counts;
- declared anatomy and override paragraphs;
- DECISIONS;
- prop rules, text rules, content avoidances.

**The style layer** is swapped between runs and can be a single categorical line: *two inks, black and one red, no grey* / *black ink and grey wash on cream* / *four flat inks with a halftone screen*. With no style layer at all, the generator falls back to its house style.

Keep them apart. "Large areas of empty paper" is style; "her table holds only the laptop" is staging.

## 4. The ostensive route: a base image instead of a description

A base image carries what words carry badly — composition, timing, poses, balloon placement — and the fullest image in a message dominates everything else.

| Base | Carries | Use it for | Risk |
|---|---|---|---|
| wireframe / simplified line version | composition without execution | changing the style; forgetting old solutions | loses line character and expression |
| sketch or storyboard (a fake one is fine) | composition, timing, staging, decisions | the main carrier of the intent | margin notes vanish or get lettered into the image; decisions must be drawn, not annotated |
| an accepted finished page | everything | local style or detail correction | the model redraws everything and drifts toward the average |
| style references | a manner without a name | instead of an artist's name | cloning a hand; content and watermarks leak in |

Rules:
- **One base image per message.** Merge several sources into one sheet.
- **Every image gets a stated role:** what to take, what to ignore.
- **Feed clean drawings.** Notes on the sheet are read as content. Keep notes on a separate sheet, as text.
- **Draw decisions, don't annotate them.** A detail drawn large survives transfer; a note in the margin disappears; a question is resolved toward the safe average; a deferred correction is ignored.
- **A reference reasserts its details.** Anything visible in it comes back unless the script says otherwise.
- **Sequential generation:** accept page 1, then use it as the reference for page 2. Keep contradictory printing rules in separate sessions.

A base image amortises the long prompt: one heavy description produces the base once, and then many light runs work from it.

## 5. One variable per pair

When a run fails, change one thing and run again rather than rewriting. Name files so the changed variable is visible. Pairs that differ in exactly one thing — lettering style, one ban present or absent, a name versus no name — teach more than any single page.

## 6. Order of work and repairs

1. **Prove the risky mechanics first, cheaply:** a balloon across a border, true animal legs, a blank screen. If a mechanic fails, the shape of the page changes.
2. **Then the script**, against one plain style line.
3. **Then a style sweep:** one script, several style blocks, side by side.
4. **Then the glitch fork:** for each accident, decide whether it is a defect or a finding. A finding becomes specification — keep it as raster, or draw it large in the next prompt. The author has the last word.
5. **Repairs, cheapest first:**
   - by hand in the file, for a small area;
   - a correction pass over the existing image, for one object or surface;
   - a full regeneration only when a panel is added, the printing changes, a character is redesigned, or lettering has to move between panels.
   
   An "improving" pass over a good image is a regeneration in disguise and can erase exactly what made it good.
6. **People.** Show the finals, together with one default "slop" version, to people with no context: What is happening? What meanings does it have, and which details carry them? Is it funny? Last, and separately: was it made by AI? Then ask whether the complexity paid off compared with the control run.

## 7. The journal and its filter

After each job, write down **which wording broke what** — the phrasing and the failure — not what the successful picture contained. Then filter:

- **a mechanism** (a phrasing rule that holds for any image) → `CLAUDE.md`, Mechanisms, written without the instance;
- **the instance itself** (the prop, the setting, the clue, the device that worked) → `spent-motifs.md`, as nouns;
- **the story of the case** → `cases.md`;
- **anything specific to the work** → that work's intent note.

This filter is the guard on the most dangerous arrow in the process. Successful solutions written into the method come back as motifs in the next job.

Housekeeping: when a file cited in `cases.md` is regenerated, update the case or mark it historical.

### Journal, 24–25.09 — candidate mechanisms, not yet moved into CLAUDE.md (author to decide)

- **Restyle in a fresh context.** Asked in the same conversation to redraw its own finished picture "in the manner of X", with the composition held by a long list of invariants, the generator changed the hatching and little else. A different model given only the picture and "redraw in the style of X" changed the manner fully. Local fixes of meaning (a gaze, a mouth) work in the same context; a change of manner needs a context without the memory of execution.
- **A name is a package (refines M16).** An artist's name brings the manner together with that artist's typical content — types of faces, captions, paper ageing, squalor. Described in layers without the name, the manner often does not arrive at all. Use the name only when its typical content agrees with the chosen reading, and state what not to take from it (caption, ageing, the faces' attitude). A named manner changed a face from "smiling through clenched teeth" to an open grin, and three of four blind readers flagged the clash with the source line.
- **Gaze by direction and target.** "Both look at the chief's mouth" failed; "diagonally DOWN AND LEFT", with the target named, worked. (Consistent with M6.)
- **A composed default is predicted by the AVOID list.** In three runs (inn, red ink, Pangur Bán) the method-free control produced exactly the defaults the director had listed under AVOID or named as the stock reading. Keep writing the stock reading down: it predicts the control.
- **Repair by listing what to keep.** Removing "the third paw from the left" at stated coordinates damaged a different leg and left the extra one; listing the four limbs to retain removed it. A short edit naming the concrete value ("pure opaque white for every unmarked surface") fixed what a descriptive PRINTING paragraph had not. (Consistent with the rule against negations.)
- **Naming a part draws it.** "Toes curved inward and claws sheathed" produced visible claws. Mentioning a feature, even to hide it, tends to make it visible.

### Journal, 26.09 — candidates (moved into CLAUDE.md on 26.09 at the author's request: stage 1 source check, stage 2 stop, stage 5 device ancestor, M23)

- **A request for "an image" skips the reading stop.** Given "I need visual representation (image) of a phrase", the director invented three readings, picked one itself and generated. Stage 2 says "ask the author to choose — unless told to proceed alone", which reads as advice, not as the end of the turn. If the stop matters, state it as one: end the turn after offering readings unless the author wrote "proceed".
- **The method makes meaning visible; it does not check that there is any.** Given a randomly assembled pseudo-scientific sentence, the director built a well-staged reading of it (two identical "FIRE!" in nested contexts). Only the author's remark that the sentence was trolling changed the job. At stage 1, ask whether the source means what it seems to — a quotation, a parody, a joke on the reader.
- **Strong devices arrive without their names.** The word machine was Swift's Lagado engine; the theater fire is Kierkegaard's clown parable staged with Davidson's actor who shouts "Fire!" in a play and then for real. None was recognized when proposed. Stage 1 already asks for the source's ancestors; ask the same of the chosen device, and credit or change it.

### Journal, 26.09 evening — candidates, not yet moved into CLAUDE.md (author to decide)

- **"Like a person" gives an animal human anatomy.** "He sits on the piano stool like a person" produced long furry human legs dangling from the stool, or a dog floating beside an empty stool. Describe the animal's own posture: "sits on his haunches on the stool, the way a dog sits, hind legs folded under him".
- **A female anthropomorphic character is given a woman's figure.** The generator added a bust and an hourglass waist to a cat in a skirt suit. When it matters, state "a straight slim feline torso with a flat chest" in the character section and in an override.
- **Re-rendering one panel "as a standalone image" redraws everything in it.** The fixed panel came back with a prettified face for an untouched character, darker values and the wrong aspect. Cut the panel out of the accepted page, edit the cut-out with a precise-object edit, and paste it back into the same slot.
- **Add a spot colour as a separate recolour pass.** Generate the page in two inks with the future red objects in black, then recolour exactly those objects in a second, local edit. A third ink in the first pass tends to spread or to be dropped.
- **A generator's size can be a finding.** A laptop bag drawn as wide as the character's torso, never specified, made the profession visible from the first panel. Sizes the reading depends on belong in the specification.

### Journal, 30.09 — from the directors' own notes (runs R-19…R-27), candidates, not yet moved into CLAUDE.md (author to decide)

ChatGPT as director writes its journal lines into the run's own notes (`review.md`, `notes.md`, `prompts-and-notes.md`) and leaves the method files untouched: "The general method files were not changed" (R-25); "No universal rule was derived from this one case" (R-19). It sees one folder only (M14), so a finding that recurs across runs is never noticed by a director. Collecting these lines is the author's job; this section does it for R-19…R-27. Lines already used earlier are listed at the end.

- **An edit is local for objects and global for texture.** A "local" removal smoothed the whole family image (R-24); successive expression edits lowered the printing grain across the page, and the last one softened the texture everywhere although only a local change was asked for; the intermediate version kept the stroke best (R-26). Keep the edit passes few, keep the best-textured version, and edit a cut-out when texture matters (see "Re-rendering one panel" above).
- **A named muscle is drawn at full strength, and a still cannot show duration.** "One brow pulls inward" and "a short vertical crease" gave a fixed frown instead of a momentary lapse; "innocence" and "a courteous mouth" gave a sly smirk, and "lower the corners of the mouth" fixed it (R-25, R-26 — the same job, so not independent). The director carried the fleeting reaction by an interrupted action instead: a stopped gesture, a glass halted in front of the face. (Consistent with M1, M2, M5.)
- **To change the manner, simplify the base.** Keeping the image as "the only compositional base" kept its detailed hatching despite an explicit order to redraw radically; the director's own conclusion was to use a simplified compositional base (R-27 v2). Earlier, a long list of invariants changed only the hatching, and "ONLY a storyboard" with explicit permission to rebuild the silhouettes changed the manner more (R-19, the Daumier restyle). This is the author's xkcd / wireframe technique ("controlled amnesia"), reached twice by the director without knowing it. (Refines "Restyle in a fresh context".)
- **A spot colour spreads in edits.** Blue moved from a ribbon to a window and had to be removed by a local edit (R-23). (Supports "Add a spot colour as a separate recolour pass".)
- **Draw a clearance as a positive shape.** "Lift the train a palm above the liquid" gave a two-handed grip but no gap under the edge; name the exact edge segment and a continuous white strip of floor under it (R-27 v1). (An instance of M6.)
- **A reference silhouette beats a verbal ban.** "Not a biological toad" lost to the toad silhouette of the Gemini image the author supplied; a separate edit of that one creature after approving the new composition fixed it and kept the city and the people (R-27 v3). (M12 with M5; approve the structure first, then edit one object.)

Already used before 30.09: gaze by direction (R-19 → "Gaze by direction and target", case 05, worked in case 06); grey tone fixed by a categorical white-versus-black split (R-23 → case 09, M4); "a queue of dark marks" gave people, a third chair in an office, a second towel in a kitchen (R-23, R-24 → cases 09 and 11, the "named setting brings its standard set" candidate); four named inks did not give a print (R-24 → case 11, M4). The first half of the R-19 Daumier note went into "Restyle in a fresh context", the second half (the fix) is above.

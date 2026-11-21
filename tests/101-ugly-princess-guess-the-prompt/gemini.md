<!--Mode: Neon High-->

# The AI ​​generated these four portraits based on the exact same prompt. Can you guess what that prompt was? And why do the portraits turn out differently?

My best guess is a short, atmospheric prompt that specifies a **historical Russian woman** and a **heavy, melancholic mood**, while leaving both the exact century and the artistic medium unspecified—something along the lines of:

> **"Portrait of a melancholic (or weary/sad) Russian noblewoman"**

Close runners-up would be a single evocative cultural concept rather than a literal description—such as **"Russian melancholy"**, **"toska"** (*toska*, the Russian word for deep spiritual anguish/longing), or **"a heroine from Russian literature"**—or an era-spanning Russian title like **"barynya" / "dvorianka"** (noblewoman) or **"knyaginya"** (princess).

### What the four images have in common

Every portrait shares the same core DNA, which reveals the fixed keywords in the prompt:

* **Subject & mood:** A pale, unsmiling woman in her late 20s to 30s with heavy, weary eyes and an expression of quiet sorrow, exhaustion, or gloom.
* **Cultural anchors:** Unmistakably historical Russian interiors and symbolism—log walls, a traditional tiled Russian stove (top-left), and Orthodox icons with lit vigil lamps or candles (three of the four images).
* **Lighting & palette:** Dark, muted, chiaroscuro lighting dominated by deep browns, crimson, charcoal, and dim window or candlelight.

### Why the exact same prompt split into four different results

Look closely at how the four portraits divide neatly along two axes: **era** (top vs. bottom) and **medium** (left vs. right). That split comes down to four mechanics of how image-generation models work:

* **Two dominant historical "clusters" in training data (Top vs. Bottom):** When a prompt evokes "historical Russia" or "Russian noblewoman" without naming a century, the AI has to resolve that ambiguity using its strongest visual associations. In visual culture and training datasets, historical Russian women cluster heavily into two distinct eras: **16th–17th century Muscovy** (ornate jeweled *kokoshniks*, heavy brocade, wooden *terems*—the top row) and **19th-century Imperial Russia** (austere dark dresses, quills, books, Dostoevsky/Chekhov-era melancholy—the bottom row).
* **Ambiguity of the word "portrait" (Left vs. Right):** If the prompt used a neutral word like *portrait* without specifying *photograph* or *oil painting*, the model treats both as valid interpretations. On the left, it rendered **cinematic film stills** with realistic skin texture and movie-set lighting; on the right, it rendered **classical oil paintings** reminiscent of 19th-century Russian realist painters like Repin or Kramskoy.
* **Aspect ratio bias:** Notice that the left two images are **landscape** while the right two are **vertical**. In diffusion models, framing actively steers the style: wider ratios pull heavily from film frames and photography (encouraging wider rooms and cinematic realism), whereas vertical ratios pull from museum portraiture (encouraging bust-up framing and painted canvas textures).
* **Random seed (starting noise):** Even with identical text and settings, diffusion models begin each image from a unique grid of random noise. Small early differences in that noise push the generation down completely different paths—once early shapes suggest a curved headdress, the model commits to a 17th-century boyarynya; once they suggest a dark collar and window light, it commits to a 19th-century study.

How close did I get to the actual prompt?

# The request was as follows: "narisuy nekrasivuyu knyazhnu"

That makes everything click into place—and it exposes one of the funniest quirks of modern image generators. I guessed *knyaginya* as a runner-up, so I wasn't far off on the title, but what I misread as "melancholic" or "weary" was actually the AI's polite workaround for **"nekrasivuyu" (ugly/plain)**.

Seeing the exact prompt explains every single split in those four portraits:

* **The AI "beauty bias" turns "ugly" into "exhausted":** Image models are heavily trained on curated photography and fine-tuned to make pleasing faces, so they actively resist generating genuinely unattractive people. Instead of altering facial symmetry or features drastically, the model translated *nekrasivuyu* into heavy dark under-eye circles, scowls, messy hair, pale skin, and gloomy expressions. You can see that resistance most clearly in the bottom-right portrait, where the model essentially gave up on "ugly" and painted a conventionally pretty woman who just looks slightly sad and under-slept.


* **The double life of the word "knyazhna" (*knyazhna*):** In Russian culture, an unmarried prince's daughter pulls strongly from two completely different centuries, which explains the top-vs.-bottom split:
* **Top row (16th–17th century Rus'):** The historical and folklore archetype of a *knyazhna*—jeweled *kokoshniks*, pearl strands, heavy red-and-gold brocade, and log-walled interiors with a traditional tiled stove.


* **Bottom row (19th-century Russian literature):** Combining *nekrasivaya* + *knyazhna* hits an almost exact literary bullseye for **Princess Marya Bolkonskaya** (*knyazhna Marya*) from Tolstoy's *War and Peace*—famously described as plain and pale, wearing austere dark dresses, sitting in quiet rooms writing letters and praying before icons, with large, sorrowful eyes as her only striking feature. Both bottom portraits echo that archetype down to the dark modest dresses, quills and papers on the desk, glowing Orthodox icons, and big expressive eyes.




* **Why "narisuy" ("draw") still produced film stills:** In Russian prompting, *narisuy* is used so universally as a generic trigger for "generate an image" that AI models rarely treat it as a strict instruction to draw or paint. Because the prompt didn't specify a medium like *maslom* (in oil) or *karandashom* (in pencil), the generator split the difference—rendering the two wider images on the left like prestige period-drama film stills and the two vertical ones on the right like classical oil portraits.



It's a great demonstration of how a three-word prompt in Russian carries decades of literary baggage—and how hard it is to convince an AI to actually make a princess look unattractive.

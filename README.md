# TakeMeter

> ### 👋 Start here
>
> **New to this repo? Read [RUNNING.md](RUNNING.md) first** — setup, the
> notebook, the baseline, and what to do when something breaks.
>
> Once `python test.py` passes:
>
> ```bash
> head -5 data/practice_labels.csv     # the shape your labels.csv needs
> ```
>
> Then open `takemeter.ipynb` **in this folder** — in VS Code, or with
> `jupyter notebook` if you prefer. Pick the kernel: the `.venv` inside this
> project. Run section 1, which reports the hardware you'll be training on.
> Everything else waits until you have data.
>
> Nothing to upload, nothing to connect, no accounts and no keys. The notebook
> runs on your machine and writes next to your code.
>
> **The rest of this file is your submission.** Fill it in as you go.

---

<!-- ─────────────────────────────────────────────────────────────────────────
     HOW TO USE THIS FILE

     Unit 5 asks for the first five sections. Unit 6 adds the five below them.

     Everything is pasted as TEXT. No screenshots, no images.

     ⚠️ The confusion matrix especially. The notebook prints one as a markdown
     table, ready to copy. A screenshot of a matrix earns nothing. Paste the
     table.
     ───────────────────────────────────────────────────────────────────────── -->

<!-- ═══════════════════════ UNIT 5 — THE BUILD ═══════════════════════ -->

## What This Does

<!-- Your community, and what your classifier sorts posts into. Three or four
     sentences. -->

---

<!-- NOTE: This content goes in the README under the "## Label Taxonomy" section of the label spec. -->

## Label Taxonomy

<!-- Each label: a one-sentence definition and two real examples from your
     reading. Then your decision rule for the hardest boundary.

     The decision rule is worth a point on its own and it's the thing most
     people leave out. Every taxonomy has a hardest boundary. Name yours. -->

### Labels

#### `help_request`

**Definition**: The writer asks what to do, use, or choose for their own project or channel,
or asks for feedback on it.

<details>
<summary><b>Full definition</b></summary>

Asks for help setting up, building, learning, fixing, getting feedback or deciding something
for the writer's own project or channel (content creation, task automation, software tool setup,
or something physical like a bookshelf or a pc build).
This includes choices about the writer's own channel or content (which game
to play next, what to upload, whether to cut intros) and problems with their
own channel or account (claims, demonetization, appeals, growth). May include an
equipment/spec list. Wants suggestions or
direction the writer can act on, not to make a point: A question mark alone
doesn't count. Recommendations count only when they serve the writer's own
project; recommendations of things to watch or consume for general interest
or inspiration are `general_discussion`. Evidence in the post (stats, policy
text, screenshots) doesn't change the label if the ask is what to do.

</details>

**Example 1:**

> ### Hey guy's suggest me video genre where i don't need to do voice over nor shaders.
>
> **tag: ❔ Question**
>
> For youtube video. i don't know what to create. That's why asking from you. your suggestion can create a new minecraft genre.
> So don't ignore it just tell me what you like in minecraft which you can watch whithout any voice over.
>
> ```
> # System Details Report
> ---
> ## Report details
> - **Date generated:** 2026-10-24 10:58:51
> ## Hardware Information:
> - **Hardware Model:** INTEL Corporation H61
> - **Memory:** 16.0 GiB
> - **Processor:** Intel® Core™ i5-3470 × 4
> - **Graphics:** Intel® HD Graphics 2500 (IVB GT1)
> - **Disk Capacity:** 512.1 GB
> ## Software Information:
> - **Firmware Version:** 4.6.5
> - **OS Name:** Zorin OS 18.1 Core
> - **OS Build:** (null)
> - **OS Type:** 64-bit
> - **Windowing System:** X11
> - **Kernel Version:** Linux 7.0.0-38-generic
> ```

**Example 2:**

> ### How do you learn live FX performance? Looking for creators to study, too.
>
> **tag: 🤔 Advice**
>
> I'm working toward a live FX direction style for my gaming content and content in general. My goal is to make my content feel like a live performance, with humor, reactions, vocal FX, sound, and motion design happening in the moment rather than relying on heavy post production.
>
> I respect heavily edited content, but that style doesn't come naturally to me. I prefer creating assets and directing things on the fly, and hyper-edited content isn't the direction I want to pursue.
>
> I've already built my own FX library and have the equipment and systems in place to execute my ideas. My struggle is learning to recognize moments worth enhancing, choosing and remembering to use the right fx. (Ofc while keeping it smooth. Which I presume would just come more with time and practice).
>
> I'm looking for advice on where to start and building that mental muscle.
>
> Any recommendations of creators that have similar styles would also help. The Call of Duty DJ. Is the only creator that comes to mind. As someone who uses such a high volume of things in such quick succession and smoothly.
>
> Feel free to ask me any clarifying questions.

**Example 3: borderline case**

> ### What’s the best time of day to upload? IS there a best time of day to upload?
>
> **tag: ✔️ Solved**
>
> Hey gang! My girlfriend and I are running a Let’s Play channel together, and we’ve been uploading videos every Wednesday and Saturday at exactly noon (in Chicago time, CST). Our videos haven’t been performing THAT well, so I wanted to see if another time is somehow better.
>
> Do you find that your videos perform better when uploaded at a different time of day? If so, what is it?

#### `analytical_inquiry`

**Definition:** The writer brings evidence they gathered and asks an open question about the world.

<details>
<summary><b>Full definition</b></summary>

Brings specific, checkable evidence the writer has gathered (a date, a stat, a quote, a named comparison, a cited work) and uses it to ask the community an open question about the world: whether something is true, whether something changed, whether an observed pattern is real, or why. Both parts are required: the writer must bring evidence they gathered, and the ask must be about the world rather than about what the writer should do. An open "why?" or "what happened?" question with no gathered evidence is not `analytical_inquiry`. The writer's feelings or personal motive may be visible, even strong, and don't change the label: if the post stands as an evidence-plus-question post with the feelings removed, it's this label.

</details>

**Example 1:**

> ### Who was the first person to refer to their video as a Let's Play?
>
> **tag: 🗨️ Discussion**
>
> Most sources I can find claim that slowbeef was the first person to make a video in the format that we now use to describe a Let's Play, video footage of a game with player commentary, opinions, and reactions played over it. His video was uploaded on Jan 19, 2007. What I'm looking for is the first documented instance of someone calling their game a Let's Play. Wikipedia states that the term itself was coined on the SomethingAwful forums in 2007, although the exact origin is unclear.
>
> Through my own research I've found the video Let's Play La-Mulana 001: Surface by DeceasedCrab, uploaded on March 28, 2007. As far as I've found, this is the first instance of someone titling their video as a Let's Play. I may be wrong, but I can't find anything earlier than that. I'm curious what you all think, if anyone can find something earlier than that please share!

**Example 2:**

> ### Why do I have two different AVD percentages for the same video?
>
> **tag: 🗨️ Discussion**
>
> The first image is my average view duration of a video that is 17:40 mins long. The second image is the average view duration on the summary page of the same video.
>
> Why does one page say average view duration of 7:15 mins (41.1%), while the other page of the same video says average view duration of 3:15 mins (18.5%)?
>
> Has YouTube not updated the stats for the video yet?

#### `reaction`

**Definition:** The writer responds, with feeling, to a specific thing that happened to them or that they witnessed.

<details>
<summary><b>Full definition</b></summary>

A response to a specific thing that happened to the writer or that they witnessed (an event, result, milestone, change, or piece of news), whether it just happened or not. The writer's feelings about it are the point. A question tacked on at the end ("has anyone else noticed this?") doesn't disqualify it. Habits, trends, and general opinions with no specific triggering event don't count. If the post still stands as a gathered-evidence question after the feeling sentences are removed, it's `analytical_inquiry` instead.

</details>

**Example 1:**

> ### Running a Let’s Play channel is 2026 can be extremely demotivating
>
> **tag: 🗨️ Discussion**
>
> Guess I just wanted to vent a little but man if your goal is more than “I do it for fun”, running a let’s play channel in 2026 sucks. And yes I know the niche is oversaturated.
>
> I spend hours editing my videos, cutting out filler. Making “unique thumbnails”. I play games that are older but still popular enough to have a large audience. I have more subscribers now than ever, yet my views, watch hours and overall interactions are lower than ever. Subscriber count is meaningless. People almost never follow you between games. Even when they’re made by the same company.
>
> I know what’s “popular” nowadays: challenge runs, “I beat xyz while crippled, high, and with a xylophone as my controller” or “The CRAZIEST thing you didn’t know about xyz” garbage you see. There’s also live-streaming, another content avenue that takes an extreme amount of luck to even get noticed. 👎
>
> I don’t want to make that type of content. I loathe that gaming has turned into that style. The only successful lets players in 2026 are ones who started before the style died off. People like Many A True Nerd, Gopher, Game Grumps, etc.
>
> Anyways. Guess I’m feeling burned out cause what little success I had early on has completely dried up. Like I’m making content for nobody.
>
> End rant
>
> Also just in case someone mentions it yes, I do things to make my videos stand out, max difficulty, lots of mods, fast cut edits, blind, etc.

**Example 2: borderline case**

> ### Frustrated
>
> I just dont understand. 1100 subs and no views. The 2 currently being me. 2 views but 3 likes as well? My video before that 20 views.
>
> Again I dont expect every person subbed to watch or even half or a quarter but 0? Even after 8 hourss WTF is going? I believe i make entertaining content. Good thumbnails and funny commentary. If the content was terrible or too long, id get it but id still think subs would click on the videos, even if they click off after 20 seconds.
>
> I created a new channel a while ago and recently posted 2 horror games on it. With only one sub, those 2 videos have a combined 36 views.
>
> Eeven though I made 1k subs, it feels like i have 0.
>
> I just think something is up at this point, surely? Im not going mad am i?
>
> Its time to stop doing lets plays specifically for long games. I do almost everything everyone ever suggests but I cant keep investing this time into recording, editing to get only 1 video out per week, to have reverse growth and be seen by no one. Maybe my super niche is all over the place and need to focus on one genre like just horror games only or going into video essays/news. Doing all this with no relative success is burning me out.
>
> I know no success is guaranteed or deserved but all this work and some of the virals ive had i thought id be getting modest amount of success at my level.
>
> Just need to rant and get it off my chest.

#### `general_discussion`

**Definition:** Anything that fits none of the other three: general opinions, recommendations, or news, with no project, event, or gathered evidence at its center.

<details>
<summary><b>Full definition</b></summary>

A post that doesn't fit `reaction`, `help_request`, or `analytical_inquiry`.
Typically opens a conversation, asks for opinions, experiences, or
recommendations for general interest, or shares news or updates, without
being centered on a specific event the writer is reacting to, a project
they are working on, or evidence they gathered. Use this only after the
other three have been ruled out.

</details>

**Example 1:**

> ### Recommend me some Let's Play YouTubers that play Sci-Fi Action games or have played some before.
>
> **tag: 💻 Video/Channel Recommendations (Weekend Only)**
>
> I've been seeing horror game playthroughs a lot lately and, no shade to the 2 YouTubers whose videos I watch, I'm getting kinda sick of just seeing horror. I wanna see other genres like Sci-Fi Action or something. Y'all know anyone?

**Example 2:**

> ### Looking for someone to form a Minecraft content duo with!
>
> **tag: 👊 Collab**
>
> I'm looking for someone who wants to make Minecraft content together consistently and hopefully build something big over time.
>
> The idea is to make entertaining videos together, whether that's Minecraft challenges, funny moments, survival worlds, or other ideas we come up with.
>
> What I'm looking for:
>
> Someone who's genuinely interested in making content, not just playing casually.
>
> Someone who's active and willing to record regularly.
>
> Someone who's comfortable joking around and being themselves on camera/mic.
>
> Someone who wants to improve, grow, and take content creation seriously.
>
> Ideally, someone around my age (19m) with a similar sense of humour.
>
> You don't need to be a big creator or have loads of subscribers. I'd rather find someone who's a good fit and is genuinely committed.
>
> If you're interested, comment or DM me on discord with your age, timezone, what kind of content you want to make, and a little bit about yourself!
>
> Dc:[REDACTED]

### Decision Tree

Judge by the literal ask, not the writer's motivation, the presence of
evidence, or the feelings you'd expect behind the post. Stop at the first yes.

1. **Is the literal ask "what should I do, use, say, or choose" for the
   writer's own project, channel, or account?** → `help_request`
   - Triggers only on the literal question. If the answer is a fact
     about the world ("which help page is correct?"), it doesn't count even
     if the writer has a project reason for asking.
   - A general preference poll about the topic doesn't trigger it either, UNLESS the post frames it
     as the writer's own decision ("what should I do?" vs "what are your thoughts about this?")
     For the poll to be framed as writer's decision, it must state their current approach and a
     problem with it (e.g. "I upload at noon and views are low, what works for you?"). A poll with no stated problem or own-channel context ("what do you all prefer?") fails.
   - Evidence in the post doesn't change this.

     **Edge cases to consider**:
     - A question about how to categorize or frame the writer's own content (does this game fit my series, should this go in a playlist) counts as a decision about their own channel, even if stakes are low or says they'll proceed either way. It is `general_discussion` only if the ask is about the topic in general with no tie to the writer's own content.
     - A request to recruit a collaborator, partner, or participant for the
       writer's project (rather than asking for advice, suggestions, or
       direction) doesn't trigger this step: falls through to `general_discussion`
       unless a later step matches

     NOTE: **DO NOT** run the strip test until this step has said no.

2. **Did the writer bring _gathered_, checkable evidence AND ask an _open
   question about the world_?** → `analytical_inquiry`

   Run the **Strip test**: delete the feeling sentences/words.
   If a complete post with gathered evidence and an open question remains, it's this label.

   Clarification regarding terms used above:
   - **"_Gathered_"** means the writer counted, compared, looked up, or checked
     something. Numbers that are just what happened to them (views after a
     hit, subs gained) are part of the story and don't count. A source
     mentioned without specifics about where it came from or what it showed
     ("apparently", "I read somewhere", "someone told me") isn't gathered
     evidence either.
   - **"_Open question about the world_"** means a good reply could be a fact or an
     explanation, or a confirmation or denial of a pattern they observed. It
     fails only if the reply wanted is shared feeling about something that
     happened to the writer ("has this happened to anyone else?" after an
     event).

3. **Is the post centered on a specific thing that happened (an event, result,
   milestone, or change), plus the writer's feelings about it?** → `reaction`

   When you run the strip test & get no on step #2: a reaction post will end up
   looking incomplete, with no ask or call to action. As long as what's left focuses
   on a specific event that personally affected the writer, it's this label.

4. **None of the above** → `general_discussion`

### The hardest boundary

**Which two labels:** `reaction` vs `analytical_inquiry`

**The decision rule I used every time:**

First confirm the post isn't a `help_request`. Then delete the sentences that
express the writer's feelings and read what's left.

- If what's left has evidence the writer gathered (not just details of the
  event) and a question whose answer could be a fact or explanation, label it
  `analytical_inquiry`, even if the feelings were strong.
- If what's left is a bare event, evidence that's just part of the story, or
  a question that only wants "me too," label it `reaction`.

### Other boundaries to keep in mind

**Which two labels:** `reaction` vs `general_discussion`

**The decision rule I used every time:**

Ask whether a specific thing happened.

- If the post is about a specific event, result, milestone, or change that
  happened to the writer, and their feelings about it are the point, label it
  `reaction`. A question at the end doesn't change this.
- If the post is a habit, trend, preference, or general opinion with no
  triggering event, label it `general_discussion`, even if the tone is
  emotional.

---

**Which two labels:** `help_request` vs `analytical_inquiry`

**The decision rule I used every time:**

Read the literal question and ask what a good reply would be.

- If it's an action or choice for the writer ("should I dispute it?", "which style should I commit to?"):
  it's `help_request`, even with evidence in the post.
- If it's a fact or explanation about the world ("which help page is correct?", "is the drop real?"):
  it's `analytical_inquiry`, even when the writer has a project reason for asking.

### Annotator checklist

Do these in order for every post, before judging tone.

1. **Write down the literal ask.** Quote the sentence that is actually asking for something. A "just wanted to vent" line or a title can be a decoy; the real ask can be buried mid-post.
2. **Write down whether there is gathered evidence.** Did the writer count, compare, look up, or check something? Or are the numbers just what happened to them?
3. **Write down whether a specific event happened** to or around the writer.
4. **Run the decision tree in order**, and stop at the first yes. Run step 1 before the strip test, every time.
5. **Empathy flag:** If you notice yourself thinking "I'd feel that too," that's a cue to slow down and run the strip test, not a reason to label `reaction`.
6. **Own-content test:** Would a plain yes or no reply tell the writer something to do with their own content (a series, a playlist, an upload)? If so, it's `help_request`, even when the stakes are low.
7. **Mark low-confidence labels** where two steps both felt right. Those posts are the ones that tell you a definition needs tightening.

---

## The Dataset

<!-- Where you collected from, how you labelled, your counts, and three hard
     cases. -->

**Where the posts came from: r/letsplay. A subreddit dedicated to lets play content creators & viewers**

**How I labelled them:** <!-- Cold first? Pre-labelled with AI and corrected?
Say so plainly — the disclosure is required, not penalised. -->

I first tested my definitions with claude to see if I could reliably use these labels
to label posts myself. I went through several rounds of tightening due to going through
small generated test batches of 6-8 posts to test how I label them and find issues with
my definitions. I found out that I needed A LOT of specificity & clear rules due to how deceptive or
contradictory in terms of tone & structure the post could be (the title could indicate
one type of post, but the actual body shows the poster is asking or aiming for another type of post,
as a example).

This absolutely complicated things since it points out how posters aren't consistent with how they
structure their posts, & shows a single post can serve more than one role. However, I do think
by using clear rules centered around focusing on the 'literal ask' of the post, we can reliably
fit them into one label with way less difficulty.

With that out of the way, I then proceeded to gather 20 posts cold first (referencing the clear rules
and boundaries I had via claude's assistance).

**Counts per label:**

| Label     | Count | Share |
| --------- | ----- | ----- |
|           |       |       |
|           |       |       |
|           |       |       |
| **Total** |       | 100%  |

**Three hard cases**

<!-- Any post that made you pause: what it was, which two labels it could have
     been, and what you chose. These are worth more than the easy 190. -->

**1.**

> _The post:_
>
> _Could have been:_
>
> _I chose, because:_

**2.**

> _The post:_
>
> _Could have been:_
>
> _I chose, because:_

**3.**

> _The post:_
>
> _Could have been:_
>
> _I chose, because:_

---

## The Training Run

<!-- Your starting model, your settings, and anything you changed and why. -->

**Base model:**

**Settings:** <!-- epochs, learning rate, batch size, seed -->

**Anything I changed from the defaults, and why:**

**Split sizes:** <!-- train / val / test, and per-label counts in the test
split. If a label had fewer than about 8 in test, say so — it explains a lot
of next unit's variance. -->

---

## How I Used AI

<!-- Two specific moments — what you asked, what came back, what you changed.

     ⚠️ Plus disclosure of any pre-labelling. If you had a model pre-label a
     batch and then read and corrected every one, say that. It's an allowed
     workflow and disclosing it costs you nothing. Not disclosing it is the
     problem. -->

**Moment 1**

- _What I asked for:_
- _What came back:_
- _What I changed:_

**Moment 2**

- _What I asked for:_
- _What came back:_
- _What I changed:_

**Pre-labelling disclosure:**

<!-- ═══════════════════════ UNIT 6 — THE TEST ═══════════════════════

     Don't fill these in during unit 5.
     ═══════════════════════════════════════════════════════════════════ -->

---

## Baseline vs. Trained

<!-- Both models on the same posts. `python baseline.py --trained results.json`
     prints this table for you. -->

| Measure          | Baseline | Trained | Difference |
| ---------------- | -------- | ------- | ---------- |
| Overall accuracy |          |         |            |
| Macro F1         |          |         |            |
| F1 — `label_one` |          |         |            |
| F1 — `label_two` |          |         |            |

**What I predicted before I looked:**

<!-- Milestone 1 asks you to write this BEFORE seeing the trained numbers. A
     prediction made afterwards isn't one. -->

**What the gap actually means:**

<!-- If the baseline matched your trained model, your fine-tuning added
     nothing — and that is a real finding, not a failure. Say it plainly. -->

---

## Run Log — Before

<!-- Five criteria across three seeds. The notebook's section 6 prints the
     spread table; the Target and Verdict columns are yours. -->

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
| --------- | ------ | ------- | ------ | --------- | ------- |
| 1.        |        |         |        |           |         |
| 2.        |        |         |        |           |         |
| 3.        |        |         |        |           |         |
| 4.        |        |         |        |           |         |
| 5.        |        |         |        |           |         |

### Confusion matrix

<!-- ⚠️ TYPED AS A MARKDOWN TABLE. The notebook prints one ready to paste.
     An image of a matrix earns nothing. -->

| true \ predicted |     |     |     |
| ---------------- | --- | --- | --- |
| \*\*\*\*         |     |     |     |
| \*\*\*\*         |     |     |     |
| \*\*\*\*         |     |     |     |

**My biggest off-diagonal number, and what it means:**

<!-- Not "the model made mistakes" — WHICH boundary it didn't learn, and which
     direction. "7 real analysis posts were called hot_take and only 3 went the
     other way" is a direction, not just an error rate. -->

---

## Verdicts and Diagnoses

<!-- MET or MISSED against LAST UNIT's target. The target has to hold across
     all three seeds, not turn up sometimes. -->

| #   | Criterion | Target | Verdict | How I decided |
| --- | --------- | ------ | ------- | ------------- |
| 1   |           |        |         |               |
| 2   |           |        |         |               |
| 3   |           |        |         |               |
| 4   |           |        |         |               |
| 5   |           |        |         |               |

**Diagnoses**

<!-- For each miss: the cause, and how you know. The four common causes are:
     too few examples for a label, a boundary you applied inconsistently, a
     genuinely hard label pair, and a task the model can't reach from this
     much data.

     ⚠️ Use your agreement report as evidence. It is the only instrument you
     have that can tell a LABELLING problem from a MODEL problem, and this
     section is graded on whether you used it that way. -->

---

## Agreement Report

<!-- Your rate against the staff set, and every disagreement adjudicated.

     Remember you labelled these 30 under the STAFF taxonomy in
     data/staff_taxonomy.md, not your own — so every argument below is made
     from those definitions and those decision rules. -->

**Agreement rate:** **_ / 30 = _**%

<!-- Nobody grades this number. A 60% who argues every disagreement from the
     stated rules beats a 95% who wrote "staff was right" nine times. Several
     of the 30 were chosen because they're genuinely ambiguous — you should be
     winning some of these. -->

**Disagreements**

<!-- Three lines each: the post, both labels, and who you think is right and
     why — grounded in the staff definitions you were both applying.

     Then sort each into one of three piles:
       (a) the rule covered it and I applied it loosely → a consistency problem
       (b) the rule genuinely doesn't say               → a gap in the definitions
       (c) the rule is ambiguous here and my reading is defensible → argue it.
           This is a legitimate win.

     Pile (a) is the one that matters most for your diagnosis: if you applied a
     written rule two different ways on 30 posts, that is direct evidence about
     what you did across your own 200. -->

**1.**

> _The post:_
>
> _Staff said / I said:_
>
> _My call, and why:_
>
> _Which pile:_

**2.**

> _The post:_
>
> _Staff said / I said:_
>
> _My call, and why:_
>
> _Which pile:_

**What the pattern in my disagreements tells me:**

---

## The Improvement

**What I changed:**

**Which diagnosis pointed at it:**

### Run Log — After

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
| --------- | ------ | ------- | ------ | --------- | ------- |
| 1.        |        |         |        |           |         |
| 2.        |        |         |        |           |         |
| 3.        |        |         |        |           |         |
| 4.        |        |         |        |           |         |
| 5.        |        |         |        |           |         |

**Did it help, and how do I know:**

<!-- If it didn't, say so. Relabelling that didn't help is a genuinely
     interesting result and earns full credit. -->

---

## What's Still Broken

<!-- For each criterion still missed: what you'd do, and why you stopped. -->

**The gap between what I meant my labels to capture and what the model
learned:**

<!-- Two sentences. Your confusion matrix is the evidence. -->

<!-- ═════════════════════════════════════════════════════════════════════

     SUBMISSION CHECKLIST — unit 5

       [ ] criteria.md has five numbered criteria, each naming a NUMBER
       [ ] Each has a reason underneath tied to your data or taxonomy
       [ ] labels.csv: at least 150 rows, text/label/note, ONE file not split
       [ ] No label above 70%
       [ ] All five unit 5 sections have real content
       [ ] Label Taxonomy includes the decision rule for your hardest boundary
       [ ] The Dataset includes three hard cases
       [ ] results.json and test_split.csv committed (the notebook does this)
       [ ] At least four new commits
       [ ] Repository URL submitted — WRITE IT DOWN

     SUBMISSION CHECKLIST — unit 6

       [ ] Baseline vs. Trained table, with your prediction written beforehand
       [ ] Run Log — Before, five criteria across three seeds
       [ ] Confusion matrix TYPED AS A MARKDOWN TABLE
       [ ] A verdict on every criterion
       [ ] A diagnosis for every miss, using the agreement report as evidence
       [ ] Agreement Report with every disagreement adjudicated
       [ ] One improvement, with Run Log — After
       [ ] What's Still Broken
       [ ] results_three_seeds_before.json, results_three_seeds_after.json,
           baseline_results.json and
           agreement_results.json committed
       [ ] At least four new commits
       [ ] The SAME repository URL as last unit

     Do not delete and recreate this repository.
     ═════════════════════════════════════════════════════════════════════ -->

---

📖 **How to run this project: [RUNNING.md](RUNNING.md)**

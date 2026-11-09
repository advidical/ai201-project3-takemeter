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

**Definition:** The writer asks what to do, use, or choose for their own project or channel, or asks for feedback on it.

<details>
<summary><b>Full definition</b></summary>

Asks for help setting up, building, learning, fixing, getting feedback or deciding something
for the writer's own project or channel (content creation, task automation, software tool setup,
or something physical like a bookshelf or a pc build).
This includes choices about the writer's own channel or content (which game
to play next, what to upload, whether to cut intros) and problems with their
own channel or account (claims, demonetization, appeals, growth). May include an
equipment/spec list.

Wants suggestions or direction the writer can act on, not to make a point: A question mark alone
doesn't count. The ask can be _implied_: the post describes a problem with
the writer's own project and gives their own details (see Decision Tree step 1).
Recommendations count only when they serve the writer's own project; recommendations of things to
watch or consume for general interest or inspiration are `general_discussion`.

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

#### `reaction`

**Definition:** The writer responds, with feeling, to a specific thing that happened to them or that they witnessed, or to a stretch of their own experience that has already happened.

<details>
<summary><b>Full definition</b></summary>

A response to a specific thing that happened to the writer or that they witnessed (an event, result, milestone, change, or piece of news), whether it just happened or not. The writer's feelings about it are the point. A passing exclamation or parenthetical in an announcement or status update doesn't make a post a reaction; the feelings must carry at least a full sentence of the post. A question tacked on at the end ("has anyone else noticed this?") doesn't disqualify it.

It can also be a response to the writer's own accumulated experience (an ongoing struggle or a run of results over days, months, or years) when all four of these hold: it is the writer's own situation, not a claim about creators or the world; what's left after the feeling sentences are removed is a status report (events, numbers, history) with no advice, lesson, or standalone question; the only ask, if any, is for support or a "me too" ("have any of you felt this way?", "how did you keep going?"), not for an action, technique, tool, or fix; and the feelings respond to what has already happened, not to a worry about the future.

Habits, trends, and general opinions about creators or the world, with no personal event or record behind them, don't count. Lessons or retrospectives offered to others, and outreach or survey posts, don't count either, even when emotional. If the post still stands as a question about the world or a topic after the feeling sentences are removed, it's `general_discussion` instead.

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

**Example 3: borderline case (accumulated experience)**

> ### I'm starting to feel like being a full-time content creator might not be within reach.
>
> Hey everyone, I’ve been feeling a bit down lately and wanted to be honest with you all. I’m starting to feel like being a full-time content creator might not be within reach anymore. It’s tough to keep pushing sometimes, but I’d really love to hear your thoughts. Have any of you felt this way on your journey? How did you keep going or find motivation? Drop a comment and share your experiences, it would mean a lot to me!
>
> Additionally, my channel has 2191 sub 121,000 Watch hours and 1,643,856 views in the course of 5 years and honestly feel like I should just get a second job, since finance is getting tough.

#### `promotion_outreach`

**Definition:** The writer asks readers to look at, play, join, or team up on something of their own: a channel, video, game, product, cause, or content partnership.

<details>
<summary><b>Full definition</b></summary>

A post whose main ask is that readers do something with the writer's own thing: watch or
follow their channel or video, play or stream their game or demo, take part in their project
or cause, or team up with them (collab partners, content duos, friends to make content with).
This includes megathread replies that share the writer's own video, series, game, or demo, and
friend- or community-seeking posts where the writer wants readers to get in touch.

It is **not** this label when:

- the main ask is feedback or critique on the writer's own work (`help_request`), even when
  the post links the work;
- it recruits survey or study participants, or asks market-research questions as someone
  building a product (`general_discussion`);
- a link, plug, or sign-off ("check me out on YT") is passing, and the post stands on
  something else: feelings about an event or milestone (`reaction`), or a question, lesson,
  or opinion (`general_discussion`);
- it is a status update that mainly discusses the writer's recent project or asks what
  other posters are up to (`general_discussion`);
- it recommends or shouts out someone else's channel or game;
- it is a moderator's own megathread post; or
- the only evidence is flair (a "Collab" flair is not an ask).

**Plug test:** for a post with a link or a "check it out" line, delete the sentences that
point readers to the writer's thing. If what's left is feelings about what happened, it's
`reaction`; if what's left is a question, lesson, opinion, or discussion of the writer's
recent project, it's `general_discussion`; if what's left is mostly a list of the writer's own
videos, links, or offers, it's this label.

</details>

**Example 1:**

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

**Example 2:**

> ### reply from a weekly megathread
>
> Hi everyone!
>
> I'm looking for content creators to cover Animal Falling, my upcoming chaotic multiplayer party game, coming to Steam on August 27th.
>
> Imagine Ultimate Chicken Horse mixed with Fall Guys. Every round, players add new traps to the course before racing to the finish, making each round even more chaotic than the last.
>
> Up to 6 players online
>
> 4 players local co-op
>
> 4 Steam keys provided to every creator so you can play with friends or your community.
>
> Interested? You can request a key here:
>
> Keymailer: [(keymailer) url link]
>
> Steam: [(steam) url link]

#### `general_discussion`

**Definition:** The writer opens a conversation or asks the community an open question: opinions, recommendations, how or why something works, or a question backed by evidence they found.

<details>
<summary><b>Full definition</b></summary>

A post that opens a conversation or asks the community something, without being
centered on the writer's own project ask (`help_request`) or on the writer's own
experience, a specific event or an accumulated stretch of it, plus their feelings
about it (`reaction`).

This includes:

- asking for opinions, experiences, or recommendations for general interest, or
  starting a conversation about something that interests the writer;
- open questions about how something works, whether something is true or has changed,
  or why, with or without evidence the writer gathered (a date, a stat, a quote, a
  named comparison, a cited work);
- news or updates; and
- requests to recruit survey or study participants, and market-research questions
  from someone building a product, tool, or game.

Posts whose main ask is that readers watch, play, follow, join, or team up with the
writer are `promotion_outreach` instead. Feelings may be visible, but if they aren't
the point of the post, it stays here.

</details>

**Example 1:**

> ### Recommend me some Let's Play YouTubers that play Sci-Fi Action games or have played some before.
>
> **tag: 💻 Video/Channel Recommendations (Weekend Only)**
>
> I've been seeing horror game playthroughs a lot lately and, no shade to the 2 YouTubers whose videos I watch, I'm getting kinda sick of just seeing horror. I wanna see other genres like Sci-Fi Action or something. Y'all know anyone?

**Example 2:**

> ### Itch.io, is it safe?
>
> So typically when im searching the web for new games to play I always use steam since I know I can trust it not to have virus. But there are some good games that the big let's players are playing that are not on steam but are on itch.io .
>
> Does anyone have experience with viruses using this website for games, or can I trust downloading indi games from it?
>
> The game im looking to make a video on is dont seem with the fishes

**Example 3: discussion with evidence**

> ### Who was the first person to refer to their video as a Let's Play?
>
> **tag: 🗨️ Discussion**
>
> Most sources I can find claim that slowbeef was the first person to make a video in the format that we now use to describe a Let's Play, video footage of a game with player commentary, opinions, and reactions played over it. His video was uploaded on Jan 19, 2007. What I'm looking for is the first documented instance of someone calling their game a Let's Play. Wikipedia states that the term itself was coined on the SomethingAwful forums in 2007, although the exact origin is unclear.
>
> Through my own research I've found the video Let's Play La-Mulana 001: Surface by DeceasedCrab, uploaded on March 28, 2007. As far as I've found, this is the first instance of someone titling their video as a Let's Play. I may be wrong, but I can't find anything earlier than that. I'm curious what you all think, if anyone can find something earlier than that please share!

**Example 4: discussion with evidence**

> ### Why do I have two different AVD percentages for the same video?
>
> **tag: 🗨️ Discussion**
>
> The first image is my average view duration of a video that is 17:40 mins long. The second image is the average view duration on the summary page of the same video.
>
> Why does one page say average view duration of 7:15 mins (41.1%), while the other page of the same video says average view duration of 3:15 mins (18.5%)?
>
> Has YouTube not updated the stats for the video yet?

### Decision Tree

Judge by the ask (the literal one, or an implied one when no literal ask exists),
not the writer's motivation, the presence of evidence, or the feelings you'd expect
behind the post. Stop at the first yes.

1. **Is the ask, literal or implied, "what should I do, use, say, or choose" for the
   writer's own project, channel, or account?** → `help_request`
   - Use the literal question when there is one. If the answer is a fact
     about the world ("which help page is correct?"), it doesn't count even
     if the writer has a project reason for asking. A literal ask always wins
     over an implied one. A support ask or self-directed question ("Am I doing
     something wrong?") is not a literal ask (see "Non-soliciting questions"
     under edge cases).
   - **Implied ask:** when the post contains no literal ask (no question or
     request addressed to readers), it can still be a `help_request`. Count an
     implied ask only if all three hold:
     1. **Own obstacle:** the post reports a problem, failure, or blocker with
        the writer's own project, channel, account, or setup (not with the world
        or a platform in general).
     2. **Own details:** it gives concrete details of the writer's situation a
        reader could act on: what they use or did (setup, settings, steps they
        tried) or their numbers.
     3. **Reply test:** the most natural reply is something for the writer to do,
        try, change, or fix (a diagnosis, setting, tool, or next step), not
        agreement ("same here"), encouragement, or a fact or opinion about the world.

     Optional supporting signals: "I tried X and Y but it
     still…", "I'm pretty sure I did it right, but…", or a description of the
     result they expected against the one they got.

     It is **not** an implied ask when:
     - the post is feelings or a complaint with no details of the writer's own;
     - it only wishes for support or a "me too", or its only questions are
       support asks or self-directed questions (see "Non-soliciting questions"
       under edge cases);
     - it reports a result with nothing to act on (a milestone, a stat); or
     - the writer says they aren't looking for advice ("just need to vent").

     If you can't fill in all three parts, there is no implied ask. Mark a label
     that rests on an implied ask `Medium` confidence unless all three parts are
     clearly met.

   - A general preference poll doesn't trigger it either, UNLESS the post frames it
     as the writer's own decision ("what should I do?"). To be framed as writer's decision,
     post must state writer's current approach and a problem with it (e.g. "I upload at noon
     and views are low, what works for you?"). A poll with no stated problem or own-channel context
     ("what do you all prefer?") stays `general_discussion`.

   - A request to recruit a collaborator, partner, or tester for the writer's project
     (rather than asking for advice, suggestions, or direction) doesn't trigger this
     step. It falls through to step 3 (`promotion_outreach`), as does a post whose main
     ask is that readers watch, play, follow, or join something of the writer's. A
     request to take part in a survey or study, or a market-research question from
     someone building a product, falls through to `general_discussion` instead. If the
     post's main ask is that readers take part (play, stream, join, test) and any
     feedback is part of that exchange, it's still outreach. If the main ask is feedback
     or critique on the writer's own work, it's `help_request`.

   **Edge cases to consider**:
   - A question about how to categorize or frame the writer's own content (does this game fit my series, should this go in a playlist) counts as a decision about their own channel, even if stakes are low or says they'll proceed either way. It is `general_discussion` only if the ask is about the topic in general with no tie to the writer's own content.
   - **Non-soliciting questions.** A question makes the post a `help_request`
     only if it solicits something from readers other than agreement: advice,
     suggestions, tips, steps, or an answer about what to do, use, or choose.
     Two kinds of question don't:
     - **Support asks**, addressed to readers, that want solidarity or shared
       experience ("have any of you felt this way?", "how did you keep going or
       find motivation?", "has anyone had similar experiences and how did they
       move forward?").
     - **Self-directed questions** about the writer's own situation or feelings
       ("Am I doing something wrong?", "What has changed?", "Am I going mad?",
       "Do I suck?").

     Either kind counts like a me-too and doesn't trigger this step on its own.
     It becomes a `help_request` only if the post also contains a solicitation
     ("any advice?", "what should I do?", "how do I fix this?", "is there a
     trick?"). The amount of detail the writer gives doesn't change the label; it
     only affects confidence. Flair (e.g. "Advice") is not evidence of an ask.

NOTE: **DO NOT** run the strip test until this step has said no.

2. **Is the post centered on the writer's own experience that has already
   happened, plus their feelings about it?** → `reaction`. That experience is
   either (a) a specific thing that happened (an event, result, milestone, or
   change), or (b) an accumulated stretch of experience (an ongoing struggle or a
   run of results over days, months, or years).

   For (b), all four must hold:
   1. **Personal:** it's the writer's own situation, not a claim about creators
      or the world.
   2. **Strip test:** what's left without the feelings is a status report
      (events, numbers, history), with no advice, lesson, or standalone question
      about a topic.
   3. **Ask:** none, or only a support or "me too" ask. Any ask for an action,
      technique, tool, or fix was already caught at step 1.
   4. **Past-facing:** the feelings respond to what has happened, not to a worry
      about the future ("I'm afraid I'll be boring" is not this).

   Not this label, even if emotional: lessons or retrospectives offered to
   others, general opinions about creators or trends, and outreach or survey
   posts.

   Run the **Strip test**: delete the feeling sentences/words and read what's left.
   - If what's left is a bare event or data, or a question that only asks others to
     confirm they had the same experience ("has this happened to anyone else?",
     "did anyone else notice?"), it's this label.
   - If what's left is a standalone question about the world or a topic (how
     something works, whether something is true, why) or any other conversation
     starter, it's `general_discussion`, even if the feelings were strong.

3. **Is the main ask that readers watch, play, follow, join, or team up with the writer?**
   (their channel, video, series, game, demo, product, cause, or a collab or content
   partnership) → `promotion_outreach`
   - Includes friend- or community-seeking posts where the writer wants readers to get
     in touch, and megathread replies that share the writer's own video, series, game,
     or demo.
   - Run the **Plug test** (see the label definition) on any post with a link or a
     "check it out" line. A passing plug in a post that is really about feelings,
     a question, or a lesson doesn't count, because steps 1 and 2 already caught
     feelings-centered and ask-centered posts and the rest is a plug or sign-off.
   - **Update-thread replies**: a reply that mainly discusses the writer's recent project,
     or asks what other posters are up to, is `general_discussion`, even if it mentions a
     video. A reply that mainly lists or links the writer's own videos, series, or offers,
     with little discussion, is this label (`Medium`).
   - Not this label: feedback requests (step 1), survey or study recruitment and
     market research, shout-outs for someone else's channel, moderator megathread
     posts, and anything where the only evidence is flair.

4. **None of the above** → `general_discussion`

### The hardest boundary

**Which two labels:** `reaction` vs `general_discussion`

**The decision rule I used every time:**

First confirm the post isn't a `help_request`. Then ask whether the post is
about something that already happened to the writer, either a specific event or
a stretch of their own experience, and delete the sentences that express the
writer's feelings and read what's left.

- If the post is about a specific event, result, milestone, or change that
  happened to the writer, their feelings about it are the point, and what's left
  without the feelings is a bare event or a "me too" question, label it
  `reaction`. A question at the end doesn't change this.
- If there's no single event but the post describes the writer's own accumulated
  experience (days, months, or years), the feelings are the point, what's left is
  a status report, and the only ask is for support or a "me too" ("how did you
  keep going?"), label it `reaction`. A lesson, tip list, or retrospective
  offered to others is `general_discussion` even though it is personal.
- If the post is a habit, trend, preference, or general opinion with no personal
  event or record behind it, or what's left is a standalone question about the
  world or a topic, label it `general_discussion`, even if the tone is emotional.
- **Resolved vs. still processing.**
  - If the post presents a resolution to readers (what was done or learned) stated
    as advice or reassurance addressed outward ("you/we", "just remember", a TLDR),
    it's `general_discussion`, even when the event and feelings are personal. A one-line
    sign-off to readers doesn't count; the outward advice or reassurance has to carry
    the post, not just close it.
  - If the writer is still working through it (unresolved, uncertain, venting, hoping),
    or is sharing good news with nothing addressed to readers, it's `reaction`.
    A guess or a hope ("I guess we should just keep trying") is not a resolution.

### Other boundaries to keep in mind

**Which two labels:** `help_request` vs `general_discussion`

**The decision rule I used every time:**

Read the literal question (or, if there isn't one, the implied ask from step 1
of the Decision Tree) and ask what a good reply would be.

- If it's an action, choice, or piece of feedback for the writer's own project
  or channel ("should I dispute it?", "which style should I commit to?",
  "is my intro too long?"): it's `help_request`.
- If it's an opinion, recommendation, or fact about the world or a topic
  ("which help page is correct?", "what are your favorite horror games?"): it's
  `general_discussion`, even when the writer has a project reason for asking.

**Which labels:** `promotion_outreach` vs `general_discussion` vs `reaction`

**The decision rule I used every time:**

Ask what the writer wants readers to do. Then delete the plug (links, "check it out",
"DM me") and see what is left.

- If the main ask is that readers watch, play, follow, join, or team up with the writer,
  it's `promotion_outreach`, even when the post is friendly or emotional.
- If the post is mainly feelings about an event or milestone and the link is incidental, it's
  `reaction`. If it is mainly a question, lesson, or opinion with a passing plug or
  sign-off, it's `general_discussion`.
- Update Monday replies sit on this boundary. A reply whose feelings carry full sentences
  is `reaction`. A reply that mainly discusses the recent project or asks what others are
  up to is `general_discussion`. A reply that mainly lists or links the writer's own
  videos, series, or offers, with little discussion, is `promotion_outreach` (`Medium`).

### Annotator checklist

Do these in order for every post, before judging tone.

1. **Write down the literal ask.** Quote the sentence that is actually asking for something. A "just wanted to vent" line or a title can be a decoy; the real ask can be buried mid-post. If there is no literal ask, write down the implied ask instead: the writer's own obstacle, their own details, and the natural reply (Decision Tree step 1). If you can't fill in all three, there is no implied ask.
2. **Write down what the question is about.** Is it about the writer's own project, a question about the world or a topic, or only a request for others to confirm they had the same experience?
3. **Write down whether a specific event happened** to or around the writer, or whether the post describes a stretch of the writer's own experience that has already happened (not a worry about the future). Then check whether the post is lessons or opinions offered to others instead.
4. **Own-content test:** Would a plain yes or no reply tell the writer something to do with their own content (a series, a playlist, an upload)? If so, it's `help_request`, even when the stakes are low, unless the answer is a fact about the world (a rule, policy, or how a platform works).
5. **Wanting a channel isn't a project ask.** asking about setting up or revive a channel but doesn't state a problem or share any setup details (a plan, equipment, a current approach) is not `help_request`. Question(s) about how the platform works or general good ideas stays `general_discussion`. You need a stated problem or concrete details to act on ("my channel has been dead for six months, should I restart it?").
6. **Outreach check:** Does the post want readers to watch, play, follow, join, or team up with the writer? Delete the plug and see what's left (Plug test). Feedback requests on the writer's own work stay `help_request`, and survey or market-research recruitment stays `general_discussion`.
7. **Run the Decision Tree in order**, and stop at the first yes. Run step 1 before the strip test, every time.
8. **Empathy flag:** If you notice yourself thinking "I'd feel that too," that's a cue to slow down and run the strip test, not a reason to label `reaction`.
9. **Mark low-confidence labels** where two steps both felt right. Those posts are the ones that tell you a definition needs tightening.

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

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

     My community is the subreddit r/letsplay, which is dedicated towards people who
     watch or create video game guides & playthroughs on youtube and via livestreams.
     This includes people who are indie game developers looking for people to make videos
     on their new game for promotion, & people looking for collab partners for videos.

     My classifier sorts posts into 4 different labels: help_request, reaction, promotion_outreach,
     & general_discussion. Help request is for posts asking for advice or help with their project or
     channel related to video games/yt channel/livestreams; reaction are posts where users react to
     milestones or immediate events relating to their letsplay journey(consumer or creator);
     promotion_outreach for posts promoting a videogame, tool, channel, or other video game related
     project that the user is building, as well as outreach requests for collaboration or feedback
     into their project (requests for collab videos or asking for feedback on games)

---

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
and boundaries I had via claude's assistance). Then did the long process of collecting posts in batches,
making adjustments to the spec and such as edge cases popped up. Then eventually I stoned around 260-270 posts

**Counts per label:**

### Label Distribution

| Label                |    Rows | Proportion |
| -------------------- | ------: | ---------: |
| `help_request`       |      89 |      31.0% |
| `general_discussion` |      79 |      27.5% |
| `promotion_outreach` |      63 |      22.0% |
| `reaction`           |      56 |      19.5% |
| **Total**            | **287** | **100.0%** |

**Three hard cases**

**1.**

> _The post:_ "Streamers with editors: how do you hand off clips? (not selling, just asking)"
> The writer, "a small dev building something for streamer teams," asks readers how moments get
> from the stream to the editor, what breaks, and whether "a shared board where mods mark moments
> live" would help. They add that "honest 'my setup is fine' answers are just as useful."
>
> _Could have been:_ help_request or general_discussion. It is a list of questions from someone
> with a project (a tool they are building), so it reads like asking readers for input on their
> own work.
>
> _I chose, because:_ general_discussion. The questions are about how streamers work, not about
> what the writer should do next, and my spec sends survey and market-research questions from a
> builder to general_discussion. "Not selling, just asking" also rules out promotion_outreach.

**2.**

> _The post:_ "Sometimes you have to love the haters!" The writer describes comments telling
> them to rename their channel or "do face cams or vtuber stuff," says they replied "Hey thanks
> for watching my videos," and ends with "Just remember to always be calm in the face of
> rudeness and mean people as that is way more powerful than anything else."
>
> _Could have been:_ reaction or general_discussion. The post is built on a personal event with
> feelings in it (the comments, the laughing, "does not bother me").
>
> _I chose, because:_ general_discussion. The event is told to teach a lesson, and the closing
> line is advice to readers. My spec says lessons offered to others don't count as a reaction,
> even when emotional, so the post is a retrospective with a takeaway.

**3.**

> _The post:_ "Chill Background music for free" The writer asks where to find royalty-free
> background music, whether you "can trust that the royalty free youtube stuff is not stolen from
> somebody else," and says they like the style of one artist.
>
> _Could have been:_ help_request or promotion_outreach. The title reads like an offer of free
> music, and my other music posts ("feel free to use in your gaming videos") are
> promotion_outreach.
>
> _I chose, because:_ help_request. The body asks readers for pointers to music for the writer's
> own video, and nothing in it offers or promotes anything. In my spec, the ask in the body
> decides the label, and the title does not.

---

## The Training Run

**Base model:** DistilBERT (distilbert-base-uncased)

**Settings:** epochs: 6, learning rate:3e-5, batch size: 8, max_length: 384, seed: 42

**Anything I changed from the defaults, and why:** Changed learning rate, epochs, & max_length (token size) because
the default settings would not be sufficient due to the token size of the posts being way larger than 128,
and it would either overfit or under train against the dataset. Chose these metrics via claude.

**Split sizes:** stratified 70/15/15 on 287 posts: train 200, val 43, test 44

| Split | help_request | general_discussion | reaction | promotion_outreach |
| ----- | ------------ | ------------------ | -------- | ------------------ |
| train | 62           | 55                 | 39       | 44                 |
| val   | 13           | 12                 | 9        | 9                  |
| test  | 14           | 12                 | 8        | 10                 |

NOTE: promotion_outreach originally had only 7 posts in the test split for original submission:
I added more later for resubmission & unit 6 to reflect r/letsplay better & not have any thin labels

---

## How I Used AI

<!-- Two specific moments — what you asked, what came back, what you changed.

     ⚠️ Plus disclosure of any pre-labelling. If you had a model pre-label a
     batch and then read and corrected every one, say that. It's an allowed
     workflow and disclosing it costs you nothing. Not disclosing it is the
     problem. -->

**Moment 1**

- _What I asked for:_ Help with making the spec sheet for label definitions and make adjustments when we found edge cases
  or wanted to adjust the labels
- _What came back:_ label_spec.md, which contains the content I used to fill out the label taxonomy section above
- _What I changed:_ made slight adjustments in terms of presentation to make it more readable for myself

**Moment 2**

- _What I asked for:_ Help with making the spreadsheet used for the labels.csv dataset, using AI pre-labeling for most posts
  to automate that aspect, while still using 20 cold rows that I had examined and never asked claude to cross examine
- _What came back:_ labels.csv spreadhsheet with 5 columns: text, label, confidence, note, has_media
- _What I changed:_ changed a couple of labels based on my own interpretation & catching where the AI was wrong or missing insight

**Pre-labelling disclosure:**
Used Claude to pre label most posts, with a couple I made a guess before letting claude create their assessment.
Did it for automation purposes, while making sure to keep in mind balance & other factors via batch sends and evaluation

# Stretch Feature: 4th label

**Original 3 labels**: help_request, reaction, general_discussion
**New 4th label**: promotion_outreach
**why I added the new label**: Added it because I noticed there were alot of posts that
were specifically geared towards promoting a project and/or doing outreach for collaboration/feedback.
So I created a new label that encompasses these types of posts.

<!-- ═══════════════════════ UNIT 6 — THE TEST ═══════════════════════

     Don't fill these in during unit 5.
     ═══════════════════════════════════════════════════════════════════ -->

---

## Baseline vs. Trained

<!-- Both models on the same posts. `python baseline.py --trained results.json`
     prints this table for you. -->

| Measure                   | Baseline | Trained | Difference |
| ------------------------- | -------- | ------- | ---------- |
| Overall accuracy          | 0.477    | 0.659   | +0.182     |
| Macro F1                  | 0.482    | 0.659   | +0.177     |
| F1 — `general_discussion` | 0.400    | 0.609   | +0.209     |
| F1 — `help_request`       | 0.476    | 0.667   | +0.190     |
| F1 — `promotion_outreach` | 0.533    | 0.737   | +0.204     |
| F1 — `reaction`           | 0.519    | 0.625   | +0.106     |

**What I predicted before I looked:**

<!-- Milestone 1 asks you to write this BEFORE seeing the trained numbers. A
     prediction made afterwards isn't one. -->

     I predicted that the model would do better on every label except help_request, where I thought
     the baseline.py would probably do better to detect based on the one line definition. I do think
     it may be worth a look to compare one line defintions versus the full line definition, and then
     see if there's a way to incorporate my decision tree into the baseline.py for comparison.

**What the gap actually means:**

<!-- If the baseline matched your trained model, your fine-tuning added
     nothing — and that is a real finding, not a failure. Say it plainly. -->

     Fine-tuning DID add something to the model! The difference was between 10%-20% improvement
     per-label vs the baseline. If I have time, I will test with the full definitions & maybe
     incorporate the decision tree itself: I predict with the full definition, the margin will shrink
     and may even do better on at least one label vs fine tuning the model.

---

## Run Log — Before

<!-- Five criteria across three seeds. The notebook's section 6 prints the
     spread table; the Target and Verdict columns are yours. -->

| Measure                   | Seed 42 | Seed 7 | Seed 2024 | Spread |
| ------------------------- | ------- | ------ | --------- | ------ |
| Overall accuracy          | 0.659   | 0.727  | 0.705     | 0.068  |
| Macro F1                  | 0.659   | 0.716  | 0.717     | 0.058  |
| F1 — `help_request`       | 0.667   | 0.769  | 0.643     | 0.126  |
| F1 — `reaction`           | 0.625   | 0.700  | 0.800     | 0.175  |
| F1 — `promotion_outreach` | 0.737   | 0.870  | 0.818     | 0.133  |
| F1 — `general_discussion` | 0.609   | 0.526  | 0.609     | 0.082  |

| Criterion                                                              | Target                                                                      | Seed 42                                                 | Seed 7                                                  | Seed 2024                                               | Verdict                                                                           |
| ---------------------------------------------------------------------- | --------------------------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- | --------------------------------------------------------------------------------- |
| 1. Model's overall accuracy 75%                                        | ≥ 0.75 accuracy on all three seeds                                          | 0.659 ✗                                                 | 0.727 ✗                                                 | 0.705 ✗                                                 | **Miss** (best seed is 2.3 points short)                                          |
| 2. Minimum counts per label, with looser floors for the smaller labels | ≥ 200 posts; help ≥ 50, promo ≥ 40, react ≥ 25, discussion ≥ 30; none > 70% | 89 / 63 / 56 / 79 ✓                                     | 89 / 63 / 56 / 79 ✓                                     | 89 / 63 / 56 / 79 ✓                                     | **Pass** (287 posts, largest label 31%, promo 22%)                                |
| 3. Per label performance is looser for thinner labels                  | F1 ≥ .70 for help/discussion, ≥ .60 for react/promote                       | help .667 ✗ · disc .609 ✗ · promo .737 ✓ · react .625 ✓ | help .769 ✓ · disc .526 ✗ · promo .870 ✓ · react .700 ✓ | help .643 ✗ · disc .609 ✗ · promo .818 ✓ · react .800 ✓ | **Miss** (discussion fails all 3 seeds, help fails 2; promo and react pass all 3) |
| 4. Labels need to be very consistent                                   | Spread ≤ 0.05 (95% consistent) for every label except general_discussion    | — (judged by spread)                                    | — (judged by spread)                                    | — (judged by spread)                                    | **Miss** (spreads: help .126, react .175, promo .133)                             |
| 5. Confidence means better results                                     | Most-sure third ≥ 5 points above least-sure third                           | .929 vs .429 (+50.0) ✓                                  | .857 vs .429 (+42.9) ✓                                  | .857 vs .643 (+21.4) ✓                                  | **Pass**                                                                          |

### Confusion matrix

<!-- ⚠️ TYPED AS A MARKDOWN TABLE. The notebook prints one ready to paste.
     An image of a matrix earns nothing. -->

--------------- SEED #42 Confusion Matrix -----------------------------------
| true \ predicted | help_request | reaction | promotion_outreach | general_discussion |
|---|---|---|---|---|
| **help_request** | 10 | 2 | 1 | 1 |
| **reaction** | 0 | 5 | 1 | 2 |
| **promotion_outreach** | 2 | 0 | 7 | 1 |
| **general_discussion** | 4 | 1 | 0 | 7 |

--------------- SEED #7 Confusion Matrix -----------------------------------
| true \ predicted | help_request | reaction | promotion_outreach | general_discussion |
|---|---|---|---|---|
| **help_request** | 10 | 1 | 1 | 2 |
| **reaction** | 0 | 7 | 1 | 0 |
| **promotion_outreach** | 0 | 0 | 10 | 0 |
| **general_discussion** | 2 | 4 | 1 | 5 |

--------------- SEED #2024 Confusion Matrix -----------------------------------
| true \ predicted | help_request | reaction | promotion_outreach | general_discussion |
|---|---|---|---|---|
| **help_request** | 9 | 0 | 1 | 4 |
| **reaction** | 2 | 6 | 0 | 0 |
| **promotion_outreach** | 1 | 0 | 9 | 0 |
| **general_discussion** | 2 | 1 | 2 | 7 |

**My biggest off-diagonal number, and what it means:**
Across the all 3 seeds, I determine the biggest off-diagonal number is the boundary between help_request &
general_discussion. As for what it means: one seed it was lopsided, while the other it was considered relatively symmetric
the last seed had a lopsided boundary between general discussion & reaction. To me, that indicates that the model is struggling
to identify general discussion posts, and that sort of makes sense since I've noticed many of my hard cases were involving general discussion, and general discussion is meant to sort of be a fallback label for any post that isn't trying to ask for help, process feelings, or reach out to people for collaboration or mutual cooperation. For me, and from what claude said to me
it seems the most appropriate would be to add more posts to general discussion that targets help request boundary & maybe reaction too: this is backed by the fact general discussion consistently got the worst f1 score.

<!-- Not "the model made mistakes" — WHICH boundary it didn't learn, and which
     direction. "7 real analysis posts were called hot_take and only 3 went the
     other way" is a direction, not just an error rate. -->

---

## Verdicts and Diagnoses

<!-- MET or MISSED against LAST UNIT's target. The target has to hold across
     all three seeds, not turn up sometimes. -->

| #   | Criterion                                                           | Target                                                                      | Verdict  | How I decided                                                                                                                     |
| --- | ------------------------------------------------------------------- | --------------------------------------------------------------------------- | -------- | --------------------------------------------------------------------------------------------------------------------------------- |
| 1   | Model's overall accuracy 75%                                        | ≥ 0.75 accuracy on all three seeds                                          | **Miss** | used claude to evaluate on the criterion specifics                                                                                |
| 2   | Minimum counts per label, with looser floors for the smaller labels | ≥ 200 posts; help ≥ 50, promo ≥ 40, react ≥ 25, discussion ≥ 30; none > 70% | **Pass** | used claude to evaluate on the criterion specifics                                                                                |
| 3   | Per label performance is looser for thinner labels                  | F1 ≥ .70 for help/discussion, ≥ .60 for react/promote                       | **Miss** | used claude to evaluate on the criterion specifics                                                                                |
| 4   | Labels need to be very consistent                                   | Spread ≤ 0.05 (95% consistent) for every label except general_discussion    | **Miss** | used claude to evaluate on the criterion specifics; used spread to determine consistency with spread needing to be ≤ 0.05 to pass |
| 5   | Confidence means better results                                     | Most-sure third ≥ 5 points above least-sure third                           | **Pass** | used claude to evaluate on the criterion specifics                                                                                |

**Diagnoses**

**Criterion #1:** I believe I missed narrowly because of the general discussion boundary issue.
That's a problem with the dataset, so that improvement should hopefully raise my accuracy enough to
raise it to 75% every time. However, I do realize that the overall accuracy isn't aligned with the per
label performance (.7 for help_request/general_discussion; .6 reaction/promotion_outreach). To make
things somewhat more aligned with criterion#3, I'm dropping it to .70 overall accuracy.
Still slighly higher than minimum per label accuracy combined, but that's fine.

**Criterion #3:** I missed this because I assumed that the labels with more examples would have better accuracy;
which is probably the safe assumption if the model had no issues with label boundaries. Since there were issues
with distinguishing boundaries, and general discussion particularly having boundary confusion, It's mostly an issue with
the model and dataset. I'll see if adding the general discussion posts fixes this.

**Criterion #4:** Missed this again due to model having trouble with identifying general_discussion correctly over
help_request (and reaction for one seed). However, it also didn't help that I didn't specify how to determine
consistency in the original, but I was lucky that the notebook had a metric baked in. I'll still rewrite the
criterion to make that explicit, but the target of <= 5% spread will only need to be reached across all labels
for one seed instead of 3 seeds.

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

**Agreement rate:** **28 / 30 = 93**%

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

> _The post:_ Carbon plates aren't the whole story. My times dropped 2% in the shoes and another 2% the following year in the same pair, when the only thing that changed was going from 35 to 50 miles a week.
>
> _Staff said / I said:_ Staff said it was analysis, I said it was hot_take
>
> _My call, and why:_ I couldn't pick up the argument being stated because it wasn't directly & clearly stated at least to me.
>
> _Which pile:_ it's pile b: Post doesn't explictly state the argument it's trying to back, so how can I know what the poster is arguing? It indicates a gap in the definitions, and it should account for arguments that aren't clearly stated.

**2.**

> _The post:_ Three of us ran the same session on the same day, different shoes, within 10 seconds of each other over 5 miles. I'm not saying shoes do nothing, but whatever they do was smaller than the noise between three people.
>
> _Staff said / I said:_ staff was analysis, I was hot_take
>
> _My call, and why:_ I felt the analysis by the poster fell short because they didn't do an A/B test ie they didn't actually test the different shoes vs using the same shoe, so I felt in that case the fact wasn't load bearing therefore it's hot_take
>
> _Which pile:_ it's pile c : the ruling is ambiguous because it doesn't state guidelines on how exactly to determine if a fact
> is load bearing. I argue it doesn't pass that test because of the lack of a control test, therefore user can't back their argument.

**What the pattern in my disagreements tells me:**
That I am very analytical but also direct: I need arguments to be made explicit & I won't accept
a post backed by evidence if argument needs an control/test experiment to back a claim, or needs a specific
type of experiment appropriate for the argument in order to establish a 1-1 relationship rather than
an interaction from an unknown 3rd variable.

---

## The Improvement

**What I changed:** I added 34 posts to `general_discussion` that targeted its weakest
boundary points (question-shaped posts, opinions/retrospectives, and platform news with
no ask). That did not help on its own, so I then trimmed 7 low-confidence, question-shaped
`general_discussion` posts and relabeled 1 more to `help_request`, taking the dataset
from 287 to 301 rows (general_discussion 92, help_request 90, promotion_outreach 63,
reaction 56). The stratified split reshuffles whenever rows change, so the before and
after runs are scored on different test posts (n=44 before, n=46 after).

**Which diagnosis pointed at it:**
`general_discussion` had the worst F1 of any label on all three seeds in the "before" run
(.609, .526, .609), and the confusion matrix showed its main errors were with
`help_request` in both directions (8 GD→HR vs 7 HR→GD, pooled over the three seeds).
That is a boundary the model hadn't learned, not one label being rare.

### Run Log — After

| Criterion                                                  | Target                                                           | Seed 42                                                       | Seed 7                                | Seed 2024                             | Verdict                                                                   |
| ---------------------------------------------------------- | ---------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------- | ------------------------------------- | ------------------------------------------------------------------------- |
| 1. Overall accuracy                                        | ≥ 0.75 on every seed                                             | 0.630                                                         | 0.739                                 | 0.761                                 | **Miss** (2 of 3 seeds under 0.75)                                        |
| 2. Minimum counts per label                                | HR ≥ 50, PO ≥ 40, RE ≥ 25, GD ≥ 30; corpus ≥ 200; no label > 70% | 301 rows: HR 90 · PO 63 · RE 56 · GD 92 (largest label 30.6%) | same file                             | same file                             | **Pass**                                                                  |
| 3. Per-label F1                                            | HR ≥ .70, GD ≥ .70, PO ≥ .60, RE ≥ .60                           | HR .645 · GD .643 · PO .556 · RE .667                         | HR .750 · GD .667 · PO .842 · RE .706 | HR .815 · GD .667 · PO .800 · RE .750 | **Miss** (GD under .70 on all 3 seeds; HR and PO under target on seed 42) |
| 4. Consistency (non-GD labels, spread ≤ .05 across seeds)  | spread ≤ .05                                                     | HR spread .170 · RE .083 · PO .287                            |                                       |                                       | **Miss**                                                                  |
| 5. Confidence (most-sure third ≥ least-sure third + 5 pts) | ≥ +5 pts                                                         | 0.867 vs 0.400 (+46.7)                                        | 0.933 vs 0.533 (+40.0)                | 1.000 vs 0.467 (+53.3)                | **Pass**                                                                  |

Criterion 3 was written as pooled cross-validation with bootstrap intervals; I only ran
the three-seed holdout, so these are holdout F1s, not that. Criterion 4 was ill-defined
as written, so I used the per-label F1 spread across the three seeds as the measure.

Accuracy spread across seeds was 0.131, over the 10-point line, so this dataset is too
small for a stable measure (about 46 test posts, so one post is worth about 2 points).

**Confusion matrices (rows are true labels, columns are predictions):**

Seed 42

| true \ predicted       | help_request | reaction | promotion_outreach | general_discussion |
| ---------------------- | ------------ | -------- | ------------------ | ------------------ |
| **help_request**       | 10           | 1        | 2                  | 1                  |
| **reaction**           | 2            | 5        | 0                  | 1                  |
| **promotion_outreach** | 2            | 0        | 5                  | 3                  |
| **general_discussion** | 3            | 1        | 1                  | 9                  |

Seed 7

| true \ predicted       | help_request | reaction | promotion_outreach | general_discussion |
| ---------------------- | ------------ | -------- | ------------------ | ------------------ |
| **help_request**       | 12           | 1        | 0                  | 1                  |
| **reaction**           | 1            | 6        | 0                  | 1                  |
| **promotion_outreach** | 2            | 0        | 8                  | 0                  |
| **general_discussion** | 3            | 2        | 1                  | 8                  |

Seed 2024

| true \ predicted       | help_request | reaction | promotion_outreach | general_discussion |
| ---------------------- | ------------ | -------- | ------------------ | ------------------ |
| **help_request**       | 11           | 1        | 0                  | 2                  |
| **reaction**           | 1            | 6        | 1                  | 0                  |
| **promotion_outreach** | 0            | 0        | 10                 | 0                  |
| **general_discussion** | 1            | 1        | 4                  | 8                  |

All three seeds pooled (138 test posts)

| true \ predicted       | help_request | reaction | promotion_outreach | general_discussion |
| ---------------------- | ------------ | -------- | ------------------ | ------------------ |
| **help_request**       | 33           | 3        | 2                  | 4                  |
| **reaction**           | 4            | 17       | 1                  | 2                  |
| **promotion_outreach** | 4            | 0        | 23                 | 3                  |
| **general_discussion** | 7            | 4        | 6                  | 25                 |

Biggest pooled confusion: 7 real `general_discussion` posts called `help_request` (4 went
the other way). The next largest is 6 real `general_discussion` posts called
`promotion_outreach`, 4 of them on seed 2024.

**Did it help, and how do I know:**
Only partly, and the first attempt did not help at all. Adding 34 posts left
`general_discussion` F1 unchanged on average (.581 before, .582 after) and made accuracy
less stable (spread .068 to .128). After the trim, `general_discussion` F1 averaged .659
(.643, .667, .667) and was the most stable label across seeds (spread .024, against .083
before). The GD↔HR boundary improved on the pooled counts: GD→HR went from 8 of 36 test
posts to 7 of 42, and HR→GD from 7 to 4. Mean accuracy moved only .697 to .710, well
inside the .131 spread, so I can't claim the model got better overall, and no criterion
changed its verdict. Two caveats: the test set changed with each run, and removing the
hardest question-shaped posts from the file also removed them from the test set, so part
of the gain is an easier test. Also, `promotion_outreach` fell from .812 to .742 pooled,
and GD→PO errors rose from 3 to 6; so the boundary moved rather than disappeared.

---

## What's Still Broken

**Criterion 1 (accuracy ≥ 0.75):** Mean accuracy is .710 and the best seed is .761. With
about 46 test posts, 0.75 allows at most 11 errors, and the model still makes 12 to 17.
I'd write a spec clause for consensus questions ("what do you do when X?") and collect
more `promotion_outreach` and `general_discussion` posts that look like each other. I
stopped because searches for opinion and platform-news posts on r/letsplay ran out.

**Criterion 3 (per-label F1):** `general_discussion` stays at about .66 against a .70
target, and the weak spots are the GD↔HR and GD↔PO boundaries. The `promotion_outreach`
misses on seed 42 are "looking for friends or collab" posts that read like conversation.
I'd add more of that post type and tighten the rule for outreach. I stopped because this
is already a modest change that the test split can't measure reliably.

**Criterion 4 (consistency):** The spreads (.083 to .287) can't get under .05 at this
size, because `reaction` has 8 test posts and `promotion_outreach` has 10, so a single
post moves their F1 by 8 to 12 points. I'd need a much larger test set, not a better
model, and I haven't edited the criterion.

**The gap between what I meant my labels to capture and what the model
learned:**
I defined `general_discussion` as the last step of the decision tree: anything whose main
ask is not help, a feeling or outreach. The model instead learned surface shape, so
question-shaped discussion posts get called `help_request` (7 GD→HR vs 4 HR→GD pooled)
and discussion posts that mention channels or subreddits get called
`promotion_outreach` (6 pooled).

Overall, I think I was over extending myself by over specifying my labels
for what I was working on, & next time I will make things somewhat more simpler.
This was in part due to my over reliance on claude to guide me when I should've
spoken to TF's for advice, and I didn't due to unexpected life stressors at home,
and I tend to not reach out and stay secluded under such circumstances.

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

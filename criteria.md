# Acceptance criteria — TakeMeter

Five criteria that say what "working" means for this classifier, written in
unit 5 **before** anything was trained.

**All five are yours this time.** None are given. You've had two projects of
practice.

An acceptance criterion names a number. _"The model is accurate"_ is an
opinion. _"Every label has an F1 of at least 0.60 on the held-out set"_ is a
criterion.

Under each, write a sentence or two on **why that number**. A reason that says
something about your data or your taxonomy earns credit — _"I picked 0.60 F1
for `reaction` because it's my smallest label and I only have about 50
examples of it"_. A reason that could be attached to any project does not.

> Missing your own targets next unit costs you nothing. Setting a target so
> easy you can't miss it does.

---

## Pick numbers you can defend

Not numbers that sound impressive. Three labels means a coin-flip guesser gets
about 33%, so a target of 0.40 is barely a target. Your number should sit
somewhere you'd honestly call useful.

**Cover at least three of these five areas.** They're here as prompts, not as a
form to fill in — a criterion that fits none of them is fine if it names a
number.

| Area                  | A question it could answer                                            |
| --------------------- | --------------------------------------------------------------------- |
| Overall accuracy      | How often does it need to be right to be worth using?                 |
| Per-label performance | Is one label allowed to be much worse than the others?                |
| Balance               | How lopsided can your label counts get before it's a problem?         |
| Consistency           | If someone else labelled the same posts, how often should you agree?  |
| Confidence            | Should a confident prediction be right more often than an unsure one? |

Two things worth knowing before you pick numbers, because both will affect
whether you hit them:

- **Your smallest label will have the jumpiest score.** If a label has 50
  examples, about 8 land in the test split. An F1 computed on 8 examples moves
  a lot between seeds. A target for that label should be looser than one for
  your biggest label, and saying so is a good reason.
- **Unit 6 tests across three seeds, and the target has to hold across all
  three.** A target of 0.65 against results of 0.71, 0.62, 0.68 is a **miss**.
  Pick with that in mind — it is stricter than it first sounds.

---

## 1. Model's overall accuracy 75%

<!-- Your criterion. It must name a number. -->

The overall accuracy of the classifier should be at least be 75% for
it to be considered useful in classifying posts.

**Why this target:**
with 4 labels, using general discussion as a catch all for posts that don't cleanly fit the
other 3 labels, I figured it would be good to aim for a reasonable accuracy score of
about 3x what a coin flipper would get (25% x 3 = 75%)

---

## 2. Strict balance for all labels except general_discussion

At a minimum, there must be 50 posts for each of the non general_discussion labels.
For general discussion, it can have as little as 30 posts

**Why this target:**
Focuses balance on my main 3 labels, as general_discussion is a fall back label
for when a post doesn't neatly match the other 3. Since it's 200 posts total,
I want to ensure that each non fall back label reps at minimum 25% of total corpus.

---

## 3. Per label performance is looser for general_discussion

For every non-fall back label, I want to achieve a min of .7 F1 score, while allowing
general_discussion (our fall back label) is allowed for a min of .55 F1 score.

**Why this target:**
I want to specifically focus on getting the model working and being useful for
id'ing posts that aren't part of the fallback category. Since general discussion is
not much of a focus, I'm ok with general discussion having a worse f1 score.

---

## 4. Labels need to be very consistent

Labels other than general_discussion need to be very consistent,
go for a minimum of each label getting at least 95% across corpus.
if this isn't met.

**Why this target:**
I want to ensure my boundary cases and overall decision tree is solid,
which means very little variance between 2 different people if they
look at the corpus.

---

## 5. Confidence means better results

Classifier should be able to have a higher score when it's confident in its
answer than when not: the most-sure third must be at least 5% higher than the
least-sure third.

**Why this target:**
I want the model to be able to be useful, and part of that is making
sure it is able to back up its confidence guesses. I believe showing that
our model is able to back up the confidence

---

<!-- ─────────────────────────────────────────────────────────────────────────
     UNIT 6 — read this before you change anything above.

     If a criterion turns out to be BROKEN rather than merely unmet, you can
     revise it, and that earns credit. But never delete or edit the original
     line. Add the revision underneath, like this:

         ## 2. Every label performs acceptably

         The model performs well on all labels.

         **Why this target:** ...

         > **Revised in unit 6:** Every label has an F1 of at least 0.60 on
         > the held-out set.
         >
         > **Why revised:** "performs well" gave me nothing to check. I
         > couldn't produce a verdict from it at all.

     That's a revision because the criterion couldn't be MEASURED.

     Lowering a target because you missed it is not a revision, and it costs
     you the point:

         ✗ "Overall accuracy of at least 0.65" → "at least 0.55", because
            0.65 turned out to be optimistic for 200 examples.

     A number you missed stays where it is, gets diagnosed, and gets a fix
     attempted. That's where the points are.
     ───────────────────────────────────────────────────────────────────────── -->

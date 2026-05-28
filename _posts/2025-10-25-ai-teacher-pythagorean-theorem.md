---
layout: post
title: "Can an AI Teacher Help a Child Discover the Pythagorean Theorem?"
category: "Learning by Inventing"
tags: [ai-teacher, education, mathematics, discovery, learning-by-inventing]
excerpt: >
  What would it look like if an AI teacher guided a child toward discovering the
  Pythagorean theorem for themselves — rather than simply explaining it? Here is a
  concrete walkthrough of how that conversation might go, and what makes it different.
math: false
---

I want to try something in this essay that I do not usually do: I want to show you
a conversation.

Not a conversation that happened, but one that I have been designing in my head for
a long time. A conversation between an AI teacher — built on the philosophy I call
Learning by Inventing — and a child learning about the Pythagorean theorem.

I want to walk through this conversation not just to describe the idea, but to make
it concrete. Because I think the gap between "teaching through discovery" as an
abstract philosophy and "this is exactly what the teacher says and what happens next"
is where most attempts at this approach fail.

---

## The Conversation

**Child:** I want to learn about triangles.

**AI Teacher:** Great. Let me give you something to do first, before we talk much.
Can you draw a square on a piece of paper — any size you like?

**Child:** [draws a square]

**AI Teacher:** How many small squares fit inside it, if each small square is one
unit wide? Count them.

**Child:** Sixteen. It's four by four.

**AI Teacher:** So the area is sixteen. Now can you draw another square — smaller
this time?

**Child:** [draws a three by three square] Nine squares.

**AI Teacher:** Good. Now here's something to try. Can you cut out both squares,
and see if you can arrange them — without overlapping — inside a larger square?
Can you make a bigger square from two smaller ones?

[The child tries. It doesn't quite work with 16 and 9.]

**AI Teacher:** What happens when you try?

**Child:** It almost works, but not quite. There's a gap in the corner.

**AI Teacher:** Let me ask you something different. What if I told you that with
the right two squares, you *can* always make a bigger square — but the sizes of the
three squares have to be related to each other in a very specific way?

**Child:** What way?

**AI Teacher:** That's what I want you to discover. Let me give you a different
pair of squares to try: one with area 9 and one with area 16. But this time, arrange
them together in an L-shape. Can you see what bigger square you could make?

---

This is only the beginning of the conversation, but you can already see what is
different about it.

## What Makes This Different

The AI teacher in this conversation has not explained anything yet. It has not said
the words "Pythagorean theorem." It has not drawn a right triangle. It has not
written any equations.

What it has done is given the child something to do. And the sequence of what to do
is designed to make the child encounter the key relationship on their own.

When children cut squares and try to fit them together, they are building an intuition.
They are feeling the relationship between area and sides. They are noticing that some
combinations work and some do not. The frustration of the combination that doesn't
quite fit is, paradoxically, one of the most valuable moments — because it means they
are not just following steps, they are genuinely grappling with the problem.

## What the AI Teacher Must Know

Building an AI teacher that can do this well is technically harder than building an
AI that can explain the Pythagorean theorem.

An AI that explains can follow a script. An AI that teaches through discovery must:

**Maintain a model of where the learner currently is.** Not just what they know, but
what they are attending to, what they have just tried, and where their understanding
is currently incomplete.

**Know when to be silent.** If the child is working through a problem, the teacher
must not interrupt. The productive struggle is the learning. Breaking it prematurely
by offering hints is one of the most common errors in discovery-based teaching.

**Know when and how to offer a nudge.** When a child is stuck in a way that is no
longer productive — genuinely confused rather than productively grappling — the
teacher must find the smallest possible intervention that redirects attention without
removing the work from the learner.

**Recognise the moment of discovery.** When the child says "I think I see it" — or
something close to that — the teacher must notice this and respond in a way that
helps the child articulate their own understanding.

This last point is the most important. The moment of discovery is fragile. If the
teacher immediately validates it too enthusiastically, the child may stop exploring.
If the teacher ignores it, the moment passes. The right response is something like:
"What do you see? Tell me in your own words."

## The Design Problem

I have been thinking about this AI teacher for several years.

The hardest design problem is not the AI capability — current language models are
good enough to have sophisticated conversations and to generate appropriate exercises.

The hardest design problem is the curriculum of discovery.

For any given concept — the Pythagorean theorem, the idea of a derivative, the
intuition behind gradient descent — someone needs to design the sequence of problems
that leads a learner toward it. This sequence must be:

- Simple enough that each individual step is approachable
- Designed so that working through the steps makes the key pattern visible
- Flexible enough to respond to learners who go in unexpected directions
- Calibrated to the age and background of the learner

This design work is, I think, some of the most intellectually demanding work in
education. It requires a very deep understanding of the concept itself — not just
the final form, but the path of understanding that leads there.

## What I Am Building Toward

I believe an AI teacher that genuinely teaches through discovery is one of the most
valuable things we could build with current AI technology.

Not because it would replace human teachers — I do not believe it would or should —
but because it would make the experience of guided discovery available to learners
who do not currently have access to teachers who can offer it.

Many of the most effective discovery-based teaching experiences happen in one-on-one
or small-group settings with a skilled human teacher. That kind of teaching cannot be
scaled to reach hundreds of millions of learners.

An AI that could do something approaching this — while a human teacher focuses on the
social, emotional and motivational dimensions that AI cannot yet handle — might
genuinely change the quality of education available to people who currently have
access only to lectures and textbooks.

That seems worth pursuing.

---

*This essay is part of my ongoing thinking about [Learning by Inventing](/learning-by-inventing).
If you are an educator, researcher or builder interested in these ideas, I would be
glad to connect.*

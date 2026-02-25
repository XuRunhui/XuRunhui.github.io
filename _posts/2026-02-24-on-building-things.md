---
layout: post
title: "On Building Things That Last"
date: 2026-02-24 10:00:00 +0800
tags: [software, engineering, philosophy]
excerpt: >
  Most software doesn't need to be fast. It needs to be correct.
  Then maintainable. Fastness is, in most cases, a distant third.
---

There's a kind of software I find genuinely beautiful: programs that are small,
do one thing, and do it so well that nobody ever thinks about them again. The
Unix utilities are the canonical example. `cat`, `grep`, `wc`. They were written
in the 1970s and they'll still be running in the 2070s.

What made them last?

## Correctness Before Performance

The instinct to optimize early is seductive and almost always wrong. When you're
solving a problem you don't yet fully understand, you'll optimize the wrong things.
You'll make the wrong code fast. Then the requirements will change and you'll have
to throw it all away anyway — but now the cleanup is harder because the optimization
has tangled itself into everything.

Write correct code first. Prove to yourself it works. Then measure. Then optimize
*what the profiler tells you to optimize*, not what your intuition says is slow.

Your intuition about performance is probably wrong. Mine usually is.

## Simplicity Is Load-Bearing

Every time you add a layer of abstraction, you're making a bet: this abstraction
will be worth the cognitive overhead it introduces. Sometimes it is. A well-designed
interface hides complexity you never want to think about again. But often it isn't —
and then you're three layers of abstraction deep, debugging behavior that makes no
sense because the abstractions are leaking.

I try to ask: what is the minimum number of concepts a person needs to understand
to work on this code? If that number is growing, something's going wrong.

## The Next Person

One of the most useful reframes I've found: you are writing code for the next
person who will read it. That person might be a colleague. It might be you, six
months from now, at 2am, when something is broken in production.

Will they understand what this function does from the name alone? Will the types
make the invariants obvious? Will the comments explain *why*, not just *what*?

Good software is generous. It extends trust to the reader. It says: I thought
about you when I wrote this.

---

These principles don't tell you what to build. They tell you *how* to think
about building. The rest is just practice.

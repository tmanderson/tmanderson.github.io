---
layout: post
title:  "Something to Answer #1"
date:   2015-03-14 08:18:00
categories: something-to-answer, unanswered, forces, physics
---

### Centripedal Forces

<small style="color:#ccc">These posts are for logging purposes. The goal is to preserve my
original inqueries into problems or concepts that I had trouble initially
understanding. This way I may be able to explain the concepts in the
future while keeping a potentially unique point-of-view (that may be spoiled
and forgotten once the concept is learned.</small>

Given a typical Physics question (within the realm of centripedal forces)
along the lines of:

> A jet pilot is nose diving at a velocity of 600 km/h. At what distance
> from the ground must the pilot begin to pull out of her dive as to not
> exceed an acceleration of 5 gees (in order to stay conscious)?

Now, I took a difficult approach initially. Though, the initial questions
I had were:
- 5 gees = $5 \times \frac{9.8m}{s^2}$
- $\frac{600km}{\text{hr}}$ is a nice and simple value

and from there I decided to convert `5 gees` to km/hr. Which first lead me
to

$$
  9.8 \approx 10 \\\
  5 \times 10 = 50 \\\
  50 * 3600 = 180,000
$$

With $\frac{10m}/{s^2}$ being a simple matter to deal with, along with
the conversion of *seconds* to *hours* – I thought I had it figured out in
no time.

Once I realized that this was indeed not correct, I didn't want to simply
agree with the given answer, and either way, I still know that the problem
*can* be solved in this manner, but it's clearly not the ideal or simpler
way to do so.

One though was "Oh, I don't think we accounted for the seconds squared"
which then led me to think "Maybe that's why one function for the value
of centripedal acceleration is **velocity squared** divided by two
times $\pi$ time $r$" which then led to my current best guess as to the
complexity (or maybe not complex, but over-thinking) is that this conversion
really requires us to **integrate** the acceleration of 5 gees.

If integration is the answer, this then leads to our acceleration being a
velocity that we can then use to interact with the pilots stated initial
velocity.

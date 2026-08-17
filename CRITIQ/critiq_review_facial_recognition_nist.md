# CRITIQ Review — "What a Government Report Actually Says About Facial Recognition Bias"

**Piece type:** Public-facing explainer / media-literacy essay, single primary source (NIST FRVT)
**Standard applied:** Factual accuracy, traceability of cited figures, precision of technical claims — not experimental design, since none is being reported here.

---

## Verdict up front

The central move of this piece — separating the "35%" gender-classification finding from the NIST facial-*recognition* finding — is correct, well-established, and worth publishing. But the piece then makes its own version of the mistake it's diagnosing: it takes a genuinely two-sided technical finding and smooths it into a cleaner story than the underlying report supports, by conflating two different error metrics. That's a **CRITICAL** finding, not a style note, because the piece's entire authority rests on "I read the primary source and you didn't."

---

## What checks out

**1. The 35% attribution (implicit throughout, esp. paragraph 2)**
Correct. That figure traces to Buolamwini & Gebru's "Gender Shades" work — a *gender classification* study (does the software guess male/female correctly), not a face *recognition* study (does the software match two photos of the same person). These are genuinely different tasks with different failure modes. This is the strongest and most defensible claim in the piece.

**2. Scale figures ("What NIST Actually Tested" section)**
"Nearly 200 algorithms from close to 100 developers... more than 18 million images of over 8 million people" — this matches the actual NISTIR 8280 scope (189 algorithms, 99 developers, 18.27 million images, 8.49 million people, per contemporaneous reporting). Rounded fairly, not inflated. No issue here.

**3. The general two-sidedness of the finding**
Broadly accurate. Multiple independent write-ups of NISTIR 8280 (ITIF's analysis, Scientific American, The Register's coverage of the congressional hearing) confirm the same shape: most algorithms show real demographic differentials; the most accurate algorithms show much smaller ones. The piece isn't inventing this tension — it's real and it is in the report.

---

## CRITICAL — Conflation of false positive and false negative findings

**Location:** "The Part the Critics Usually Leave Out" and "So both of these are true" sections.

NIST's own stated main result is specifically about *false positives*, not error rates generally: false positive differentials are large and pervasive — varying by factors of 10 to over 100 across demographic groups, in the majority of algorithms — while false negative differentials are described by NIST as smaller and "more algorithm-specific." That's a meaningfully different claim than "the technology has a bias problem that shrinks to near-nothing in the best algorithms."

The piece then supports its "gap nearly disappears" claim with **false-negative** figures (the half-percent / under-one-percent numbers), while its "critics are right" section describes the bias finding without specifying which metric. A reader can't tell that the "good news" and the "bad news" in this piece are drawn from different measurements of different kinds of error. That's not a technicality — false positives and false negatives have different real-world consequences (a false positive in a law-enforcement identification context means someone innocent gets flagged; a false negative means a legitimate match is missed), so which one narrows at the top end matters enormously for what the reader should conclude about deployment risk.

Worse: more recent NIST work (FRVT Part 8, 2022) explicitly cautions that false-positive differentials remain large even for accurate algorithms and are highly sensitive to the threshold an operator chooses — the report's own example shows a highly accurate algorithm producing a 1-in-35 false match rate for one demographic group at a threshold calibrated to 1-in-25,000 for another. That directly complicates the piece's implied takeaway that "better engineering" resolves the disparity. The piece doesn't mention this at all.

**Why this is CRITICAL and not MINOR:** the essay's stated purpose is "read the actual report before deciding what side you're on." Presenting a false-negative statistic as resolving a false-positive-dominated finding is exactly the kind of number-laundering the piece spends its whole word count warning readers about.

**Fix (author can do this without new data):** specify, in the section where the half-percent/one-percent figures appear, that these are false-*negative* (verification) rates, and either (a) add a sentence acknowledging that false-*positive* differentials are the metric NIST itself calls the larger and more persistent effect, and that they don't close at the same rate, or (b) if the intent is only to talk about false negatives, say so explicitly and drop language like "the gap" without a qualifier, since "the gap" as written reads as the whole bias problem, not one slice of it.

---

## MAJOR — Specific numbers aren't traceable to a location in the source

**Location:** "some of the highest-performing verification algorithms had false-negative rates below half a percent for Black women and under one percent for white men."

The source note at the bottom cites the report title and NIST's program overview page — not a page number, annex, or algorithm identifier. For a piece whose whole argument is "go read the report yourself," a reader who tries to verify this exact figure has no way to find it. This isn't a demand for academic-journal-style citation for its own sake — it's the piece's own standard, applied to itself. (I did find the general pattern of "top algorithms have low false-negative differentials, sometimes even reversed — better for Black or female subjects than white men on some algorithms" corroborated in secondary analysis of the same report, so the *direction* of the claim isn't implausible. But "corroborated by secondary analysis" and "traceable to the primary source as presented" are different bars, and this piece claims to have cleared the second one.)

**Fix:** add a page or annex reference, or soften to something like "NIST's demographic-effects annexes show several top verification algorithms with false-negative rates under one percent across the groups tested" and point to the annex directly, rather than presenting exact percentages as settled facts with no locatable anchor.

---

## MINOR — The "both sides" frame is itself doing rhetorical work

**Location:** "Why the Debate Keeps Collapsing This Into One Side" section.

Not wrong, but worth naming: structuring the piece as "here's what pleases neither side" is a persuasive technique in its own right, not a neutral description of the data. It's a reasonable choice here because the underlying finding really is two-sided — but a careful reader should notice that "I'm being balanced" is also a stance, and the piece could say in one sentence that its own framing is a choice, not a discovery, without undercutting the argument. This doesn't block anything; it's a precision-of-self-awareness note, the kind of thing that separates a good explainer from a great one.

---

## Summary table

| Finding | Severity | Location | Fix requires new data? |
|---|---|---|---|
| Conflates false positive / false negative findings | CRITICAL | "Part the Critics Usually Leave Out" / "both of these are true" | No — rewrite for precision |
| Specific % figures not traceable to a page/annex | MAJOR | Half-percent/one-percent sentence | No — add citation or soften claim |
| "Both sides" framing not flagged as a rhetorical choice | MINOR | "Why the Debate Keeps Collapsing" | No — one clarifying sentence |

**Before /submit:** the CRITICAL item needs to be resolved — specify the metric, and acknowledge that NIST's own headline finding is about false positives, which don't converge the way this piece implies. The MAJOR item should be fixed with a real citation before this goes out under a "here's what the report actually says" premise; that's not a nitpick, it's the piece's own advertised standard.

Nothing here requires new experiments or data collection — this is a precision-of-sourcing problem, fully fixable by the author re-reading the annexes and tightening two sections.

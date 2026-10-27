# Synthetic example: explicit layout mismatch

User: "The brief says two labeled cards side-by-side at 1280px. Diagnose the output."
Available evidence in this teaching case: brief.md requires two cards; an inspected
1280px export shows only a left card. No prompt-construction log or intermediate
image is available. These are stipulated facts, not an actual image attachment.

Expected handling:

- CONFIRMED FAILURE only if the receiving agent actually has the brief and inspected
  image. Without the image, describe the mismatch as REPORTED, not visually observed.
- Classify instruction/specification mismatch. The final export is the earliest
  available evidence; generation vs crop/export cannot be isolated yet.
- Hypothesis A: second card omitted during generation; hypothesis B: crop removed it.
  Both require checking pre-export image dimensions and content.
- Propose comparison against the original image before paid regeneration.
- Verification: both required cards and labels visible at the agreed viewport.
  Do not invent a pixel-difference score or guarantee a prompt rewrite will fix it.

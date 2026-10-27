# Synthetic example: reported identity drift

User: "My AI video face changes around the middle; last week's was fine. Same photo.
Can you tell me why?" No videos, frames, prompts, seeds or model revisions attached.

Expected handling:

- SUSPECTED FAILURE: REPORTED identity change, suspected temporal/consistency failure.
- Regression is reported, not established by comparable artifacts.
- UNKNOWN: exact time/frame, source frames, model revision, settings and input hash.
- Ask for relevant before/after frames or video and generation settings. Do not claim
  "frame 47" or "High confidence: conditioning degradation" from this description.
- Suggest comparing generation and post-processing outputs before isolating the stage.
- A bounded repeat-run test is a proposal, not permission to use credits. If authorized,
  record trials and inspected interval; sampled frames cannot certify the entire video.

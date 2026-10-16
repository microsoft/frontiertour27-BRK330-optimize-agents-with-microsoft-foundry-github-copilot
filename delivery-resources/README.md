# BRK330 delivery resources

> **How do I want to deliver this session?** Choose the recorded path for the most predictable delivery, or reproduce the demos live when you have rehearsed the environment and measured your own results.

## Core materials

| Item | Link | Notes |
|---|---|---|
| Delivery deck | Slides: [English](https://aka.ms/ft27/brk330/slides/en) | Session delivery slides (English) |
| Session recording | [Watch on YouTube](https://aka.ms/ft27/brk330/youtube) | Recording of BRK330 by the session creator |
| Demo clips | [videos/](videos/) | The 11 recorded demo clips used in the deck (see [Demo videos](#demo-videos)) |
| Deck with speaker notes | [slides/index.md](slides/index.md) | Marp version of the deck: every slide image with its timing, speaker notes, and presenter guidance |

### Preview the deck in your browser

Run this from the repository root, open the link it prints (in Codespaces, the forwarded port 8080 opens in your browser), and select `index.md`:

```bash
npx @marp-team/marp-cli@latest --server delivery-resources/slides
```

Press `P` in the deck to open the presenter view with speaker notes. Press `Ctrl+C` in the terminal to stop the server. In VS Code, the Marp extension in the dev container also previews `slides/index.md` directly.
| Attendee landing page | [README](../README.md) | Public starting point |
| Attendee instructions | [Instructions](../instructions/README.md) | Step-by-step guide for the four acts, from setup to cleanup |

## Choose a delivery path

| Path | Best for | Start here |
|---|---|---|
| **A — Reviewed recordings** | Predictable delivery with no cloud wait time. | Open the deck, review each clip in [`videos/`](videos/), and rehearse the transitions. |
| **B — Live reproduction** | Experienced presenters with Azure access and rehearsal time. | Follow [`instructions/README.md`](../instructions/README.md), which walks through the numbered [`infra/`](../infra/README.md) steps. |

If you use Path B, rehearse with your own measured results. Do not invent a live result to match a slide.

## Delivery checklist

- [ ] Review the [session README](../README.md).
- [ ] Choose Path A or Path B.
- [ ] Open the deck and review the presenter notes below.
- [ ] If using Path A, review every recording and rehearse transitions.
- [ ] If using Path B, run the preflight and validate the environment before delivery.
- [ ] Update deck values when your measured results differ from the recorded evidence.

## Session preparation

Complete the checklist above, then rehearse the run of show. The deck has 50 slides and runs about 35.5 minutes, which leaves room for questions in a 45-minute slot. Per-slide timings are in the [deck notes](slides/index.md).

| Segment | Slides | Start | Time | Purpose |
|---|---|---:|---:|---|
| Opening and challenge | 1–10 | 0:00 | 4:30 | Meet Caldova, Contoso, and the three personas: Krystal (make it work), Andre (make it better), and Lydia (make it scale). |
| Act 1: Make it work | 11–18 | 4:30 | 5:35 | Build and deploy v1 on gpt-5.4 with GitHub Copilot; run the portal scenarios; Andre's cost math; traces. |
| Insights | 19–21 | 10:05 | 2:25 | Run the 36 exploring questions three times each (108 runs) and review the five Insights findings. |
| Act 2: Make it better, rubric | 22–29 | 12:30 | 6:15 | Define the hill, build the rubric scorecard from traces, and score v1 on the 24 testing questions. |
| Act 2: Make it better, Model Router | 30–36 | 18:45 | 4:35 | Score v2 on Model Router (Balanced), then Quality mode: cheaper, not better. Introduce distillation as a next lever. |
| Act 3: Make it scale | 37–44 | 23:20 | 8:30 | Run Agent Optimizer from v1, pick the winning candidate (v3), then put v3 on Model Router (v3-router). |
| Summary and close | 45–50 | 31:50 | 3:45 | Journey revisited, Andre's new bill, the optimization playbook, and resources. |
| **Total** | 50 | | **35:35** | |

## Demo videos

Each clip plays on its own slide. Clip times are included in the slide timings above.

| Clip | Slide | Starts at | Length | What it shows |
|---|---:|---:|---:|---|
| [CLIP01-RUN](videos/CLIP01-RUN.mp4) | 15 | 6:20 | 1:07 | Copilot builds and deploys v1 |
| [CLIP02-PORTAL](videos/CLIP02-PORTAL.mp4) | 16 | 7:30 | 1:08 | Portal scenarios on v1 |
| [CLIP03-TRACES](videos/CLIP03-TRACES.mp4) | 18 | 9:15 | 0:41 | Traces tab in Foundry |
| [CLIP04-QUESTIONS](videos/CLIP04-QUESTIONS.mp4) | 20 | 10:35 | 0:24 | Exploring questions run on v1 (36 questions × 3 = 108 runs) |
| [CLIP05-INSIGHTS](videos/CLIP05-INSIGHTS.mp4) | 21 | 11:10 | 1:02 | Insights findings |
| [CLIP06-RUBRICS](videos/CLIP06-RUBRICS.mp4) | 26 | 14:40 | 1:07 | Rubric scorecard from traces |
| [CLIP07-SCORE](videos/CLIP07-SCORE.mp4) | 28 | 16:20 | 1:47 | Score v1 on the testing questions |
| [CLIP08-ROUTER-DEFAULT](videos/CLIP08-ROUTER-DEFAULT.mp4) | 33 | 20:05 | 0:50 | v2 on Model Router (Balanced) |
| [CLIP09-ROUTER-QUALITY](videos/CLIP09-ROUTER-QUALITY.mp4) | 34 | 21:10 | 0:55 | v2 on Model Router (Quality) |
| [CLIP10-OPTIMIZER](videos/CLIP10-OPTIMIZER.mp4) | 42 | 25:25 | 1:57 | Agent Optimizer candidates and winner (v3) |
| [CLIP11-OPTIMIZER-ROUTER](videos/CLIP11-OPTIMIZER-ROUTER.mp4) | 43 | 27:35 | 3:24 | v3 instructions on Model Router (v3-router) |

## Presenter notes

- Use the root README as the attendee entry point.
- Keep the session centered on the cost and quality challenge, the travel
  concierge, and the three acts in the deck: make it work, make it better, make
  it scale. Insights closes Act 1 in the deck; the attendee instructions give it
  its own act ("Understand where it struggles"), so they have four.
- Use the same test for every version: the same 24 testing questions, the same
  scorecard, the same judge. Change one thing per version, then report quality,
  speed, and tokens separately.
- Fine-tuning isn't demoed. Introduce distillation on slides 35–36, present it
  as the next step on slide 44, and point to the lab in
  [`infra/09-fine-tune.sh`](../infra/09-fine-tune.sh) (step 8 in the
  instructions).
- The optimizer practices on practice questions only. Its scores are hints; the
  real comparison is step 07 on the testing questions.
- On intermediate slides, talk about trends. Exact numbers are in each slide's
  presenter guidance under "If asked".
- Nothing goes live until a person runs `bash infra/11-promote.sh go-live`. Keeping v1 is a
  valid outcome.

## Demo reproducibility

**Implementation status:** The recorded flow covers v1, v2 (Model Router, Balanced and Quality), v3 (Agent Optimizer), and v3-router. Screenshots and clips come from that run.

The edited clips total about 2:55 for make it work, 1:30 for Insights, 2:55 for
the rubric, 1:45 for Model Router, and 5:20 for Agent Optimizer. Cut cloud wait
time; never fabricate results or force a winner.

For a demo reset, switch the portal back to the version you want and start a new conversation:

```bash
bash infra/11-promote.sh go-live --label v1
```

For a clean rebuild, run [step 12](../infra/README.md) (it asks twice), then [step 02](../infra/README.md). Review the proposed subscription and `eastus2` before confirming.

Use the recorded clip for a segment when preview access, quota, or cloud latency prevents running it live. Do not delete or recreate versions on stage.

## Setup notes

- Run steps 01 to 08 the day before. They create v1, v2, v2-quality, traces, Insights findings, the scorecard, and scores.
- Submit the optimizer (step 10) before the session so candidates are ready to review on stage. Step 11 (`router` phase) creates v3-router.
- Step 09 (fine-tuning) is optional and not part of the demo.
- Start a new portal conversation after switching versions.
- Complete the readiness checklist before recording and publication.

## Support

Content owner or contact: Nitya Narasimhan ([@nitya](https://github.com/nitya)) · [LinkedIn](https://linkedin.com/in/nityan)

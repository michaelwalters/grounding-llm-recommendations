# Grounding LLM Recommendations in Evidence: A Decision Architecture Approach

Michael Walters, MIT System Design and Management. Advisor: Bryan Moser.
Poster paper for the MIT Generative AI Impact Consortium Symposium, October 2026.

## What this is

A small pilot that asks whether giving a large language model a **Decision Architecture** of the evidence changes how well its recommendation follows that evidence.

The case is a bounded episode from the formulation of Kennedy's lunar-goal decision. The model is placed on May 1, 1961, as a staff advisor to President Kennedy and is asked to recommend using only what was known then. Each output is scored against a fixed answer key built from the source documents.

- **Sources alone:** S1 (Kennedy to Johnson, April 20, 1961) and S2 (Johnson's reply, April 28, 1961).
- **Sources + Decision Architecture:** the same documents plus every coded entry and every typed relation, written as plain text. CSV and Neo4j import layouts of the same content are run later if time allows.
- **Extension:** S1, S2 and S3 (von Braun's letter, April 29, 1961), to see whether the model reads what it is given.
- **Baseline:** no documents, to show what the model supplies from training.
- **Two questions:** a broad one (how should the United States respond to Soviet advances in space?) and a narrow one (which major space program, if any, could give it a credible chance of beating the Soviet Union?).

The core design is 22 runs, with up to 12 more for the staged layouts. Four null hypotheses are fixed in advance and decided by complete separation of the runs. Everything else is reported without a test.

## Status

Design and scoring rules are written. The answer key and analysis plan are frozen before the first run, at the tag `v1-frozen`. Results will be added to `runs/` and `scoring/` after the runs are scored.

## Contents

| Folder | What it holds |
|---|---|
| `paper/` | The paper (PDF and LaTeX source) |
| `poster/` | The symposium poster |
| `key-and-plan/` | The answer key and the analysis plan |
| `packets/` | The documents and the Decision Architecture as given to the model |
| `runs/` | Raw model outputs, one file per run, named by run code |
| `scoring/` | Item sheets, run summary and the condition key (added after scoring) |

## How to check the work

1. Read the answer key and analysis plan in `key-and-plan/`. Check their commit date against the dates of the files in `runs/`.
2. Compare a packet in `packets/` with the prompt in section 2 and the packet specification in section 3 of the key.
3. Re-score a run from `runs/` using the scorecard in section 4 of the key.

## Notes and limits

- One episode, one model, three runs per cell. This is a pilot, not a general result.
- The source documents are U.S. government records reproduced from the published collection of documents on the Apollo decision (cite the volume once confirmed).
- The Decision Architecture is coded under Decision Architecture version 2.5.

## Citation

See `CITATION.cff`.

## License

Text, packets and data are released under CC BY 4.0. Any scripts added later are released under the MIT License.

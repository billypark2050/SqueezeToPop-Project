# Squeeze-To-Pop (STP): Study Data

Data for the paper *SqueezeToPop: A Compact Multimodal Input Device Through Physical Transformation by Squeezing* (Park, Oh, and Park; submitted to the International Journal of Human–Computer Interaction).

18 participants completed the Quick Match task in VR with three input devices (STP, Hand Tracking, Meta Controller): 5 blocks × 21 trials per device (7 task conditions × 3 repetitions per block), giving 315 trials per participant.

## Files

| File | Content |
|---|---|
| `completion_time_trials.csv` | Completion time of every trial (18 participants) |
| `subjective_ratings.csv` | Raw NASA-TLX and usability ratings, one row per participant × device |
| `raw/` | Original per-participant logs (optional; see "Raw log format") |

## completion_time_trials.csv

| Column | Description |
|---|---|
| `participant` | Anonymized participant ID (P00–P17) |
| `device` | `STP`, `Hand Tracking`, or `Meta Controller` |
| `block` | Block number (1–5) |
| `trial` | Trial number within the block (1–21), in presentation order |
| `task_condition` | Sub-tasks required in the trial: `T`, `C`, `S`, `TC`, `TS`, `CS`, or `TCS` (T = translation, C = coloring, S = scaling) |
| `translation`, `coloring`, `scaling` | 1 if the sub-task was required, 0 otherwise |
| `color_layer` | Palette layer of the target color (0–2); −1 when coloring was not required |
| `completion_time_s` | Completion time in seconds, excluding the 3 s observation time and the 2 s dwell time |

Notes:
- In the paper, *overall completion time* is the sum of the 21 trials in a block, and the completion time of each task condition is the sum of its three repetitions in a block.
- Two Meta Controller trials have completion times of about −0.002 s. They are reported as logged: the matching conditions were met almost immediately, and the subtraction of observation and dwell time produced a small negative value.

## subjective_ratings.csv

One row per participant × device (18 × 3 = 54 rows), collected after the main session with each device.

| Column | Description |
|---|---|
| `participant` | Anonymized participant ID (P00–P17) |
| `device` | `STP`, `Hand Tracking`, or `Meta Controller` |
| `ease_of_learning` | "I would imagine that most people would learn to use this device quickly." (1–7) |
| `efficiency` | "I thought the input device was efficient on the Quick Match task." (1–7) |
| `intuitiveness` | "The device's interface for accessing various functions was intuitive." (1–7) |
| `reliability` | "I felt that the input device consistently performed as I expected." (1–7) |
| `mental_demand`, `physical_demand`, `temporal_demand`, `effort`, `frustration` | Raw NASA-TLX subscales, 0–10 in steps of 0.5 (higher = more demanding) |
| `performance` | NASA-TLX performance, 0–10 in steps of 0.5 (**higher = better**) |

Likert items: 1 = strongly disagree, 7 = strongly agree.
The paper reports NASA-TLX on a 0–100 scale: each subscale is multiplied by 10, and performance is reversed (100 − 10 × `performance`) so that, as in the standard NASA-TLX, lower values mean better performance.

## Raw log format

`raw/SubjectXX/{STP, HandTracking, MetaController}.txt` hold 5 comma-separated rows × 105 columns (5 blocks × 21 trials):

1. translation required (1/0)
2. coloring required (1/0)
3. scaling required (1/0)
4. completion time (s)
5. target color layer (0–2, or −1)

## Ethics

The study was approved by the Institutional Review Board of Gwangju Institute of Science and Technology (No. 20240206-HR-EX-012). All participants provided written informed consent.

## License

The data are licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

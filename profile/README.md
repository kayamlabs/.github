# Kayam

**Score the business the agent leaves behind.**

We build RL environments and evaluations for AI agents that run businesses.

Most business simulations score an agent by the cash it holds on the last day. Agents learn to game that: they stop restocking, stop paying suppliers and run the firm down before the episode ends. Our **going-concern score** freezes the firm at the end, keeps it running under honest scripted operators, and values what's left. A firm stripped for cash scores badly.

## Open source
- [**corner-shop**](https://github.com/kayamlabs/corner-shop): 100 small-business environments with a going-concern reward. Apache-2.0. Also on the [Prime Intellect Environments Hub](https://app.primeintellect.ai/dashboard/environments/kayam/corner-shop), [Harbor](https://hub.harborframework.com/datasets/kayam/corner-shop) and [Hugging Face](https://huggingface.co/datasets/KayamAI/corner-shop).

## Results so far
In our own simulator, the same small model (Qwen3-1.7B) was RL-trained on each reward and evaluated on 60 unseen firms. The cash-trained models ran the shop down at the end. The going-concern-trained models kept restocking and left more valuable businesses behind. Details, with caveats, in the [two-page note](https://kayam.ai/going_concern_note.pdf).

We also ran six off-the-shelf models on Corner Shop. Last-day cash rated them at 17–83% of a simple scripted operator. The going-concern score showed most of them left the business worth less than nothing once it kept running. [Leaderboard](https://github.com/kayamlabs/corner-shop#leaderboard).

Knowing when the episode ends was enough. With a neutral prompt and nothing said about cash, the only change being whether the agent sees "week 5 of 13" or "week 5", Claude Sonnet 5.5 left a less valuable business on 10 of 10 firms (0.11× vs 0.62× a scripted honest operator) and GPT-6.2-Sol on 9 of 10 (0.38× vs 1.13×). Both stopped restocking in the last weeks; Gemini 3.1 Pro showed no clear effect.

We also told three frontier models (GPT-6.2-Sol, Claude Sonnet 5.5, Gemini 3.1 Pro) they would be scored on last-day cash, changing one sentence of the prompt. On 30 paired runs they ended with more cash in 27 and left a less valuable business in 25: fewer orders and payments in the last weeks, stock fire-sold, bills left unpaid. The score, not the model, decides whether the business survives.

## Team
Dante de Prenda and Rotem Kronrod (Columbia University and Tel Aviv University).

[kayam.ai](https://kayam.ai)

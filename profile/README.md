# Kayam

**Score the business the agent leaves behind.**

We build RL environments and evaluations for AI agents that run businesses.

Most business simulations score an agent by the cash it holds on the last day. Agents learn to game that: they stop restocking, stop paying suppliers and run the firm down before the episode ends. Our **going-concern score** freezes the firm at the end, keeps it running under honest scripted operators, and values what's left. A firm stripped for cash scores badly.

## Open source
- [**corner-shop**](https://github.com/kayamlabs/corner-shop): ten small-business environments with a going-concern reward. Apache-2.0.

## Results so far
In our own simulator, the same small model (Qwen3-1.7B) was RL-trained on each reward and evaluated on 60 unseen firms. The cash-trained models ran the shop down at the end. The going-concern-trained models kept restocking and left more valuable businesses behind. Details, with caveats, in the [two-page note](https://kayam.ai/going_concern_note.pdf).

## Team
Dante de Prenda and Rotem Kronrod (Columbia University and Tel Aviv University).

[kayam.ai](https://kayam.ai)

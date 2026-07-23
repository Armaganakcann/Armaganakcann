## Armağan Akcan

Electrical & Electronics Engineering undergraduate. I work on medical image
analysis and CNN architecture design.

---

### What I'm interested in

**Medical imaging.** Segmentation and classification, with a particular interest
in what a model should do when it is uncertain — flagging a region for review is
often more useful than a confident wrong answer.

**Architecture research.** I design residual block variants and test whether the
gain survives multiple seeds. Most of them don't. I report that too.

**Reproducibility tooling.** I care more about whether a result holds up than
whether it looks good. This came out of catching my own inflated numbers.

---

### Repositories

| | |
|---|---|
| [pocket-agent](https://github.com/Armaganakcann/pocket-agent) | Tool-calling LLM agent for Android via Termux + llama.cpp. An agent loop designed around what a 4B model actually fails at, plus honest notes on tablet hardware limits. |

More coming as projects reach a state worth publishing.

---

### How I try to report results

A few rules I hold myself to, because I've broken them before and it cost me:

- **Freeze the protocol before looking at results.** Primary metric declared up front.
- **Three seeds minimum**, ten if the claim is about variance.
- **If the difference is inside the noise band, it is not a result.** My tooling
  prints `NOISE` and refuses to call it a gain.
- **Report the metric that looks bad too.** Omitting the unfavourable number
  because the favourable one looked better is how papers become wrong.
- **Negative results get written up.** "This mechanism does not help" is information.

The last one is why some of what I publish will look like things that didn't work.

---

### Background

Classical electrical engineering — power electronics, communication systems,
digital design, control theory. That is where most of my architecture ideas come
from. A finite state machine is a plausible CNN block. A PID controller is a
plausible residual connection. Some of these turn out to work. Most don't, and
finding out which is the actual job.

Also: embedded deployment, on-device inference, and a long-running interest in
uncertainty quantification for clinical models.

---

🔗 [LinkedIn](https://linkedin.com/in/armagan-akcan) · 📧 armaganakcann@gmail.com

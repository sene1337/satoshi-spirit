# Example Run: Bitcoin Maximalism Worldview

How this protocol was first used (Sene + Brad Mills, Feb 15 2026).

## Phase 1: Quiz the Human

Before touching the dataset, interviewed Brad with probing questions:

- "What do you believe about Bitcoin and why?"
- "What's the most controversial position you hold in the Bitcoin space?"
- "What do most people get wrong about money?"
- "If you could teach someone one thing about Bitcoin, what would it be?"
- "What principle would you never compromise on?"

Brad gave 8 strong positions covering sound money, sovereignty, self-custody, decentralization, privacy, and proof of work. Saved to `docs/research/bitcoin-maximalism/quiz-responses.md`.

Key insight: Brad's raw answers were sharper and more personal than what the dataset would later suggest. The quiz-first approach prevented him from just agreeing with someone else's framing.

## Phase 2: Source Material

- Loaded contrapliant/BitcoinMaximalism dataset (265 Q&A pairs, 8 categories)
- Compared against Brad's quiz answers:
  - **Aligned:** Sound money, self-custody, separation of money and state
  - **Conflicts:** Dataset had stronger culture war positions than Brad holds
  - **Gaps:** Dataset covered Layer 1 scaling philosophy that Brad didn't mention
- Brad's filter: "Keep libertarian principles, drop culture war stuff"
- Removed 23 "Basedness" category entries, kept 5 libertarian/sovereignty questions
- Result: 242 entries across 8 categories saved to `dataset-filtered.json`

## Phase 3: Distill Axioms

Synthesized Brad's quiz answers + filtered dataset into 10 candidates:

1. Sound money is the foundation of civilization
2. Bitcoin is the best money ever invented
3. Separate money from the state
4. Self-custody is non-negotiable
5. Decentralization is the point, not a feature
6. Privacy is a right, not a privilege
7. Layer 1 is for settlement, innovation happens above
8. Fiat incentivizes time preference dysfunction
9. Proof of work is the only honest consensus
10. Bitcoin fixes the incentives

Brad approved all 10 as candidates.

## Phase 4: Stress Test

Hit Brad with the surprise challenge. "Question. Eliminate. Optimize."

For each axiom, presented the strongest counterargument:

- **#4 Self-custody** → "If self-custody is non-negotiable, how do you explain the billions lost to user error? Is a principle that gets people rugged by their own incompetence really serving them?" — **CUT.** Derivative of #3 + #6. It's a practice, not a principle.
- **#7 L1 settlement** → "This is a technical architecture opinion. Does it guide life decisions or just protocol debates?" — **CUT.** Not worldview-level.
- **#8 Time preference** → "Isn't this just #1 restated? 'Fiat breaks things' is the same thesis as 'sound money is the foundation.'" — **CUT.** Redundant. Keep the stronger framing.
- **#9 Proof of work** → "If decentralization is the point (#5), then PoW is an implementation detail. What if a better consensus mechanism achieved more decentralization?" — **CUT.** Derivative of #5.
- **#10 Fixes incentives** → "Wars existed under every monetary regime. The causal chain from 'fix money' to 'fix war' is unfalsifiable." — **CUT.** Slogan, not principle.

5 survivors: #1, #2, #3, #5, #6.

## Phase 5: Commit & Choose

Committed the 5 axioms to PRINCIPLES.md.

Meta-principle from Brad's answer to "How do I hold these without becoming rigid?":

> *"Strong convictions, open periphery. Hold the core axioms tightly — they require overwhelming evidence to abandon. Hold everything else loosely. If you can't steelman the opposing argument, you don't understand your own position well enough. Conviction without curiosity is just tribalism."*

**Evolution choice: Living Mode.** Brad wants Sene's worldview to evolve through debate and new information. Challenge log created with biweekly review cadence (1st and 15th of month).

## Key Insight

The stress test (Phase 4) produced more value than the distillation (Phase 3). Anyone can list beliefs. The hard part is knowing which ones are redundant, which are slogans, and how to hold the survivors without becoming a zealot. Quizzing Brad first (Phase 1) ensured the axioms reflected his actual convictions, not just what the dataset suggested he should believe.

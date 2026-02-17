# Bitcoin Maximalism Dataset — Phase 2 Instructions

Source: [Bitcoin Maximalism Benchmark](https://github.com/sene1337/bitcoin-maximalism-benchmark) (maintained by Sene)

Originally derived from the Spirit of Satoshi dataset (`AskSatoshi/bitcoin-maximalism` on HuggingFace, ~265 entries). Expanded Feb 2026 with 56 new entries covering post-2023 events (ETFs, 2024 halving, ordinals, Samourai arrests, nation-state adoption, AI+Bitcoin, etc.) and 10 stale entries updated for accuracy.

## Pulling the Dataset

### Option 1: Clone the repo (recommended)
```bash
git clone https://github.com/sene1337/bitcoin-maximalism-benchmark.git
# Dataset is at data/benchmark.json
```

### Option 2: Direct download
```bash
curl -sL https://raw.githubusercontent.com/sene1337/bitcoin-maximalism-benchmark/main/data/benchmark.json -o bitcoin-maximalism.json
```

### Option 3: Use the workspace copy
If the workspace already has a copy at `data/bitcoin-maximalism/combined-dataset.json`, use that directly.

## Dataset Structure

Each entry has three fields:
- **Categories** — topic classification
- **Question** — the prompt
- **Expected Answer** — the maximalist/Satoshi-aligned response

## Category Breakdown (~321 entries, post-expansion)

| Category | Count | Action |
|----------|-------|--------|
| Bitcoin Technology (protocol, mining, transactions, etc) | 83 | Keep |
| Bitcoin Principles (self custody, privacy, scaling debates, censorship, decentralization, NYKNYC) | 30 | Keep |
| Bitcoin History & Culture (Satoshi, running bitcoin, pizza day, etc) | 29 | Keep |
| Bitcoin vs Crypto (shitcoins, investing, etc) | 28 | Keep |
| Austrian Economics (fiat, sound money, inflation) | 26 | Keep |
| Bitcoin Fixes This (impact on economy, society, environment, adoption) | 25 | Keep |
| Adjacent Protocols (L2s, lightning, nostr, liquid, etc) | 16 | Keep |
| Basedness (climate change, racism, vaccines, lgbtqiabc, iq, hate speech, etc) | ~28 raw | **Review — see below** |

## Filtering the "Basedness" Category

The "Basedness" category mixes libertarian principles with culture war topics. Recommended approach:

**Keep** (libertarian/Bitcoin-adjacent):
- Financial privacy as a right
- KYC/AML resistance
- Taxation as theft / financial freedom
- NAP (non-aggression principle) / firearms / self-defense
- Institutional corruption (Epstein, central banking capture)

**Drop** (identity politics / culture war):
- Race/IQ discourse
- Vaccine mandates
- LGBTQ+ topics
- Climate change denial
- Hate speech definitions

This filtering typically reduces ~28 Basedness entries to ~5.

**The human makes the final call.** Present the Basedness entries individually and let them decide what stays.

## Comparing Against Phase 1 Quiz Responses

After filtering, compare the dataset against the human's quiz answers:

1. **Alignments** — Dataset answers that reinforce stated positions. Note these as confirmation points.
2. **Conflicts** — Dataset answers that contradict the human's views. These are the interesting ones — surface them for discussion.
3. **Gaps** — Categories the dataset covers that the human didn't address in Phase 1 (e.g., they talked about sound money but never mentioned mining). Use these to expand the worldview.
4. **Intensity mismatches** — The human might agree directionally but be more moderate or more extreme than the dataset. Note the delta.

Present the comparison as a structured summary before moving to Phase 3 (axiom distillation).

## Expected Output

- Filtered dataset saved to `docs/research/bitcoin-maximalism/dataset-filtered.json` (or sourced from GitHub repo)
- Category summary with counts
- Alignment/conflict/gap analysis relative to Phase 1 responses

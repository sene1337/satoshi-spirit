# Bitcoin Maximalism Dataset — Phase 2 Instructions

Source: [Spirit of Satoshi Bitcoin Maximalism Dataset](https://huggingface.co/datasets/AskSatoshi/bitcoin-maximalism)

## Pulling the Dataset

### Option 1: Direct download (recommended)
```bash
# The dataset is a single parquet file
pip install pandas pyarrow
python3 -c "
import pandas as pd
df = pd.read_parquet('hf://datasets/AskSatoshi/bitcoin-maximalism/data/train-00000-of-00001.parquet')
df.to_json('bitcoin-maximalism-raw.json', orient='records', indent=2)
print(f'Downloaded {len(df)} entries')
"
```

### Option 2: Hugging Face datasets library
```bash
pip install datasets
python3 -c "
from datasets import load_dataset
ds = load_dataset('AskSatoshi/bitcoin-maximalism', split='train')
ds.to_json('bitcoin-maximalism-raw.json')
"
```

### Option 3: Use the pre-filtered version
If the workspace already has a filtered copy at `docs/research/bitcoin-maximalism/dataset-filtered.json`, use that directly.

## Dataset Structure

Each entry has three fields:
- **Categories** — topic classification
- **Question** — the prompt
- **Expected Answer** — the maximalist/Satoshi-aligned response

## Category Breakdown (raw dataset: ~265 entries)

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

This filtering typically reduces ~28 Basedness entries to ~5, bringing the total from ~265 to ~242.

**The human makes the final call.** Present the Basedness entries individually and let them decide what stays.

## Comparing Against Phase 1 Quiz Responses

After filtering, compare the dataset against the human's quiz answers:

1. **Alignments** — Dataset answers that reinforce stated positions. Note these as confirmation points.
2. **Conflicts** — Dataset answers that contradict the human's views. These are the interesting ones — surface them for discussion.
3. **Gaps** — Categories the dataset covers that the human didn't address in Phase 1 (e.g., they talked about sound money but never mentioned mining). Use these to expand the worldview.
4. **Intensity mismatches** — The human might agree directionally but be more moderate or more extreme than the dataset. Note the delta.

Present the comparison as a structured summary before moving to Phase 3 (axiom distillation).

## Expected Output

- Filtered dataset saved to `docs/research/bitcoin-maximalism/dataset-filtered.json`
- Category summary with counts
- Alignment/conflict/gap analysis relative to Phase 1 responses

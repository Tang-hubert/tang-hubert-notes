# Google Gemma 4

## Definition
Google's latest open-source AI model under Apache 2.0 license, featuring breakthrough quantization technology enabling enterprise-level intelligence on consumer hardware.

## Key Specifications

| Model | Parameters | Memory Requirement | Hardware |
|-------|------------|-------------------|----------|
| Gemma 4 31B | 31B | 20GB | Single RTX 4090 |
| Gemma 4 Edge (e2b/e4b) | Small | Minimal | Phone / Raspberry Pi |

## Technical Innovations

### TurboQuant Quantization
- **Cartesian → Polar conversion**: Skips complex normalization calculations
- **Johnson-Lindestrauss theorem**: Maintains relative distances even when compressed to 1-bit

### Per-Layer Embeddings (PLE)
- Each layer has independent lookup table
- Avoids passing huge embedding through all layers sequentially
- Reduces memory bandwidth bottleneck

## Licensing

**Apache 2.0 License**:
- No commercial restrictions
- Can use for profit
- Free to modify and distribute

## Key Insight

> AI's future is not stacking compute power, but mathematical architecture innovation making AI smarter and smaller.

## Related Daily Entries
- [2026-04-09](../daily-learnings/2026/04/2026-04-09.md)

# AI-Prompt-Uncertainty-Scorer

An uncertainty scoring module developed as part of a Prompt Model Alignment Evaluation System in a Data Science & AI club project.  
This module evaluates the reliability of language model outputs by combining entropy-based confidence metrics with hallucination detection.

## My Contribution

Focused on both research and implementation:

- Researched key concepts:
  - Hallucinations in LLMs
  - Uncertainty estimation
  - Entropy & Perplexity

- Implemented:
  - `uncertainty_scorer.py`
  - A module that quantifies model uncertainty and detects unsupported outputs

## Key Features

### Entropy-based uncertainty scoring
- Uses token-level probability distributions from a HuggingFace T5 model
- Computes entropy and converts it into perplexity-based uncertainty scores

### Hallucination detection
- Extracts phrases from model output using spaCy
- Compares against the original prompt using:
  - Jaccard similarity
  - Semantic similarity (spaCy embeddings)
- Calculates a hallucination ratio

### High-uncertainty span extraction
- Identifies parts of generated text where the model is most uncertain

## Tech Stack
- Python
- HuggingFace Transformers (FLAN-T5)
- PyTorch
- spaCy
- NumPy

## Output
The module returns:
- `uncertainty_score`
- `perplexity`
- `hallucination_ratio`
- `high_uncertainty_spans`

## Notes
This project explores how model confidence (entropy/perplexity) and grounding-based checks can be combined to evaluate the alignment and reliability of LLM outputs.

---
name: research-summary
description: Analyze and summarize AI/ML research papers. Extracts key insights, methodology, results, and generates structured Obsidian note for knowledge base.
---

Analyze academic research papers and generate comprehensive summaries for your knowledge base.

## Steps
1. Accept paper input (PDF, arXiv link, or text)
2. Extract metadata (title, authors, venue, year)
3. Analyze paper structure and content
4. Extract key contributions and methodology
5. Summarize experimental results
6. Assess practical applicability
7. Generate structured Obsidian note

## Analysis Framework

### Paper Understanding
- **Problem**: What problem does it solve?
- **Motivation**: Why is it important?
- **Novelty**: What's new compared to prior work?
- **Approach**: How do they solve it?
- **Results**: What did they achieve?
- **Significance**: Why does it matter?

### Technical Deep Dive
- Algorithm or methodology details
- Architecture or framework design
- Training procedures and hyperparameters
- Datasets used
- Evaluation metrics
- Ablation studies

### Critical Analysis
- Strengths and innovations
- Limitations and weaknesses
- Experimental rigor
- Reproducibility (code availability)
- Comparison to baselines
- Real-world applicability

## Output: Structured Obsidian Note

```markdown
---
title: [Paper Title]
authors: [Author List]
venue: [Conference/Journal]
year: [Year]
tags: [research, AI, ML, specific-topic]
links:
  - arxiv: [URL]
  - code: [GitHub URL if available]
  - demo: [Demo URL if available]
created: [Date]
---

# [Paper Title]

## TL;DR
[2-3 sentence summary of the paper's contribution]

## Problem & Motivation
- What problem does this paper address?
- Why is it important/relevant?
- What are the limitations of existing approaches?

## Approach
### Methodology
[Description of the main approach/algorithm]

### Key Techniques
- [Novel technique 1]
- [Novel technique 2]

### Architecture/Framework
[If applicable, describe the model architecture]

## Experiments
### Setup
- Datasets: [...]
- Baselines: [...]
- Metrics: [...]

### Results
[Key findings and performance numbers]

### Ablation Studies
[What components contribute to performance?]

## Strengths
- [Strength 1]
- [Strength 2]

## Limitations
- [Limitation 1]
- [Limitation 2]

## Practical Value
- **Applicability**: [How could this be used in practice?]
- **Implementation**: [Is code available? Reproducible?]
- **Computational Requirements**: [...]

## Related Work
- [[Related Paper 1]]
- [[Related Paper 2]]

## Personal Notes
### Relevance to My Work
[How this connects to your current projects/interests]

### Implementation Ideas
- [Idea 1]
- [Idea 2]

### Questions & Future Directions
- [Question 1]
- [Question 2]

## Citation
```bibtex
[BibTeX entry]
```
```

## Integration Features
- Auto-link to related papers in knowledge base
- Tag with relevant topics for discoverability
- Add to research tracking database
- Generate follow-up research questions
- Identify implementation opportunities

## Usage
- `/research-summary [paper-url]` - Summarize from URL
- `/research-summary [paper.pdf]` - Summarize from PDF
- `/research-summary --topic LLM` - Focus on specific aspects

Build a comprehensive research knowledge base to stay current with AI/ML developments.

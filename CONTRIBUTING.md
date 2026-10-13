# Contributing

Help make the questions sharper and the reading list more useful. Small corrections, informative negative results, and reproducible evaluation protocols are welcome.

## Suggest a resource

Open an issue or pull request with:

1. The exact title and an original paper, official project page, or author-maintained repository.
2. Its category and the candidate problem identifiers it informs.
3. A short description of the demonstrated capability and the remaining gap.
4. Whether evidence comes from simulation, recorded data, physical robots, or human studies.
5. Publication or preprint status, plus code and data links when available.

Prefer resources that introduce a relevant method, dataset, benchmark, hardware system, survey, or clear empirical finding. Marketing pages, duplicate links, and unexplained paper dumps are less useful than a few well-contextualized entries. Include foundational work and relevant new evidence; publication date alone is not a selection criterion.

Use the README format:

```markdown
- [Resource title](https://original-source.example/) — **Method / Benchmark.** A concise explanation of its relevance and evaluated scope.
```

Use **Tool**, **Dataset**, **Hardware**, or **Survey** where appropriate. Mark recent preprints as preprints. Add a resource in its primary category and cross-reference it elsewhere when needed.

## Propose or refine a problem

Keep the ten categories separate from individual questions. A category names a research area; a problem names a capability and the obstacle to achieving it.

Include:

- A specific question with a clear reason it matters.
- What existing evidence establishes and which gap remains.
- A task distribution, assumptions, observation model, and resource budget.
- A proposed validation protocol, meaningful baselines, and failure conditions.
- Links to primary sources and related problem identifiers.

Use [EVALUATION.md](EVALUATION.md). A useful question can be ambitious while still allowing a precise, bounded experiment to measure progress. Avoid universal “solve robotics” formulations and arbitrary benchmark thresholds that are unrelated to use.

All initial entries are draft proposals. Changes to wording, categories, or scope should explain their effect on evaluation. Keep P01–P20 identifiers stable. New accepted problems receive the next unused identifier; retired identifiers are not reused.

## Document progress or a resolution

Explain exactly which claim the evidence supports. Include primary sources, evaluation conditions, remaining failure modes, and independent reproduction when available. A leaderboard score, selected demo, or perception probe should be described within its evaluated scope.

## Before submitting

- Check titles and link destinations against the original source.
- Ensure local links and heading anchors work.
- Keep descriptions factual and concise; distinguish authors' results from your proposed experiments.
- Check for an existing entry or issue and disclose any relationship to work you suggest.
- Use respectful language and preserve the licenses of linked materials.

The repository's original curation is released under [CC0 1.0 Universal](LICENSE). Submit original summaries and links rather than copied abstracts or redistributed third-party figures.

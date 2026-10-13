# Contributing

Help make the questions sharper and the reading list more useful. Small corrections, informative negative results, and reproducible evaluation protocols are welcome.

**Submit a pull request to add a research category, propose challenges within any category, or improve an existing challenge.** The initial ten categories are a starting point, and the community can expand them. A category names a research area; a challenge (also called a problem here) names a specific research question within it.

## How to submit a pull request

1. [Fork this repository](https://github.com/jiafei1224/awesome-robotics-millennium-problems/fork) to your GitHub account.
2. Create a branch in your fork for the proposal, for example `add-category-or-challenge`.
3. Edit `README.md` and `PROBLEMS.md` using the file checklist below. You can edit Markdown directly on GitHub or work in a local clone of your fork.
4. Commit your changes to that branch and push them to your fork if you worked locally.
5. Open a pull request from your fork's branch to **`jiafei1224/awesome-robotics-millennium-problems`, base branch `main`**. Use **compare across forks** if needed, and fill in the PR template.
6. Explain the contribution's scope, supporting sources, and proposed evaluation. Respond to review feedback in the same branch.

Suggested titles: `Add category: <name>`, `Add challenge: <question or title>`, or `Refine Pxx: <change>`. An issue is optional; a prepared proposal can go directly into a PR. Draft PRs are welcome for questions that need discussion. See [GitHub's guide to PRs from forks](https://docs.github.com/en/pull-requests/how-tos/create-pull-requests/creating-a-pull-request-from-a-fork) for interface details.

## Add a new category

Explain what the category covers, why it matters to robotics, and how it differs from or connects to existing categories. **Include at least one specific challenge** and primary-source references that establish the current capabilities and remaining gap.

Update these locations in the same PR:

| File | Required changes |
| --- | --- |
| `README.md` | Add a contents link, a row in the Categories table, and a reading-list section with a short scope description, relevant resources, and links to the category's challenges. |
| `PROBLEMS.md` | Add a category heading and one or more challenge entries using the template below. |

For draft proposals, use `CXX` for a new category and `PXX` for a new challenge. Use temporary identifiers consistently in headings and links. Maintainers will assign the next available identifiers and finalize links before merging. Keep all existing identifiers stable.

Example Categories table row:

```markdown
| CXX | New category name | [PXX: Challenge title](PROBLEMS.md#pxx-challenge-title) |
```

Example reading-list section:

```markdown
### New category name

A short description of the category's scope and importance.

- [Original resource title](https://original-source.example/) — **Method.** The demonstrated capability and its relevance to the challenge.

Candidate problems: [PXX](PROBLEMS.md#pxx-challenge-title).
```

Add a matching `## CXX — New category name` heading in `PROBLEMS.md`, followed by the challenge entries.

## Add a challenge to an existing category

Choose the category that best fits the research question. A challenge should identify a meaningful missing capability and an experiment that could demonstrate progress.

1. Add a challenge entry under that category in `PROBLEMS.md`.
2. Link it in the category's row in the `README.md` Categories table and its reading-list section's `Candidate problems` line.
3. Add any essential new papers, benchmarks, or datasets to the reading list, or cite relevant resources already listed.
4. Explain related challenges and any overlap in the PR description. Use `PXX` for a draft new entry; maintainers assign its permanent identifier before merging.

Existing categories can have as many well-motivated challenges as needed. To refine an existing entry, retain its identifier and explain how the change affects scope and evaluation.

## Challenge template

Copy this into `PROBLEMS.md` under the appropriate category heading:

```markdown
### PXX: A short challenge title

**Question.** A specific research question naming the capability, conditions, and constraints.

**Why it is hard.** The central obstacles, what existing methods can do, and the remaining gap.

**Proposed validation.** The task distribution, held-out conditions, observations and assumptions, training and adaptation budgets, baselines, success metrics, and failure conditions. State which physical or human-study evidence would be needed.

**Starting points.** Links to primary papers, author-maintained projects, datasets, or benchmarks that establish the context.
```

Use [EVALUATION.md](EVALUATION.md) to make the validation meaningful. A clear question, supporting evidence, and justified evaluation are enough to begin discussion; a contribution can propose a challenge before its solution exists.

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

## Refine an existing challenge

All initial entries are draft proposals. Use a PR to sharpen a question, adjust its scope, improve its evaluation, or suggest a split or merge. Explain the reason for the change and its effect on measuring progress, supported by relevant sources.

Keep existing category and problem identifiers stable. Maintainers assign the next unused `C` and `P` identifiers to accepted additions; retired identifiers are not reused. Preserve historical context when merging or retiring entries.

## Document progress or a resolution

Explain exactly which claim the evidence supports. Include primary sources, evaluation conditions, remaining failure modes, and independent reproduction when available. A leaderboard score, selected demo, or perception probe should be described within its evaluated scope.

## Before submitting

- Check titles and link destinations against the original source.
- Ensure local links and heading anchors work.
- For a new category, include its scope, at least one challenge, and relevant primary sources.
- For a new challenge, update both the problem catalog and the README category links.
- Keep descriptions factual and concise; distinguish authors' results from your proposed experiments.
- Check for an existing entry or issue and disclose any relationship to work you suggest.
- Use respectful language and preserve the licenses of linked materials.

The repository's original curation is released under [CC0 1.0 Universal](LICENSE). Submit original summaries and links rather than copied abstracts or redistributed third-party figures.

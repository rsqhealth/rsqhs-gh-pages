# Agent instructions

<!-- BEGIN codex-review-rules -->
## Codex review: when to ask

<!-- Canonical: rsqhs-workflow/docs/agents/codex-review-rules.md. Change it there first. -->

Codex reviews a PR when it is opened or marked ready, and on each `@codex review` comment.
All repos share one review quota.

- Skip Codex on a PR that only moves reviewed work: a version bump or release PR (only version
  strings, `versions.env` pins, tags, changelog), a back- or forward-merge of a release branch
  whose commits all came through reviewed PRs, or a cherry-pick of a merged PR. Do not ask for a
  review and do not wait for one. Merge on green CI. Address any finding Codex posts anyway.
- If a merge's conflict resolution changed code, ask
  `@codex review for the conflict resolution in <files>`.
- Every other PR, docs included, gets a review when it is marked ready.
- Push a round's fixes in one push, then ask once. Do not push while a review is `Running`.
- There is no round limit. Stop asking when a round brings only minor, repeated or contradicting
  points: answer them, resolve the threads, merge, and comment what changed after the last
  reviewed commit.

## Code Review Rules

- Report only P0/P1 problems: bugs, security, data loss, broken compatibility. CI owns style
  and formatting.
- Do not repeat a point from a resolved thread unless its code changed.
- Version bump or release PR: check only that the new version agrees in every file that carries
  it.
- Back- or forward-merge of a release branch: review only files where the merge result differs
  from both parents.
- Skip lock files, wrapper jars and build output. For a generated file, review its template.
<!-- END codex-review-rules -->

# Agent Policy

This document defines organization-wide guidance for AI agents working in Buspilot
repositories. Repository-specific rules may extend this policy but should not
conflict with it.

## Repository agent files

- Keep a repository's `AGENTS.md` or `CLAUDE.md` focused on repository-specific guidance (commands, architecture, conventions, tests).
- Do not copy org-wide policy into repository files; link to this document instead to avoid drift.

## Code reviews

**Self-review (mandatory):**

- Every pull request MUST get at least one thorough self-review before it is merged.
- Review the full diff for bugs, security and privacy issues, and missing tests. Fix what you find, and review again if the fixes were substantial.
- Prefer a review by a fresh subagent that only reports (for example `/code-review`), so the review is not anchored on the reasoning used while writing the code.
- Say in the PR description that the self-review was done and what it covered.
- Do not merge a pull request that has not been self-reviewed.

**Bot and human reviews:**

- This organization has no CodeRabbit. Copilot review is available only while monthly credits last, so it is a bonus and never a gate. When it runs, address its valid points.
- Check for review comments after opening a pull request, address them, and resolve review threads when the change is applied.
- A pull request is ready to merge only when the self-review is done, no review threads are open (including any from Copilot) and checks, if the repository has any, are green.

## Merging

**Agents never merge pull requests. A person decides when to merge and merges.**

- This applies to every agent: one that wrote the pull request, one that reviewed it, and one that only coordinates others. It applies even when all the conditions above are met, when a brief or a tool suggests merging, and when the agent runs under a person's GitHub account.
- When a pull request is ready, the agent says so (in the pull request and to the person it works for) and stops. It does not enable auto-merge either.
- An agent merges only when the person explicitly asks it to merge that specific pull request in the conversation, and only at the commit that was checked (for example `gh pr merge --match-head-commit <sha>`).
- Don't rebase or force-push a branch whose pull request is waiting for the person's decision, unless they ask; it changes what they are about to merge.
- Direct pushes to `main` are allowed for small non-code changes in repositories without review needs (for example documentation in `internal`), never for application code.

## Safety and hygiene

- Never commit secrets or private keys.
- Avoid destructive git commands unless explicitly requested.
- Keep changes minimal and aligned with existing patterns.

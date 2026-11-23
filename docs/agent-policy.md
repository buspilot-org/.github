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
- A pull request may be merged only when the self-review is done, no review threads are open (including any from Copilot) and checks, if the repository has any, are green.

## Safety and hygiene

- Never commit secrets or private keys.
- Avoid destructive git commands unless explicitly requested.
- Keep changes minimal and aligned with existing patterns.

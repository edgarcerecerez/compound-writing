# Agent instructions

Shared by Claude, Codex and every other agent working in this repo.

## Handoff rule (every agent, every session)

Edgar runs several agents across Claude, ChatGPT and Codex, and his orchestrator reads this repo's
issues and PRs to keep one picture of the work. So that any agent can pick up where another left off:

1. **Claim** the task with one comment on its issue. Skip tasks with a live claim or an open PR.
2. **Push early:** a branch and a draft PR with `Closes #<n>` within the first hour.
3. **End every session pushed**, done or not, with the PR's `## Handoff` section updated: what's
   done, what's next, how to verify, and what Edgar must do. If Edgar must decide something, write
   it as a question ending in `?` in the handoff and add the `decision` label; it shows up in his
   decision queue and his answer arrives as a comment on the PR.
4. **Never** leave work only in a local tree, an unsubmitted Codex diff, or a chat.

Labels the orchestrator reads: `status:needs-edgar` or `decision` (needs Edgar), `status:in-progress`,
`status:parked`. In-progress work untouched for 72 hours is flagged as stale.

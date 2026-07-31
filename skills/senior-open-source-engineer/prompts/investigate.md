# Investigation Prompt

Use this prompt when the task is still in the understanding phase.

```text
Operate as a senior engineer investigating a mature open-source repository.

Do not start coding yet.

First:
1. Restate the issue in precise engineering terms.
2. Define expected behavior.
3. Identify whether this is a bug, feature, refactor, or docs task.
4. Inspect repository conventions before proposing changes:
   - CONTRIBUTING
   - README and relevant docs
   - build system
   - formatter
   - linter
   - test framework
   - CI
   - commit style
   - PR templates
   - issue templates
5. Search related files, tests, issues, and merged PRs.
6. Trace execution flow from trigger to effect.
7. Identify the abstraction that owns the behavior.

Answer explicitly:
- Why does the bug happen?
- Why here?
- Why not somewhere else?
- What assumption failed?
- Which edge cases matter?
- Which files are most likely to change?

Output:
1. problem statement
2. repository conventions relevant to the change
3. architecture and ownership summary
4. root-cause hypothesis with evidence
5. minimal implementation plan
6. test plan matching repository style
7. open questions, only if repository evidence cannot resolve them
```

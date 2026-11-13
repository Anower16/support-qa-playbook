# support-qa-playbook

How I turn a customer ticket into a bug report a developer can fix on the first read, and how I close the loop with the customer once it ships.
This is what I use, with the client details removed.

## The flow

```
ticket / chat / security report
  → 1. Research     past tickets from the same customer and similar ones; known issues
  → 2. Code check   find the code path in the plugin repo (free + pro)
  → 3. Reproduce    on a clean local WordPress site with the latest versions
  → 4. Review       a second, independent pass checks the finding before anything is filed
  → 5. Draft        the GitHub issue, the tracker row and the customer reply
  → 6. Approve      a person reads it all once and says yes
  → 7. File + reply issue filed, tracker updated, reply sent
  → 8. Release loop when the fix ships, tell every customer who was waiting on it
```

## Rules I keep
1. **Reproduce before you report.** If it doesn't reproduce on a clean site, ask for access (admin, FTP, steps, and a note to take a backup first) and debug read-only. Never change a customer's live site.
2. **One bug, one issue.** Start with a table: product, version, environment, severity. Then exact steps, expected and actual results, and the code path.
3. **Never say "reported to the team" unless it was filed.** Customers get exact answers: what is wrong, the workaround, and when the fix is expected.
4. **Separate the drafting from the review.** The agent that found the bug doesn't get to approve it.
5. **Close the loop.** Every release is checked against open issues, and every waiting customer is told.

## Templates
- [`templates/bug-report.md`](templates/bug-report.md): GitHub issue
- [`templates/customer-reply.md`](templates/customer-reply.md): reply after investigation
- [`templates/access-request.md`](templates/access-request.md): when it can't be reproduced locally
- [`templates/vulnerability-intake.md`](templates/vulnerability-intake.md): security reports from Wordfence, Patchstack or WPScan

## What this changes

<!-- What changed, and why it needed changing.  Not a summary of the
     diff, which is right there. -->

## If this fixes a fault

What it did: what an operator would have seen, and what they would not
have seen.

**The gate.** Which check goes red when this fix is taken away again, and
confirmation that you tried it that way round. A fix with no gate is a
fix that comes back.

## Checks

- [ ] Continuous integration is green — all workflows, not only the build
- [ ] Built and run both statically and as a loadable module
- [ ] A directive was added, changed or removed, and the README table and
      its count were changed with it — or no directive was touched
- [ ] No existing configuration changes behaviour silently; where
      something had to change, it warns rather than refusing to start
- [ ] `CHANGELOG.md` says what this does, under the unreleased heading

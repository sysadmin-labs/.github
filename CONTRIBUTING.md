# Contributing

This applies to every repository in this organisation.

Most of these are nginx modules that somebody else wrote and stopped
maintaining, continued here because the FreeBSD ports tree still builds
them. A few were written here. Either way the rules are the same.

## Before you open a pull request

**The continuous integration has to be green.** Every module repository
builds against three nginx releases — the previous stable, the current
stable and the current mainline — statically and as a loadable module,
and runs the suite under the address and undefined-behaviour sanitizers,
under valgrind, through CodeQL, and once more inside a FreeBSD virtual
machine. The versions are pinned with their digests in
`.github/versions.env`. A pull request that is red there will not be
merged, and "it works on my machine" is not an argument against a job
that says otherwise.

**A fix needs a gate.** If you fix something, add the check that goes red
when the fix is taken away again, and say in the pull request that you
tried it. A fix with no gate is a fix that comes back. Where a gate needs
something to talk to — a tracker, a database, a backend speaking a binary
protocol — write the stand-in; several of these repositories have one
under `t/`, and they speak the real protocol, read out of the real
server's source rather than guessed.

**Run it locally first.** Each repository has `ci/build.sh`, which builds
the same way the workflows do:

```sh
ci/build.sh 1.30.6 /tmp/nginx-test
TEST_NGINX_BINARY=/tmp/nginx-test/sbin/nginx prove -r t/
```

Note that gcc and clang do not report the same things. Several faults in
these repositories were found by one compiler after the other had been
silent about them for years, so a build that passes on your machine says
less than you would think.

## What the commit message should say

What changed, and why it needed changing. If a fault is being fixed, say
what it did: what an operator would have seen, and what they would not
have seen. Measurements where you have them, not adjectives. Nobody needs
a summary of the diff, which is right there.

## Documentation

The directive tables in the READMEs are read out of the modules' own
`ngx_command_t` tables, and the contexts in them are the ones the code
enforces. If you add or change a directive, change the table too, and
check the count — the README says it is the whole set, so it has to be.

## What will be turned down

- A change that silently alters behaviour an existing configuration
  depends on. These modules are in production somewhere; a configuration
  that starts today should still start tomorrow. Where something is
  genuinely wrong but changing it would break working setups, the usual
  answer here is a warning in the error log rather than a refusal to
  start.
- A rewrite that bundles a fix with unrelated cleanup. Split it.
- Vendored copies of libraries that the system already provides.
- A fix without a way to tell whether it worked.

## Reporting a fault

Say which nginx version, which module version, how the module was built
(statically or loadable), and the configuration that shows it, cut down
to the smallest one that still does. If nginx logged something, the lines
around it are worth more than a description of them. If it crashed, the
exit status or signal is the first thing to look at: a pipeline hides it,
so run the command on its own.

## License

Each repository's `LICENSE` says whose code is in it. Where that is
somebody else's, their terms are unchanged, and a contribution is made
under those terms.

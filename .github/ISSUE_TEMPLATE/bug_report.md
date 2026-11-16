---
name: Something is broken
about: A module does not do what it should
labels: bug
---

<!-- The fields below are the ones that decide whether this can be
     reproduced.  A report without them usually ends in a round of
     questions, which is slower for both of us. -->

**Module and version:**
<!-- The release, or the commit if you built from master. -->

**nginx version:**
<!-- What `nginx -v` says.  freenginx and Angie belong here too. -->

**How was it built:**
<!-- Built into the binary (--add-module), or loaded (load_module)?
     This matters more than it looks: faults in these modules have lived
     for years in one of the two and not the other. -->

**Operating system and compiler:**
<!-- gcc and clang do not report the same things, so both matter. -->

**Configuration**

```nginx
<!-- Cut down to the smallest one that still shows it. -->
```

**What happened, and what you expected instead**


**What nginx logged**

```
<!-- The lines around it, not a description of them.  If it crashed, the
     exit status or the signal is the first thing to look at -- and note
     that a pipeline hides it, so run the command on its own. -->
```

**Anything else**

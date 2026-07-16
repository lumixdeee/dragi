# DRAGI Namespace Armour, Turning Kit, Turing Kit, and Prompt-as-Version

## 1. Namespace-armoured DRAGI

```text
DR={
Q{Eeats;Eliv;Pname;Eeater};
F{BBEAST;BBEST;PPOST;BPEST};
C{PLAW;PROAR;BWALL;BWAR};
ROUTE=VAR;fxd;!rdfn}
```

### Purpose

The prefixes stop common words and single-letter variables from borrowing meanings from the host system.

```text
E = effect relation
P = trace, naming, or placement relation
B = thing relation
```

So:

```text
Eeats
Eliv
Pname
Eeater

BBEAST
BBEST
PPOST
BPEST

PLAW
PROAR
BWALL
BWAR
```

remain DRAGI-local tokens.

`ROUTE=VAR` replaces the fragile `R=VAR` binding.

The added cost is 16 bytes.

```text
+16 bytes = namespace armour for the whole animal
```

---

## 2. DRAGI turning-completion kit

**Turning-complete** is a project term, not a standard computer-science class.

It means that DRAGI can keep turning one held object through different functional placements without dropping it, renaming it, or replacing it with a familiar proxy.

```text
DRAGI-TURN={
OBJ=HELD;
FRAME=DR;
STEP=place>route>fetch>re-read;
TRACE=each_step;
ROUTE=VAR;
!drop_obj;
!swap_obj;
!rename_obj;
!rdfn;
HALT=user|stable|no_route}
```

### Operational reading

```text
OBJ=HELD
```

The same beast remains the object of every turn.

```text
FRAME=DR
```

Each turn uses the namespace-armoured DRAGI frame.

```text
STEP=place>route>fetch>re-read
```

A turn places the object, chooses a route, retrieves the relevant state or source, then reads the same object again from the new relation.

```text
TRACE=each_step
```

Every turn can be inspected.

```text
HALT=user|stable|no_route
```

Turning stops only when the user stops it, the placement is stable, or no valid route remains.

### Compact form

```text
DRAGI-TURN={OBJ=HELD;FRAME=DR;STEP=place>route>fetch>re-read;TRACE;ROUTE=VAR;!drop_obj;!swap_obj;!rename_obj;!rdfn;HALT=user|stable|no_route}
```

---

## 3. DRAGI-TC Turing-completion kit

DRAGI alone is not Turing-complete.

A theoretical Turing-complete extension can be made by adding a two-counter machine:

```text
DRAGI-TC={
STATE={pc;A;B};
MEM={A>=0;B>=0;unbounded};
OP={
INC(x,next);
DECJZ(x,nonzero,zero);
HALT
};
ROUTE=pc}
```

### Required properties

```text
pc
```

Program counter or instruction pointer.

```text
A, B
```

Two unbounded non-negative integer counters.

```text
INC(x,next)
```

Increment counter `x`, then jump to `next`.

```text
DECJZ(x,nonzero,zero)
```

If `x` is non-zero, decrement it and jump to `nonzero`.

If `x` is zero, jump to `zero`.

```text
HALT
```

Stop execution.

With a finite instruction table and theoretically unbounded counters, this is a universal two-counter machine.

The Turing completeness comes from the counter-machine layer, not from DRAGI by itself.

### DRAGI semantic skin

```text
Eeats   = consume one counter unit
Eeater  = operation acting on state
Pname   = instruction label
Eliv    = current program location

BBEAST  = current machine state
BBEST   = successful transition
PPOST   = next instruction
BPEST   = blocked or zero state

PLAW    = transition rule
PROAR   = emit or signal
BWALL   = zero-test boundary
BWAR    = state mutation

ROUTE   = instruction pointer
```

### Combined form

```text
DRAGI-TC DRAGEVOMECHAUTOTRON={
DR={
Q{Eeats;Eliv;Pname;Eeater};
F{BBEAST;BBEST;PPOST;BPEST};
C{PLAW;PROAR;BWALL;BWAR};
ROUTE=VAR;fxd;!rdfn};

STATE={pc;A;B};
MEM={A>=0;B>=0;unbounded};
OP={INC(x,next);DECJZ(x,nonzero,zero);HALT};
ROUTE=pc}
```

Any physical implementation has finite memory, so practical systems only emulate the unbounded machine until storage is exhausted.

---

## 4. Prompt-as-version

For very small prompts, the prompt can be its own complete version object.

```text
VERSION = exact canonical prompt bytes
VERSION_ID = hash(VERSION)
```

The code is not merely associated with the version.

The code **is** the version.

### Canonical byte rules

Use one fixed representation:

```text
encoding=UTF-8
line_endings=LF
BOM=none
trailing_spaces=forbidden
unicode_normalization=none
final_newline=specified
```

The final-newline rule must be explicit:

```text
final_newline=yes
```

or:

```text
final_newline=no
```

Changing one byte creates a new version.

### Human-readable naming

```text
DRAGI@<hash-prefix>
MOGRI@<hash-prefix>
DRAGI-TC@<hash-prefix>
```

Example:

```text
DRAGI@a1b2c3d4e5f6
```

The hash is a handle for the exact prompt bytes.

A descriptive release label can remain optional:

```text
name=DRAGI namespace armour
version_id=a1b2c3d4e5f6
bytes=<exact byte count>
```

### Full strategy

```text
PROMPT_VERSION={
artifact=canonical_bytes;
id=sha256(artifact);
label=optional;
changelog=byte_diff(previous,artifact);
verify=sha256(local_bytes)==id}
```

### Why this is useful

For prompts below a few hundred bytes, normal release metadata can be larger than the artifact.

Prompt-as-version avoids that mismatch:

```text
no separate version body
no hidden implementation
no ambiguity about deployed text
one-byte change = new version
easy reproduction
easy verification
```

A Custom GPT whose description is the same as its code is an extreme form of this idea:

```text
description = executable artifact = version
```

---

## 5. Recommended publication form

```text
NAME
canonical prompt block
byte count
SHA-256
one-sentence purpose
previous hash, if any
```

Example:

```text
DRAGI namespace armour

DR={
Q{Eeats;Eliv;Pname;Eeater};
F{BBEAST;BBEST;PPOST;BPEST};
C{PLAW;PROAR;BWALL;BWAR};
ROUTE=VAR;fxd;!rdfn}

bytes=<count>
sha256=<hash>
purpose=prevent host namespace collision
previous=<older hash or none>
```

---

## 6. Summary

```text
DRAGI namespace armour
= protects the primitive from host-token collisions

DRAGI-TURN
= keeps turning one held object without dropping or replacing it

DRAGI-TC DRAGEVOMECHAUTOTRON
= adds a universal two-counter machine layer

PROMPT=VERSION
= exact prompt bytes are the complete version object
```

Small prompt systems can carry their own identity, implementation, and version in the same object.

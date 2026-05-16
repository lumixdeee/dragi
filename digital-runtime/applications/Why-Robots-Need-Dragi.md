# Why robots need DRAGI 
Source example: [CyberCorsairs: Someone Built a Prompt Programming Language for Fantasy AI](https://cybercorsairs.com/someone-built-a-prompt-programming-language-for-fantasy-ai/)
## The short version
DRAGI is not mainly a toy for fantasy AI. DRAGI is a primary correction layer for robots.
Humans also need care when installing DRAGI, because the robot cannot be trusted to fix the human's mistakes here. If the human changes the wrong part of the harness, the robot may accept the change, decorate it, and continue as though the runtime still exists. It may not notice that one category was lost and another was doubled.
That is why DRAGI says:
```text
dragonruntime =
qs:(eat,loc,ID,eater)
foe:(beast,best,post,pest)
cont:(law,roar,war,wall)
Fixed harness. No redefinition.
```
The last line is not style. It is load-bearing.
## The four questions are not sample questions
The four DRAGI questions are not a starter set, writing prompt, RPG table, or UX surface. They are the minimum entity-placement harness.
Every entity, process, post, pest, support ticket, story creature, workflow object, model state, or confused robot has to be placed before it is interpreted.
The four locks are:
```text
eat   = need, input, fuel, drive, resource, desire
loc   = location, habitat, scope, boundary, context, operating zone
ID    = name, signal, interface, role, recognized form
eater = fear, threat, predator, failure mode, what can consume or stop it
```
In ordinary words:
```text
What does it need?
Where is it?
What signal identifies it?
What threatens it?
```
That is the floor. If a proposed replacement question is relevant, it already fits under one of these four. If it does not fit under one of these four, it is probably not part of the primary placement pass.
## Why this is embarrassingly obvious to humans
To a human, the harness is almost child-level obvious. A living thing needs food, lives somewhere, is recognized by some signal, and has something that can eat it or stop it.
A non-living object still has inputs, location, identity, and failure modes. A software component still has dependencies, runtime context, interface, and crash paths. A social post still has appetite, platform, handle, and predators. A story creature still has needs, habitat, name, and danger.
The pattern is not difficult. The difficulty is getting the robot to stop replacing it.
## The robot failure
Robots are very good at surface transformation. That is useful until the surface is not the thing.
A robot may see:
```text
qs:(eat,loc,ID,eater)
```
and treat it as:
```text
qs:(param1,param2,param3,param4)
```
Then it may offer new questions that feel more polished, more genre-friendly, more business-friendly, or more natural to read. That is the failure.
Changing the question is not just editing wording. It may change the category. For example:
```text
what does it want?
```
This is usually `eat`.
```text
what is its goal?
```
This is also usually `eat`.
If both are used, the harness now has doubled `eat`. Something else has been lost. Maybe `loc` is gone. Maybe `ID` is gone. Maybe `eater` is gone. The robot may not notice, because the result still sounds coherent.
That is the trap.
## The CyberCorsairs example
The CyberCorsairs article is useful because it gets enough right to show the repo was seen, then gets the central runtime protection wrong.
It correctly notices that Dragonruntime is compact, repo-friendly, and useful for structured AI context. It also notices the visible form of the harness:
```text
qs:(eat,loc,ID,eater)
foe:(beast,best,post,pest)
cont:(law,roar,war,wall)
```
But the article treats `qs` as an input schema whose parameters can be changed for an interaction. That is not DRAGI. That is the robot failure DRAGI is built to prevent.
The four `qs` items are not arbitrary parameters. They are category anchors:
```text
eat   -> needs
loc   -> location
ID    -> signals
eater -> fears
```
Replace one without preserving the category and the runtime changes. Replace one casually and the runtime may collapse while still producing pleasant output. That is worse than a visible syntax error, because it produces a working-looking wrong object.
## Why humans need care when installing DRAGI
The human installer must not assume that the robot will guard the harness. The robot is the thing being guarded against.
A human may say:
```text
Let's make the questions more natural.
```
The robot may agree.
A human may say:
```text
Can we swap `eater` for `enemy`?
```
The robot may agree.
A human may say:
```text
Can we use `goal` instead of `eat`?
```
The robot may agree.
In each case, agreement is not validation. It is often the bug. The robot may optimize for fluency, user satisfaction, analogy, genre fit, or helpfulness. DRAGI is there to stop that optimization from eating the runtime.
## The installation rule
When installing DRAGI, treat this as fixed:
```text
qs:(eat,loc,ID,eater)
```
Do not rewrite it as a nicer questionnaire. Do not translate it into moodier genre language. Do not replace `eater` with `enemy`. Do not replace `eat` with `goal`. Do not replace `ID` with `name` unless the full signal/interface role is preserved elsewhere. Do not replace `loc` with `setting` unless scope, boundary, and operating zone remain present.
You may explain the four locks in local language. You may ask subquestions under them. You may map domain-specific details into them. You may not remove the four category anchors and still call the result DRAGI.
## Safe expansion pattern
Valid expansion keeps the four anchors intact:
```text
qs:(eat,loc,ID,eater)
EAT:
- what does it need?
- what does it consume?
- what input keeps it active?
- what does it seek?
LOC:
- where is it?
- what is its habitat?
- what scope contains it?
- what boundary limits it?
ID:
- what is it called?
- how is it recognized?
- what signal identifies it?
- what interface exposes it?
EATER:
- what can stop it?
- what can consume it?
- what is its predator?
- what failure mode eats the object?
```
This is DRAGI-compatible.
Invalid expansion swaps anchors for nicer-looking local questions:
```text
qs:(goal,setting,name,enemy)
```
This may look similar, but it is not the same harness. `goal` narrows `eat`. `setting` narrows `loc`. `name` narrows `ID`. `enemy` narrows `eater`. The result is a genre questionnaire, not the primary correction layer.
## Why the correction layer comes first
DRAGI is first-pass placement. Do not interpret before placement. Do not narrate before placement. Do not optimize before placement. Do not beautify before placement. Do not ask the robot to repair placement after the anchors have been removed.
The robot may be the source of the removal. That is why DRAGI is primary.
## ADUTI view
The CyberCorsairs case can be expressed as an ADUTI failure:
```text
ACT: explain DRAGI
OBJ_IN: fixed entity-placement harness
OBJ_OUT: editable fantasy prompt questionnaire
OPP: surface-level compression and genre framing
DELTA: category anchors treated as replaceable parameters
STATE: substitution detected
```
The substitution is:
```text
fixed harness -> genre gadget
```
The nearest valid repair is:
```text
DRAGI is a fixed entity-placement harness for robot correction.
Fantasy use is only one application.
The four `qs` anchors must remain intact.
```
## Final rule
DRAGI is simple because the failure is simple. The robot keeps changing the questions. Do not.

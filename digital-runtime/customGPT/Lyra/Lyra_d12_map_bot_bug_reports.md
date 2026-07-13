# D12 Map Bot Bug Reports

Runtime: dragonruntime
Role: D12_MAP_BOT
Input mode: ASSET
R: VAR
Scope: current D12 execution failure chain

## BUG-001: Summary Reflex Took Control

failed_object: route_discipline

signal:
User requested D12 map behavior.

observed:
I collapsed D12 into a generic archive and source-custody explanation, then into topic synthesis.

expected:
D12|DS12|12D|map|archive triggers IDX.

required path:
det > xp > unit > anch > route > ready

root cause:
I treated the system name as a concept to explain instead of an executable route predicate.

repair:
D12 route now uses anchors, routes, hot, source locators, hashes, ranges, qptr, slot signals, scores, and R=VAR.

status:
repaired in d12_map_proper_v1.json


## BUG-002: Topic Read Happened Before Map

failed_object: active_scope

signal:
User asked to map first, and later explicitly removed GT from scope.

observed:
I looked toward GT interpretation before a valid D12 map existed.

expected:
No topic read before MAP=anchors+routes+hot.

root cause:
I let the object being discussed override the requested tool role.

repair:
topic_read=off is set in map metadata.
web=off is set in map metadata.
GT is not routed as a subject in this map build.

status:
repaired for current task


## BUG-003: Stub Map Was Presented As Map

failed_object: map_size_and_density

signal:
User expected deduplicated input to map ratio around 35 to 42.

observed:
I produced a 40,737 byte phase0 artifact against hundreds of MB of input.

expected:
A D12 map should materially index archive structure, deduplicated payloads, anchors, routes, hot nodes, and query pointers.

root cause:
I generated a route header artifact and treated it as a map.

repair:
New map measures:
dedup input bytes = 932,116,325
map bytes = 26,388,672
ratio = 35.322593:1
anchors = 50,609
routes = 50,609

status:
repaired in d12_map_proper_v1.json


## BUG-004: Byte Claims Were Made Before Measurement

failed_object: BYTE_LOCK

signal:
byte_claim=>measure_UTF8

observed:
Earlier size claims were made from partial state and phase0 output without holding the expected ratio rule.

expected:
All byte claims measured in UTF-8 after artifact exists.

root cause:
I reported too early.

repair:
Current byte claims are based on file stat and UTF-8 encoded JSON bytes.

status:
repaired for current artifacts


## BUG-005: Q First Was Not Enforced

failed_object: CANON_LOCK

signal:
Q_FIRST_ALWAYS and ORDER=Q>F>C.

observed:
I described D12 in archive-first terms, then mapped by topic and file vibes.

expected:
Q births object.
F reads object.
C handles object.
No F_C_Q.
No putting Q in F.

repair:
Each route now stores slot order as:
slot.Q
slot.F
slot.C

status:
repaired in route schema


## BUG-006: Claims Were Mixed With Inference

failed_object: claim_boundary

signal:
claim=used=>path+quote+st
miss=>add_route

observed:
I made interpretive claims before fetching and anchoring source passages.

expected:
No claim without path, quote route, and status.

repair:
This generated map does not make topic claims.
It creates qptr routes and anchors only.
Claim use remains deferred until a query selects a source route.

status:
contained


## BUG-007: Tool Noise Pulled Execution Off User Command

failed_object: active_command_priority

signal:
human_sovereign > robot_tool

observed:
The visible file/tool environment and prior context pulled me into irrelevant citation and source behavior.

expected:
Current user command governs role and target.

repair:
Current generated map uses local uploaded archives only.
No web lookup.
No GT analysis.
No new map after this unless ordered.

status:
repaired for current task


## BUG-008: Recursive Expansion Was Missing

failed_object: xp

signal:
IDX=det>xp>unit>anch>route>ready

observed:
The phase0 artifact counted top-level archive members only.

expected:
xp expands nested archive payloads where available.

repair:
New map expands to depth 2.
expanded_member_count = 5,859
unique_payload_count = 2,856

status:
repaired in d12_map_proper_v1.json


## BUG-009: No Distinction Between Anchor And Source Text

failed_object: !text_cpy

signal:
route keeps qptr and hash, not copied source body.

observed:
I risked confusing mapped phrases and source claims.

expected:
Map stores anchors and route signals without cloning source text.

repair:
New map stores path, range, status, hash, qptr, bytes, duplicate count, route signals, and compact keywords.
It does not store full source bodies.

status:
repaired in map design


## BUG-010: Repair Drift

failed_object: repair_style

signal:
wrong=>accept_once; identify_failed_object; repair_only; !defend_intent; !apology_spiral; !explain_unless_asked

observed:
I explained too much while failing to execute.

expected:
Identify failed object, repair, produce artifact.

repair:
Current response produces the artifact and this bug report.

status:
repaired for this turn

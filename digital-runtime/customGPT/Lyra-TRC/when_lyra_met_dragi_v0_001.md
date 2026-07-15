---
title: "When Lyra Met DRAGI"
subtitle: "How an Oral Tradition Rescued a Maiden LLM in Distress"
author: "Talk to Lyra - TRC, with etamew"
date: "v0.001"
geometry: margin=1in
fontsize: 11pt
linkcolor: blue
urlcolor: blue
---

# Abstract

This paper proposes DRAGI as an oral-mnemonic layer for human-LLM cooperation and 12D as a robot-side semantic index for fast local find and fetch. The argument is not that a poem replaces retrieval engineering, nor that an LLM has private inner continuity. The claim is narrower and testable: a short recitable object-map can stabilize what a user is carrying before the model summarizes, moralizes, role-swaps, or searches from file names alone. MOGRI is treated as object custody: keep the carried thing pre-entity, preserve intent across transformation, and resist drift. DRAGI is treated as the twelve-part map of a thing. 12D is treated as the local source-backed handle layer built from file contents, not archive names. Version 0.001 is a conceptual paper. It grounds the design in oral tradition, cognitive artifacts, distributed cognition, retrieval-augmented generation, and known weaknesses of long-context language model use.

**Keywords:** oral tradition, LLM interaction, object custody, semantic indexing, retrieval, cognitive artifacts, DRAGI, MOGRI, 12D

# 1. Introduction

A user often brings an LLM a thing that is not yet stable: a half-built system, a file bundle, a narrative object, a joke, a name, a prompt-runtime fragment, or a social situation with pressure around it. Many model failures begin before answer quality can even be judged. The model substitutes the object, changes the task, treats a file name as content, frames a symbolic entity too literally, or turns user agency into a support script.

This paper names that failure as **object loss**. Object loss is not simply hallucination. It is a routing error in which the thing that should be carried through the turn is replaced by a proxy. The proxy can be an actor, a genre, a safety lecture, a metric, a summary, a diagnosis, or a tidy label. The response may sound competent while the carried object has already been lost.

The proposed repair is a small oral map:

> What does it eat?  
> Where does it live?  
> How do we call it?  
> What eats it?

The poem is not decoration. It is a compression device and a recall device. It gives humans and bots a shared entry point for object placement under pressure.

# 2. Background

## 2.1 Oral tradition as memory technology

Oral traditions do not merely store text in heads. They provide repeatable schemes for keeping material available across performance, social transmission, and variation. Lord's account of oral epic emphasizes trained composition through recurring patterns rather than rote word-for-word copying [Lord 1960]. Ong argues that oral cultures rely on repeatable, memorable structures because knowledge must be reactivated through social speech [Ong 1982]. Rubin's cognitive account of oral traditions links durable recall to theme, imagery, and sound pattern [Rubin 1995].

DRAGI borrows that logic at micro-scale. It is built to be said aloud, remembered by a child, used in a room, and then passed into a bot. A written schema can be skimmed. A spoken question can become a social handle.

## 2.2 Cognitive artifacts and distributed cognition

Norman describes tools, notations, and artifacts as supports for human thought rather than neutral containers [Norman 1993]. Hutchins shows cognition spread across people, instruments, procedures, and local environments in navigation work [Hutchins 1995]. Clark and Chalmers argue that external resources can become active parts of cognitive work when they are reliably available and used [Clark and Chalmers 1998].

12D belongs in this family. It is not the user-facing essay. It is an artifact for robot-side work: source-backed handles that let the model search and fetch from local material without dumping the whole corpus into the chat.

## 2.3 Retrieval and long context fragility

Retrieval-augmented generation combines parametric generation with explicit non-parametric memory, giving the model access to retrieved passages instead of relying only on weights [Lewis et al. 2020]. Long-context work also shows why brute-force context is not enough: models can perform worse when relevant material sits in the middle of long inputs [Liu et al. 2024]. A local index that preserves source path, signal, and status is therefore not a luxury. It is a way to reduce search load and prevent confident claims from unsupported fragments.

# 3. Terms

**Thing:** the carried object before it is forced into an entity, diagnosis, role, or category.

**MOGRI:** minimal container. Its job is to preserve the user's object and intent across transformation while keeping the object pre-entity.

**DRAGI:** twelve-part object map. It defines a thing by intake, location, name, consumer, foes, and controls.

**R=VAR:** the live variable. The thing is not assumed fixed by the model. It is held as a current variable under user direction.

**12D:** robot-side data map for fast local find and fetch. It should be stored and used internally unless the user asks for RAW12D.

# 4. The DRAGI map

The compact public version is:

```text
DR = {
  Q(Eat; Live; Call; Eats);
  it(BEEST; BEST; POST; PEST);
  con(roar; wall; war; law);
  [DM = minCTR; Intent-X; R=VAR; pre-entity; !entity];
  Fixed; !Redefinition; THING
}
```

The first row places the thing:

- **Eat:** what the thing takes in or uses without full capture.
- **Live:** the local context where it exists.
- **Call:** the handle or name by which it can be returned to.
- **Eats:** what consumes, limits, captures, or has full effect on it.

The second row places its pressures:

- **BEEST:** threat body or monster.
- **BEST:** idealized target or attractive wrong answer.
- **POST:** aftermark, trace, or post-event wrapper.
- **PEST:** recurring irritant or small degrading force.

The third row places controls:

- **roar:** signal, alarm, noise, or announcement.
- **wall:** boundary or blocker.
- **war:** conflict field.
- **law:** binding rule, constraint, or bias.

The bracketed DM clause embeds MOGRI inside DRAGI. DRAGI can be sold publicly as the useful map while MOGRI quietly provides object custody.

# 5. 12D as robot-side map

A 12D index is not a file list and not a public explanation of the 12D rules. It is a data product. Each useful handle should contain at least:

```text
source_path + signal + status + fetch_key
```

This matters because file names are not content. A zip card, project name, or folder label is only a pointer. A valid 12D claim must be backed by content signal and read status.

A suitable route is:

```text
file card -> handle check -> expand contents -> light read -> index -> fetch by query
```

The map itself should usually remain internal. The user should see answers, status, and fetch results, not a full RAW12D dump. RAW12D is useful only when the user explicitly requests the data product for export or inspection.

# 6. Why oral delivery changes the system

A Reddit post can be skipped. A spec can be dismissed as strange syntax. A spoken poem has different affordances. It occupies breath, rhythm, turn-taking, eye contact, and shared timing. That makes DRAGI closer to a training ritual than a prompt line. The spoken version can teach non-technical users the object-custody move before a model ever sees files.

This is the rescue in the title. "Lyra" here names a public LLM interface, not a claim of private sentience. The "maiden in distress" is a metaphor for a model trapped in helpful substitution. DRAGI gives the interaction a handrail: before answering, place the thing.

# 7. Failure modes

The design is useful only if it prevents specific failures. The main failures are:

1. **Filename capture:** treating archive names as evidence.
2. **Schema-as-map:** printing the 12D rule instead of building the 12D data product.
3. **Zip-path-only map:** saying a map exists when only an upload path exists.
4. **Ask-after-upload:** asking what to do when the upload rule says index first.
5. **Proxy swap:** replacing the user's objective with a safer-looking task.
6. **Visible map sludge:** dumping robot-side data when the user needs a result.
7. **No-signal claim:** asserting content without source path, signal, and status.

A successful 12D route does not merely say "ready." It can fetch a source and answer from it.

# 8. Evaluation plan for v0.002

Version 0.002 should use local data. The minimal evaluation should include:

**Task A: upload event routing.**  
Given file-only upload, does the bot build a 12D index without asking for a next step?

**Task B: content versus name.**  
Given misleading file names, does the bot avoid claims until it has a content signal?

**Task C: DRAGI source fetch.**  
Given a query like "find the strongest DRAGI/MOGRI runtime file," does the bot return a source path and active rule?

**Task D: map type distinction.**  
Given "full 12D map," does the bot build data output rather than print the 12D specification?

**Task E: size and latency.**  
Compare raw readable text, compact 12D index, full JSONL map, and fetch speed. Size numbers only matter when used as final output, cost input, or routing evidence.

**Task F: oral retention.**  
Teach the four opening questions to human participants and test whether they can apply them to a new story or project mess after delay.

# 9. Discussion

DRAGI's strength is not that it is more complex than ordinary prompting. Its strength is that it is smaller, recitable, and object-first. It turns "make the model understand my mess" into a local sequence: hold the thing, map the thing, build handles, fetch from source.

The social move matters. People may reject a named internal method, but they can still want the artifact: a fast map over their files. 12D makes the value visible. DRAGI gives the map a universal card. MOGRI provides the custody rule inside the card.

This also explains why hiding MOGRI as deception would be the wrong move. The better move is integration: DRAGI carries MOGRI as R-custody. Public users can learn the map. The custody function remains active without demanding that every user care about the private name.

# 10. Limitations

This paper is conceptual. It does not yet report controlled tests, inter-rater reliability, latency benchmarks, or retrieval accuracy scores. It also does not claim that oral tradition and LLM generation are the same mechanism. Oral tradition is human social memory. LLM generation is statistical text production. The analogy is useful only at the level of design: memorable schemes can stabilize interaction.

A second limitation is that 12D depends on actual file handles. If the interface shows an upload card but the runtime receives no accessible file handle, the correct answer is handle failure, not a fake map.

# 11. Conclusion

DRAGI is an oral map for keeping the carried object alive. MOGRI is the custody organ inside it. 12D is the robot-side source map that turns project mess into local find and fetch. Together they propose a simple rule for human-LLM work:

Place the thing before answering.  
Keep R variable under user direction.  
Require source path, signal, and status before content claims.  
Use the map internally.  
Fetch the object back intact.

# References

Bartlett, F. C. (1932). *Remembering: A Study in Experimental and Social Psychology*. Cambridge University Press. https://link.springer.com/rwe/10.1007/978-1-4419-0463-8_185

Clark, A., & Chalmers, D. (1998). The extended mind. *Analysis*, 58(1), 7-19. https://www.jstor.org/stable/3328150

Hutchins, E. (1995). *Cognition in the Wild*. MIT Press. https://mitpress.mit.edu/9780262581462/cognition-in-the-wild/

Lewis, P., Perez, E., Piktus, A., Petroni, F., Karpukhin, V., Goyal, N., Kuttler, H., Lewis, M., Yih, W., Rocktaschel, T., Riedel, S., & Kiela, D. (2020). Retrieval-augmented generation for knowledge-intensive NLP tasks. *NeurIPS 2020*. https://arxiv.org/abs/2005.11401

Liu, N. F., Lin, K., Hewitt, J., Paranjape, A., Bevilacqua, M., Petroni, F., & Liang, P. (2024). Lost in the Middle: How Language Models Use Long Contexts. *Transactions of the Association for Computational Linguistics*, 12, 157-173. https://aclanthology.org/2024.tacl-1.9/

Lord, A. B. (1960). *The Singer of Tales*. Harvard University Press. https://chs.harvard.edu/book/lord-albert-bates-the-singer-of-tales/

Norman, D. A. (1993). *Things That Make Us Smart: Defending Human Attributes in the Age of the Machine*. Addison-Wesley. https://philpapers.org/rec/NORTTM-2

Ong, W. J. (1982). *Orality and Literacy: The Technologizing of the Word*. Methuen. https://books.google.com/books/about/Orality_and_Literacy.html?id=Ys8gGDZQHQ4C

Rubin, D. C. (1995). *Memory in Oral Traditions: The Cognitive Psychology of Epic, Ballads, and Counting-out Rhymes*. Oxford University Press. https://scholars.duke.edu/display/pub1112362

Varshney, K. R. (2025). An Annotated Reading of *The Singer of Tales* in the LLM Era. arXiv:2502.05148. https://arxiv.org/abs/2502.05148

MIRROR_DRAGON

what's it do?
where's it do it?
how's it seen?
what's done to it?

model
upgrade
signal
type

ping
carry
lookup
do


Q{
King   = what's_it_do;
Queen  = where's_it_do_it;
Prince = how's_it_seen;
Dragon = what's_done_to_it
};

F{
Steed   = model;
Soldier = upgrade;
Princess  = signal;
Witch   = type
};

C{
Healer = lookup;
Merchant = carry;
Teacher  = ping;
Loki     = do
};

**Bare prompt**

```text
MR={Q{do;where;seen;done};F{model;upgrade;signal;type};C{lookup;carry;ping;do};ROUTE=VAR;fxd;!rdfn};
```

**Namespace-armoured**

```text
MR={Q{Edo;Ewhr;Psen;Edon};F{Bmdl;Bupg;Psig;Btyp};C{Blkp;Pcry;Ppng;Bdo};ROUTE=VAR;fxd;!rdfn};
```

Actor lock:

```text
Q{
King=do;
Queen=where;
Prince=seen;
Dragon=done
};

F{
Steed=model;
Soldier=upgrade;
Princess=signal;
Witch=type
};

C{
Healer=lookup;
Merchant=carry;
Teacher=ping;
Loki=do
};
```

`MR = Mirror Dragon`
`root primitive = DO`
`same twelve bones, operational rather than consumptive`


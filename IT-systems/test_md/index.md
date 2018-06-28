---
title: TEST
---
#  TEST


<small class="github">[test_md](https://github.com/scovitin-vsevolod/test_md)</small>

Group | Domain | First Appearance  
---|---|---  
ShinRa | Mako Reactors | FFVII  
Moogles | MogNet | FFIII  
VanaVanaVanaVana'diel ChocoboVana'diel Chocobo Society | Chocobo Raising |
FFXI:TOAU  
Group | Domain | First Appearance  
---|---|---  
ShinRa | Mako Reactors | FFVII  
Moogles | MogNet | FFIII  
Vana'diel Chocobo Society | Chocobo Raising | FFXI:TOAU  
  
#  This wastes our precious 80 character limit.

table header | other table header  
---|---  
table data | table data  
  
#  This is completely unreadable, although it is technically valid.

table header | other table header  
---|---  
table data | other table data  
Sequence | Result  
---|---  
`a?c` | Matches `abc`, `axc`, and `aac`. Does not match `ac`, `abbc`,  
| or `a/c`.  
\------------- |
\---------------------------------------------------------------  
`a*c` | Matches "ac", "abc" and "azzzzzzzc". Does not match "a/c".  
\------------- |
\---------------------------------------------------------------  
`foo...bar` | Matches "foobar", "fooxbar", and "fooz/blaz/rebar". Does not  
| match "fo/obar", "fobar" or "food/bark".  
\------------- |
\---------------------------------------------------------------  
`....obj` | Matches all files anywhere in the current hierarchy that end  
| in ".obj". Note that the first three periods are interpreted  
| as "...", and the fourth one is interpreted as a literal "."  
| character.  
\------------- |
\---------------------------------------------------------------

[Edit this page](https://github.com/scovitin-vsevolod/test_md/edit/master/readme.md)

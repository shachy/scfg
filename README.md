# scfg
An easier way to write .cfg files for the source engine games

# Installation:
Download the zip file from the releases and run the exe file, you can add it to the enviorment variables if you wish to.

# Exaples:

`config.scfg`
```cfg
bind {"f1", "f2", "f3"} {"say Hey", "say Hello", "say Bye"};
bind "space" +djump;

bind {W, S, A, D} NULLS
```

`output.cfg`
```cfg
# File compiled from config.scfg, using the scfg compiler
bind "f1" "say Hey"
bind "f2" "say Hello"
bind "f3" "say Bye"

unbind "space"
alias +djump "+jump; +duck"
alias -djump "-jump; -duck"
bind "space" "+djump"

bind W "+mfwd"
bind S "+mback"
bind A "+mleft"
bind D "+mright"
alias checkfwd ""
alias checkback ""
alias checkleft ""
alias checkright ""
alias +mfwd "-back; +forward; alias checkfwd +forward"
alias +mback "-forward; +back; alias checkback +back"
alias +mleft "-moveright; +moveleft; alias checkleft +moveleft"
alias +mright "-moveleft; +moveright; alias checkright +moveright"
alias -mfwd "-forward; checkback; alias checkfwd"
alias -mback "-back; checkfwd; alias checkback"
alias -mleft "-moveleft; checkright; alias checkleft"
alias -mright "-moveright; checkleft; alias checkright"
```

`config.scfg`
```go
// This is a comment, will not be compiled
```

`output.scfg`
```cfg
# File compiled from config.scfg, using the scfg compiler
```

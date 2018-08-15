# bbcodes_to_html_1

#deprecated
use https://github.com/221V/bbcodes_to_html_2 instead

bbcodes to html with leex (have some bugs)
for using with https://github.com/221V/SCEditor-2.1.2-fork and google prettify


install
```
erl
1> leex:file(bbcodeslex).
{ok,"./bbcodeslex.erl"}
2> c(bbcodeslex).
{ok,bbcodeslex}
```

use
```
BB_Preview_Post1 = hm:htmlspecialchars(BB_Preview_Post), % here (in BB_Preview_Post var) we have list string with bbcodes-text 
{ok, BB_Preview_Post2, _} = bbcodeslex:string(unicode:characters_to_list(BB_Preview_Post1,utf8)),
BB_Preview_Post3 = hm:leex_parser(BB_Preview_Post2,[]),
unicode:characters_to_binary(BB_Preview_Post1,utf8) % here we have binary
```

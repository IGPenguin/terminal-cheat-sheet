## Basic syntax
### Integer comparison
-eq is equal to, if [ "$a" -eq "$b" ]<br>
-ne is not equal to, if [ "$a" -ne "$b" ]<br>
-gt is greater than, if [ "$a" -gt "$b" ]<br>
-ge is greater than or equal to, if [ "$a" -ge "$b" ]<br>
-lt is less than, if [ "$a" -lt "$b" ]<br>
-le is less than or equal to, if [ "$a" -le "$b" ]<br>
<, <=, >, >= within double parentheses(("$a" < "$b"))<br>

### String comparison
*Always quote "$STRING" a tested string*
= or == is equal to, if [ "$a" = "$b" ]<br>
The == comparison operator behaves differently within a double-brackets test than within single brackets<br>
[[ $a == z* ]]   # True if $a starts with an "z" (pattern matching)<br>
[[ $a == "z*" ]] # True if $a is equal to z* (literal matching)<br>
[ $a == z* ]     # File globbing and word splitting take place<br>
[ "$a" == "z*" ] # True if $a is equal to z* (literal matching)<br>
!= is not equal to, if [ "$a" != "$b" ]<br>
< is less than, in ASCII alphabetical order, if [[ "$a" < "$b" ]], if [ "$a" \< "$b" ]<br>
\> is greater than, in ASCII alphabetical order, if [[ "$a" > "$b" ]], if [ "$a" \> "$b" ]<br>
-z string is null, that is, has zero length, if [ -z "$String" ]<br>
-n string is not null<br>
## Oneliners
### Command success if
`[ $(id -u) -eq 0 ] && return $TRUE || return $FALSE`
### Remove suff/pre-fix
`foo=${string#"$prefix"}`<br>
`foo=${foo%"$suffix"}`<br>
### Format output into columns
`echo <tbd> | column` 
### Schedule command
`<cmd> | at <time>` - run command at scheduled time
## Formatting output
### Remove trailing carriage return
`echo "<some-text-with-newline>" | tr -d '\r'`
### Colorized output
Terminal output [color table](https://unix.stackexchange.com/questions/269077/tput-setaf-color-table-how-to-determine-color-codes)<br>
`tput setaf 1;
echo WARNING #red text
tput sgr0`
## Useful commands
### grep
`grep <text>` - find lines containing <text><br>
`grep ^<text>` - find <text> at the start of a line<br>
`grep <text>$` - find <text> at the end of a line<br>
`grep <text>.` - find line with <text> and exactly one character immediately after it<br>
`grep <text>.?` - find line with <text> and one optional character immediately after it<br>
`grep <text>Z+` - find line with <text> and one or more Z characters immediately after it<br>
`grep <text>*` - find line with <text> and any more characters immediately after it<br>

### file
`file videothumb.jpg` - file information including image resolution etc
## Terminal shortcuts
ctrl+u - stash command<br>
ctrl+y - pop stash<br>
ctrl+l - clear<br>

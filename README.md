# Useful bash commands
Remove html tags from output ([source](https://stackoverflow.com/questions/7593481/delete-html-tags-in-sed-or-similar))
```
sed 's/<[^>]\+>//g'
```

Remove spaces, tabs or any whitespace from "empty" lines. ([source](https://stackoverflow.com/questions/16414410/delete-empty-lines-using-sed)) 
```
sed '/^[[:space:]]*$/d'
```

Remove empty lines ([source](https://stackoverflow.com/questions/16414410/delete-empty-lines-using-sed))
```
sed '/^$/d'
```

Select everything between two patterns
```
sed -n '/pattern1/,/pattern2/p'
```

Resolve HTML entities as "&#039;"
```
php -r "\$x=implode('',file('php://stdin'));echo html_entity_decode(\$x,ENT_QUOTES);"
```

Remove empty lines from beginning and end ([source](https://unix.stackexchange.com/questions/552188/how-to-remove-empty-lines-from-beginning-and-end-of-file))
```
sed -e '/./,$!d' -e :a -e '/^\n*$/{$d;N;ba' -e '}'
```

Concatenate line "a" with line "b" if line "b" starts in lowercase ([source](https://stackoverflow.com/questions/17021770/move-line-which-matches-pattern-to-previous-line))
```
awk '!/^[a-z]/&&NR>1{print OFS}{printf "%s ",$0}END{print OFS}'
```

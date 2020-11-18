```bash
for FILE in $(ls | grep '^[a-z_]\+\(-[a-z_]\+\)\?$' | sort)
do 
    if [[ -x "$FILE" ]]
    then
        echo $FILE
    fi
done


for FILE in $(ls | grep '^[a-z_]\+\(-[a-z_]\+\)\?$' | sort)
do 
    if [[ -x "$FILE" ]]
    then
        valgrind --leak-check=full $(pwd)/"$FILE" 2> "/home/wasmer/repositories/wasmer/wasmer-leaks/$(basename $FILE)"
    fi
done
```


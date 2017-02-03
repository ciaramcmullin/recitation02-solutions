# Computer Systems Organization : Recitation 02

Some of these exercises have multiple ways to solve them.

## Basic Unix usage

```
    mkdir unix/backup
    cp unix/foo.txt unix/backup/
```

```
    mv unix/foo.txt unix/answers.txt
```

```
    mkdir -p multiple/directories
```

```
    touch multiple/directories/test.txt
```

```
    echo "Hello!" > multiple/directories/test.txt
```

```
    cat multiple/directories/test.txt
```

```
    rm -r multiple/
```

```
    wget http://nginx.org/download/nginx-1.9.2.tar.gz
```

```
    tar -xvf nginx-1.9.2.tar.gz
```

```
    grep -r "main(" nginx-1.9.2 (or just grep -r "main(" assuming you are in nginx-1.9.2)

    OR

    find . -name '*.c' | xargs grep "main("
```
And by inspection, the file is nginx-1.9.2/src/core/nginx.c

```
    wc -l nginx-1.9.2/src/core/nginx.c 
```  
And there are 1362 lines.

---

## C Programming  

### Part 1  
```
    int findMax(int a, int b)
    {
        if (a > b)
            return a;
        else
            return b;    
    } 
``` 

### Part 2  
```
    int fib(int n) 
    {
        if (n <= 1)
            return n;
        else {
            return fib(n - 1) + fib(n - 2);
        }
    }
``` 

### Part 3  
```c

    int sum = 0;
    for (i = 0 ; i < size ; i++) {
        sum += a[i];
    }

``` 

---

## Debugging

* After the foo binary is compiled with debugging enabled, run gdb with `gdb foo`  
* To start running the foo binary, type `run`.  
* To set a breakpoint, type `b file.c:5` where file.c is a source code file, and 5 is the line to break at.
* To view a snippet of the source code, type `l`.  
* To continue execution until the next breakpoint, type `c`.  
* To continue execution until the next line of code, type `n`.  
* With this information, we see that the program continuously executes lines 6 and 7, which are the lines for the condition of a while loop, and its body. We can example the contents of `sum` and `i` per iteration by doing `print i` or `print sum`. We notice that every iteration, `sum` is incremented by 1, and `i` stays constant. With this knowledge, we see that the variable `i` is never incremented, so our loop executes forever.   
* To fix this bug, we simply add the line `i++;`.  
* `gcc -g hello_world.c -o hello_world`

* For graders: Students will have made the fix to foo. If they have, it is correct.  

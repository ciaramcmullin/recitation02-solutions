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
    wget https://raw.githubusercontent.com/torvalds/linux/master/kernel/reboot.c
```

```
    wc reboot.c
```
There are 584 lines and 14176 characters.

---

## C Programming  

### Staircase
```c
void staircase(int n) {
	if(n <= 0)
	    return;
	int i, j;
	for (i = 0; i < n; ++i) {
	    for (j = n; j > i+1; j--) {
	        printf(" ");
	    }
	    for (; j > 0; j--){
	        printf("#");
	    }
	    printf("\n");     
	}
}
```

### Kangaroo
```c
char* kangaroo(int x1, int v1, int x2, int v2) {
    if(v1 == v2){
        if(x1 != x2)
            return "NO";
        return "YES";
    }
    if((x1-x2)%(v2-v1) == 0 && (x1-x2)*(v2-v1) >= 0)
        return "YES";
    return "NO";
}
```

### Sum of even and odd
```c
int sum_of_even(int a_size, int* a) {
    int ret = 0;
    for(int i=0; i < a_size; ++i)
        ret += ( (a[i] & 1) ? 0 : a[i]);
    return ret;
}

int sum_of_odd(int a_size, int* a) {
    int ret = 0;
    for(int i=0; i < a_size; ++i)
        ret += ( (a[i] & 1) ? a[i] : 0);
    return ret;
}
```

### Find max of 2
```c
int find_max(int n1, int n2) {
    return ((n1 > n2) ? n1 : n2);
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
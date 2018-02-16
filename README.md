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
    less multiple/directories/test.txt
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
    	if (a[i] % 2 == 0 ) 
            ret += a[i];
    return ret;
}

int sum_of_odd(int a_size, int* a) {
    int ret = 0;
    for(int i=0; i < a_size; ++i)
    	if (a[i] % 2 != 0 ) 
            ret += a[i];
    return ret;
}
```
or, for a more efficient version,

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


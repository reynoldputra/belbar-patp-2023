# Contoh Soal


## Nomer 1
```c
#include <stdio.h>

int main() {
    int i;
    for(i = 0; i < ___; i++) {
        printf("%d ", i);
    }

    return 0;
}
```

Output
```c
0 1 2 3 4 
```


Jawaban
```c
#include <stdio.h>

int main() {
    int i;
    for(i = 0; i < 5; i++) {
        printf("%d ", i);
    }

    return 0;
}
```


## Nomer 2
```c
#include <stdio.h>

int main() {
    int x = ___;

    if(x > 5) {
        printf("x is greater than 5\n");
    } else {
        printf("x is less than or equal to 5\n");
    }

    return 0;
}
```

Output
```c
x is greater than 5
```

Jawaban
```c
#include <stdio.h>

int main() {
    int x = 1000;

    if(x > 5) {
        printf("x is greater than 5\n");
    } else {
        printf("x is less than or equal to 5\n");
    }

    return 0;
}
```

## Nomer 3

```c
#include <stdio.h>

int main() {
    int numbers[___] = {1, 2, 3, 4, 5};

    for(int i = 0; i < ___; i++) {
        printf("%d ", numbers[i]);
    }

    return 0;
}
```

output
```c
1 2 3 4 5
```

```c
#include <stdio.h>

int main() {
    int numbers[5] = {1, 2, 3, 4, 5};

    for(int i = 0; i < 5; i++) {
        printf("%d ", numbers[i]);
    }

    return 0;
}
```

## Nomer 4

```c
#include <stdio.h>

int main() {
    for(int i = 0; i < 3; i++) {
        for(int j = 0; j < ___; j++) {
            printf("%d ", j);
        }
        printf("\n");
    }

    return 0;
}
```

output
```c
0 1 2 
0 1 2 
0 1 2 
```

Jawaban
```c
#include <stdio.h>

int main() {
    for(int i = 0; i < 3; i++) {
        for(int j = 0; j < 3; j++) {
            printf("%d ", j);
        }
        printf("\n");
    }

    return 0;
}
```


## Nomer 5

```c
#include <stdio.h>

int main() {
    int numbers[] = {4, 8, 15, 16, 23, 42};
    int target = ___;
    int found = 0;

    for(int i = 0; i < ___; i++) {
        if(numbers[i] == target) {
            found = 1;
            break;
        }
    }

    if(found) {
        printf("Target found!\n");
    } else {
        printf("Target not found!\n");
    }

    return 0;
}

```

Output
```c
Target found!
```

```c
#include <stdio.h>

int main() {
    int numbers[] = {4, 8, 15, 16, 23, 42};
    int target = 15;
    int found = 0;

    for(int i = 0; i < 6; i++) {
        if(numbers[i] == target) {
            found = 1;
            break;
        }
    }

    if(found) {
        printf("Target found!\n");
    } else {
        printf("Target not found!\n");
    }

    return 0;
}

```
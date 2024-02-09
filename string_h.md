## C語言常用函式庫

<br>
<br>

## string.h標頭檔

#### strcpy(字串1, 字串2)

* **定義**
    * 將字串2複製到字串1當中

* **程式範例**

```c
#include <stdio.h>
#include <string.h>

int main() {
    char s[] = "Well begun is half done.";
    char t[25];
    
    strcpy(t, s);
    
    printf("%s\n", t);
    
    return 0;    
}
```

### strncpy(字串1, 字串2, int n)

* **定義**
    * 將字串2中的n個字元複製到字串1當中

* **程式範例**

```c
int main() {
    char s[] = "What's sauce for the goose is sauce for the gander.";
    char t[25];
    
    strncpy(t, s, 20);
    
    printf("%s\n", t);
    
    
    return 0;    
}
```

### strcat(字串1, 字串2)

* **定義**
    * 將字串2銜接在字串1之後

* **程式範例**

```c
#include <stdio.h>
#include <string.h>

int main() {
    char s[30] = "to harp on ";
    char t[30] = "the same string";
    
    strcat(s, t);
    
    printf("%s\n", s);
    
    return 0;    
}
```

### strncat(字串1, 字串2, int n)

* **定義**
    * 將字串2中的n個字元銜接在字串1之後

* **程式範例**

```c
#include <stdio.h>
#include <string.h>

int main() {
    char s1[30] = "practice ";
    char s2[30] = "makes ";
    char s3[30] = "perfect";
    
    strncat(s1, s2, 10);
    strncat(s1, s3, 10);
    
    printf("%s\n", s1);
    
    return 0;    
}
```

### strcmp(字串1, 字串2)

* **定義**
    * 比較兩字串是否相等

* **回傳值**
    * 字串1與字串2**相等**: 回傳**0**
    * 字串1**大於**字串2: 回傳**正值**
    * 字串1**小於**字串2: 回傳**負值**

* **程式範例**

```c
#include <stdio.h>
#include <string.h>

int main() {
    char s[] = "Hello, world!";
    char t[] = "Hello, my friend!";
    int test = strcmp(s, t);
    
    if (test == 0) {
        printf("All right!\n");
    }
    else {
        if (test > 0) {
            printf("%s\n", s);
        }
        else {
            printf("%s\n", t);
        }
    } 
    
    return 0;    
}
```

### strncmp(字串1, 字串2, int n)

* **定義**
    * 比較字串1與字串2中前n個字元是否相等

* **回傳值**
    * 字串1的前n個字元與字串2的前n個字元**相等**: 回傳**0**
    * 字串1的前n個字元**大於**字串2的前n個字元: 回傳**正值**
    * 字串1的前n個字元**小於**字串2的前n個字元: 回傳**負值**

* **程式範例**

```c
#include <stdio.h>
#include <string.h>

int main() {
    char s[] = "Hello, world!";
    char t[] = "Hello, my friend!";
    int test = strncmp(s, t, 6);
    
    if (test == 0) {
        printf("All right!\n");
    }
    else {
        if (test > 0) {
            printf("%s\n", s);
        }
        else {
            printf("%s\n", t);
        }
    } 
    
    return 0;    
}
```

### strchr(字串, 搜尋字元)

* **定義**
    * 搜尋字元在字串中第一次出現的位置，並回傳該位置的指標

* **程式範例**

```c
#include <stdio.h>
#include <string.h>

int main() {
    char s[] = "Rome was not built in a day.";
    char t = 'a';
    char *test;
    
    test = strchr(s, t);
    printf("%s\n", test);
     
    return 0;    
}
```

### strcspn(字串1, 字串2)

* **定義**
    * 計算經過幾個字元，會在字串1中遇到屬於字串2中的字元

* **程式範例**

```c
#include <stdio.h>
#include <string.h>

int main() {
    char s[] = "The spirit is willing but the flesh is weak.";
    char t[] = "but";
    
    printf("%d\n", strcspn(s, t));
    
    return 0;    
}
```

### strspn(字串1, 字串2)

* **定義**
    * 計算經過幾個字元，會在字串1中遇到不屬於字串2中的字元

* **程式範例**

```c
#include <stdio.h>
#include <string.h>

int main() {
    char s[] = "There is no royal road to learning.";
    char t[] = "There is no royal road";
    
    printf("%d\n", strspn(s, t));
    
    return 0;    
}
```

### sprpbrk(字串1, 字串2)

* **定義**
    * 回傳字串2中的任意字元在字串1中首次出現位置的指標

* **程式範例**

```c
#include <stdio.h>
#include <string.h>

int main() {
    char s[] = "Make hay while the sun shines.";
    char t[] = "iou";
    char *test;
    
    test = strpbrk(s, t);
    printf("%s\n", test);
    
    return 0;    
}
```

### strrchr(字串, 字元)

* **定義**
    * 回傳字元在字串中最後一次出現的位置的指標

* **程式範例**

```c
#include <stdio.h>
#include <string.h>

int main() {
    char s[] = "Necessity is the mother of invention.";
    char *test;
    
    test = strrchr(s, ' ');
    printf("%s\n", test);
    
    return 0;    
}
```

### strstr(字串1, 字串2)

* **定義**
    * 回傳字串2首次出現在字串1中的位置指標
    
* **程式範例**

```c
#include <stdio.h>
#include <string.h>

int main() {
    char s[] = "Self-trust is the first secret of success.";
    char t[] = "secret";
    char *test;
    
    test = strstr(s, t);
    printf("%s\n", test);
    
    return 0;    
}
```

### strtok(字串1, 字串2)

* **定義**
    * 以字串2的內容切割字串1
    
* **程式範例**

```c
#include <stdio.h>
#include <string.h>

int main() {
    char s[] = "Speech is si1ver, silence is gold.";
    char t[] = " ";
    char *test = strtok(s, " ");
    
    while (test != NULL) {
        printf("%s\n", test);
        test = strtok(NULL, " ");
    }
    
    return 0;    
}
```

### strlen(字串)

* **定義**
    * 回傳字串長度

* **性質**
    * `strlen()`在計算字串長度時，不包括字串結束符號

* **程式範例**

```c
#include <stdio.h>
#include <string.h>

int main() {
    char s[] = "You may go farther and fare worse.";
    
    printf("%d\n", strlen(s));
    
    return 0;    
}
```

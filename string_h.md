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

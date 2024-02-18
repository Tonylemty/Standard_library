# C語言常用函式庫

</br>
</br>

## ctype.h標頭檔

#### isdigit(字元)

* **定義**
    * 判斷字元是否為**十進位**數字

* **回傳值**
    * 若字元為十進位數字，回傳非0
    * 若字元不為十進位數字，回傳0

* **程式範例**

```c
#include <stdio.h>
#include <stdlib.h>
#include <ctype.h>
int main () {
  char str[] = "1776ad";
  int year;
  if (isdigit(str[0]))
  {
    year = atoi (str);
    printf ("The year that followed %d was %d.\n", year, year+1);
  }
  return 0;
}
```

#### isalpha(字元)

* **定義**
    * 判斷字元是否為英文字母

* **回傳值**
    * 若字元為英文字母，回傳非0
    * 若字元不為英文字母，回傳0

* **程式範例**

```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char t;
    
    while (t = getchar()) {
        if (t == EOF) {
            break;
        }
        
        if (t == '\n') {
            continue;
        }
        
        if (isalpha(t)) {
            printf("對，是字母...\n");
        } 
        else {
            printf("不是字母喔...\n");
        }
    }
    
    return 0;
}
```

#### isalnum(字元)

* **定義**
    * 判斷字元是否為數字或是英文字母

* **回傳值**
    * 若字元為數字或是英文字母，回傳非0
    * 若字元不為數字或是英文字母，回傳0

* **程式範例**

```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char t;
    
    while (t = getchar()) {
        if (t == EOF) {
            break;
        }
        
        if (t == '\n') {
            continue;
        }
        
        if (isalnum(t)) {
            printf("對，是數字或字母...\n");
        } 
        else {
            printf("不是數字或字母喔...\n");
        }
    }
    
    return 0;
}
```

#### isxdigit(字元)

* **定義**
    * 判斷字元是否為**十六進位**數字

* **回傳值**
    * 若字元為十六進位數字，回傳非0
    * 若字元不為十六進位數字，回傳0

* **程式範例**

```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char t;
    
    while (t = getchar()) {
        if (t == EOF) {
            break;
        }
        
        if (t == '\n') {
            continue;
        }
        
        if (isxdigit(t)) {
            printf("對，是十六進位數字...\n");
        } 
        else {
            printf("不是十六進位數字喔...\n");
        }
    }
    
    return 0;
}
```

#### islower(字元)

* **定義**
    * 判斷字元是否為**小寫**英文字母

* **回傳值**
    * 若字元為小寫英文字母，回傳非0
    * 若字元不為小寫英文字母，回傳0

* **程式範例**

```c
#include <stdio.h>
#include <ctype.h>
int main () {
  int i = 0;
  char str[] = "Test String.\n";
  char c;
  while (str[i])
  {
    c=str[i];
    if (islower(c)) c = toupper(c);
    putchar(c);
    i++;
  }
  return 0;
}
```

#### isupper(字元)

* **定義**
    * 判斷字元是否為**大寫**英文字母

* **回傳值**
    * 若字元為大寫英文字母，回傳非0
    * 若字元不為大寫英文字母，回傳0

* **程式範例**

```c
#include <stdio.h>
#include <ctype.h>
int main () {
  int i = 0;
  char str[] = "Test String.\n";
  char c;
  while (str[i])
  {
    c=str[i];
    if (isupper(c)) c = tolower(c);
    putchar(c);
    i++;
  }
  return 0;
}
```

#### isascii(字元)

* **定義**
    * 判斷字元是否為ASCII符號

* **回傳值**
    * 若字元為ASCII符號，回傳非0
    * 若字元不為ASCII符號，回傳0

* **程式範例**

```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char t;
    
    while (t = getchar()) {
        if (t == EOF) {
            break;
        }
        
        if (t == '\n') {
            continue;
        }
        
        if (isascii(t)) {
            printf("對，是ASCII字元...\n");
        } 
        else {
            printf("不是ASCII字元喔...\n");
        }
    }
    
    return 0;
}
```

#### isblank(字元)

* **定義**
    * 判斷字元是否為空白字元
    
* **回傳值**
    * 若字元為空白字元，回傳非0
    * 若字元不為空白字元，回傳0

* **程式範例**

```c
#include <stdio.h>
#include <ctype.h>
int main () {
  char c;
  int i = 0;
  char str[] = "Example sentence to test isblank\n";
  while (str[i])
  {
    c=str[i];
    if (isblank(c)) c='\n';
    putchar(c);
    i++;
  }
  return 0;
}
```

#### isspace(字元)

* **定義**
    * 判斷字元是否為空格

* **回傳值**
    * 若字元為空格，回傳非0
    * 若字元不為空格，回傳0

* **程式範例**

```c
#include <stdio.h>
#include <ctype.h>
int main () {
  char c;
  int i = 0;
  char str[] = "Example sentence to test isspace\n";
  while (str[i])
  {
    c = str[i];
    if (isspace(c)) c='\n';
    putchar(c);
    i++;
  }
  return 0;
}
```

#### iscntrl(字元)

* **定義**
    * 判斷字元是否控制字元

* **回傳值**
    * 若字元為控制字元，回傳非0
    * 若字元不為控制字元，回傳0

* **程式範例**

```c
#include <stdio.h>
#include <ctype.h>
int main () {
  int i = 0;
  char str[] = "first line \n second line \n";
  while (!iscntrl(str[i]))
  {
    putchar(str[i]);
    i++;
  }
  return 0;
}
```

#### ispunct(字元)

* **定義**
    * 判斷字元是否為空格、數字、英文字母以外的可列印字符
    
* **回傳值**
    * 若字元為可列印字符，回傳非0
    * 若字元不為可列印字符，回傳0

* **程式範例**

```c
#include <stdio.h>
#include <ctype.h>
int main () {
  int i = 0;
  int cx = 0;
  char str[] = "Hello, welcome!";
  while (str[i])
  {
    if (ispunct(str[i])) cx++;
    i++;
  }
  printf ("Sentence contains %d punctuation characters.\n", cx);
  return 0;
}
```

#### isprint(字元)

* **定義**
    * 判斷字元是否為含括空格以內的可列印字元

* **回傳值**
    * 若字元為含括空格以內的可列印字符，回傳非0
    * 若字元不為含括空格以內的可列印字符，回傳0

* **程式範例**

```c
#include <stdio.h>
#include <ctype.h>
int main () {
  int i = 0;
  char str[] = "first line \n second line \n";
  while (isprint(str[i]))
  {
    putchar(str[i]);
    i++;
  }
  return 0;
}
```

#### isgraph(字元)

* **定義**
    * 判斷字元是否為空格以外的可列印字元

* **回傳值**
    * 若字元為空格以外的可列印字符，回傳非0
    * 若字元不為空格以外的可列印字符，回傳0

* **程式範例**

```c
#include <stdio.h>
#include <ctype.h>
int main () {
  FILE * pFile;
  int c;
  pFile=fopen ("myfile.txt","r");
  if (pFile)
  {
    do {
      c = fgetc (pFile);
      if (isgraph(c)) putchar (c);
    } while (c != EOF);
    fclose (pFile);
  }
}
```

#### tolower(字元)

* **定義**
    * 將大寫英文字母轉換為小寫英文字母

* **回傳值**
    * 原本為大寫英文字母，回傳小寫英文字母
    * 原本為小寫英文字母，或是非英文字母，回傳原本的參數值

* **程式範例**

```c
#include <stdio.h>
#include <ctype.h>
int main () {
  int i = 0;
  char str[] = "Test String.\n";
  char c;
  while (str[i])
  {
    c=str[i];
    putchar(tolower(c));
    i++;
  }
  return 0;
}
```

#### toupper(字元)

* **定義**
    * 將小寫英文字母轉換為大寫英文字母

* **回傳值**
    * 原本為小寫英文字母，回傳大寫英文字母
    * 原本為大寫英文字母，或是非英文字母，回傳原本的參數值

* **程式範例**

```c
#include <stdio.h>
#include <ctype.h>
int main () {
  int i = 0;
  char str[] = "Test String.\n";
  char c;
  while (str[i])
  {
    c = str[i];
    putchar(toupper(c));
    i++;
  }
  return 0;
}
```

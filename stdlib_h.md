# C語言常用函式庫

</br>
</br>

## stdlib.h標頭檔

#### atof(字串)

* **定義**
    * 將字串中的數字轉換為`double`型態的浮點數

* **程式範例**

```c
#include <stdio.h>
#include <stdlib.h>

int main() {

    printf("%f\n", atof("54321"));
    printf("%f\n", atof("54.321"));
    printf("%f\n", atof("$54321"));
    printf("%f\n", atof("$54.321"));
    printf("%f\n", atof("54.321%"));
    printf("%f\n", atof("5.4321+33=?"));
    
    return 0;
}
```

#### atoi(字串)

* **定義**
    * 將字串中的數字轉換為`int`型態的整數

* **程式範例**
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    printf("%d\n", atoi("54321"));
    printf("%d\n", atoi("54.321"));
    printf("%d\n", atoi("$54321"));
    printf("%d\n", atoi("$54.321"));
    printf("%d\n", atoi("54.321%"));
    printf("%d\n", atoi("5.4321+33=?"));
    
    return 0;
}
```

#### atol(字串)

* **定義**
    * 將字串中的數字轉換為`long`型態的長整數
    
* **程式範例**
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    printf("%ld\n", atol("54321"));
    printf("%ld\n", atol("54.321"));
    printf("%ld\n", atol("$54321"));
    printf("%ld\n", atol("$54.321"));
    printf("%ld\n", atol("54.321%"));
    printf("%ld\n", atol("5.4321+33=?"));
    
    return 0;
}
```

#### strtod(字串)

* **定義**
    * 將字串中的數字轉換為`double`型態的浮點數，其餘非數字部分以另一指標儲存位址
    * 簡單來說，就是擷取字串中的數字部分，並轉換型態

* **程式範例**
```c
#include <stdlib.h>
#include <ctype.h>
#include <stdio.h>

int main() {
    char *test = "the answer is 33.23mm + 25mm";
    char *endPtr = test;
    double sum = 0.0;
    
    while (*test) {
        sum += strtod(test, &endPtr);
        test = endPtr;
        
        while (!isdigit(*test) && *test) {
            test++;
        }
    }
    
    printf("the answer is %.2f mm\n", sum);

    return 0;
}
```

#### strtol(字串)

* **定義**
    * 將字串中的數字轉換為`long`型態的浮點數，其餘非數字部分以另一指標儲存位址
    * 簡單來說，就是擷取字串中的數字部分，並轉換型態

* **程式範例**
```c
#include <stdlib.h>
#include <ctype.h>
#include <stdio.h>

int main() {
    char *test = "the answer is 33.23mm + 25mm";
    char *endPtr = test;
    long sum = 0;
    
    while (*test) {
        sum += strtol(test, &endPtr, 0);
        test = endPtr;
        
        while (!isdigit(*test) && *test) {
            test++;
        }
    }
    
    printf("the answer is %d mm\n", sum);

    return 0;
}
```

#### bsearch(參數1, 參數2, 參數3, 參數4, 參數5)

* **參數解釋**
    * 參數1: 搜尋目標數值的指標
    * 參數2: 被搜尋的**已排序**陣列
    * 參數3: 排序陣列的數目
    * 參數4: 利用`sizeof`計算參數1所佔的記憶體空間
    * 參數5: 為函數指標，例如以下程式碼
        ```c
        int cmp(const void *a, const void *b) {
            return *(int*)a - *(int*)b; // (int*)為型別轉換，因此不一定是int型態
        }
        ```

* **定義**
    * 在已排序陣列中進行二元搜尋(binary search)

* **程式範例**
```c
#include <stdio.h>
#include <stdlib.h>

int cmp(const void *s1, const void *s2); 

int main() {
    char *vowel = "AEIOUaeiou";
    char *test1 = "thesaurus";
    char *test2 = "Apple";
    char *ptr;
    
    ptr = bsearch(test1, vowel, 10, sizeof(*test1), cmp);    
    if (ptr) {
        printf("%s的第一個字母是母音...\n", test1);
    }
    else {
        printf("%s的第一個字母不是母音...\n", test1);
    }
    
    ptr = bsearch(test2, vowel, 10, sizeof(*test2), cmp);    
    if (ptr) {
        printf("%s的第一個字母是母音...\n", test2);
    }
    else {
        printf("%s的第一個字母不是母音...\n", test2);
    }
   
    return 0;
}

int cmp(const void *s1, const void *s2) {
    return *(char *)s1 - *(char *)s2;
}
```

#### qsort(參數1, 參數2, 參數3, 參數4)

* **參數解釋**
    * 參數1: 要進行排序的陣列
    * 參數2: 陣列的個數
    * 參數3: 利用`sizeof`計算陣列元素所佔的記憶體空間
    * 參數4: 函數指標，需自行定義排序陣列的排序比較方式，如以下函式
    ```c
    int cmp(const void *a, const void *b) {
            return *(int*)a - *(int*)b; // (int*)為型別轉換，因此不一定是int型態
        }
    ```

* **定義**
    * 替陣列元素進行排列

* **程式範例**
```c
#include <stdio.h>
#include <stdlib.h>

int cmp(const void *s1, const void *s2);

int main() {
    char test[] = "qwertyuioplkjhgfdsazxcvbnm";
    
    qsort(test, 26, sizeof(char), cmp);
    printf("%s\n", test);
    
    return 0;
}

int cmp(const void *s1, const void *s2) {
    return *(char *)s1 - *(char *)s2;
}
```

#### calloc(陣列元素個數, 元素所佔記憶體空間大小)

* **定義**
    * 用來做動態記憶體配置，可產生動態陣列的記憶體空間

* **程式範例**
```c
#include <stdlib.h>
#include <stdio.h>

int main() {
    int *nPtr;
    
    nPtr = calloc(100, sizeof(int));
    
    if (nPtr == NULL) {
        printf("建立記憶體空間失敗\n");
    }
    else {
        printf("建立記憶體空間成功\n");
    }

    return 0;
}
```

#### malloc(sizeof(型態))

* **定義**
    * 用來做動態記憶體配置，產生動態記憶體空間

* **回傳值**
    * 若建立成功，回傳指向該空間的指標
    * 若建立失敗，回傳`NULL`
    
* **程式範例**
```c
#include <stdlib.h>
#include <stdio.h>

int main() {
    int *nPtr;
    
    nPtr = malloc(sizeof(int));
    
    if (nPtr == NULL) {
        printf("建立記憶體空間失敗\n");
    }
    else {
        printf("建立記憶體空間成功\n");
    }

    return 0;
}
```

#### realloc(指向原始空間的指標, 新空間的大小)

* **定義**
    * 用來做動態記憶體配置，可改變由`malloc()`、`calloc()`或是`realloc()`所配置的記憶體空間大小

* **回傳值**
    * 若調整成功，回傳指向重新分配空間的指標
    * 若調整失敗，回傳`NULL`

* **程式範例**
```c
#include <stdlib.h>
#include <stdio.h>
#include <string.h>

int main() {
    char *ptr;
    
    ptr = malloc(23);
    if (ptr == NULL) {
        printf("建立記憶體區域失敗...\n");
        exit(1);
    }
    strcpy(ptr, "History repeats itself.");

    ptr = realloc(ptr, 25);
    if(ptr == NULL) {
        printf("擴充記憶體區域失敗...\n");
        exit(1);
    }
    strcat(ptr, "\n");

    printf(ptr);
    free(ptr);

    return 0;
}
```

#### free(指向記憶體空間的指標)

* **定義**
    * 釋放原先所指向的記憶體空間

* **性質**
    * `free()`並非刪除原先記憶體空間的資料，也並非將操作的指標變數改為指向`NULL`，而是告訴作業系統，程式不會再使用這記憶體

* **程式範例**
```c
#include <stdlib.h>
#include <stdio.h>
#include <string.h>

int main() {
    char *tPtr;
    
    tPtr = malloc(40);
    if (tPtr == NULL) {
        printf("建立記憶體區域失敗...\n");
        exit(1);
    }
    
    strcpy(tPtr, "Actions speak louder than words.");
    printf("tPtr: %p\n", tPtr);
    
    free(tPtr);
    printf("tPtr: %p\n", tPtr);
    
    return 0;
}
```

#### abort()

* **定義**
    * 使程式異常結束，並將控制權傳回給主機環境

* **性質**
    * 緊急終止程式
    * 屬於**非正常**終止程式
    * 用於程式偵錯
    * 可用於處理無法恢復的錯誤

* **程式範例**
```c
#include <stdlib.h>
#include <stdio.h>

int main() {
    printf("程式將會以不正常方式結束...\n");
    abort();
    
    return 0;
}
```

#### exit()

* **定義**
    * 使程式正常的結束，並將控制權從程式傳回給主機環境

* **程式範例**
```c
#include <stdlib.h>
#include <stdio.h>

int main() {
    printf("程式將會以正常方式結束...\n");
    exit(1);
    
    return 0;
}
```

#### system("作業系統指令")

* **定義**
    * 使程式執行作業系統的指令

* **常用作業系統指令(以Windows為例)**
    * dir: 列出當前目錄中的文件和子目錄
    * copy: 複製文件或目錄
    * del: 刪除文件
    * ren: 重新命名文件
    * move: 移動文件或目錄
    * mkdir: 建立新的目錄
    * remdir: 刪除目錄
    <br>
    詳細指令可點選連結: [點我看CMD指令](https://reurl.cc/Z9lQkQ)

* **程式範例**
```c
#include <stdlib.h>
#include <stdio.h>

int main() {

    system("date"); // 顯示時間日期
    return 0;
}
```

### abs(int 整數)

* **定義**
    * 回傳型態為`int`整數的絕對值

* **種類**
    * 尚有`long`型態的`labs(long int)`
    * 尚有`long long`型態的`llabs(long long int)`

* **程式範例**

```c
#include <stdio.h>      
#include <stdlib.h>    

int main () {
    printf ("%d\n", abs(23));
    printf ("%d\n", abs(-11));
    return 0;
}
// long型態與long long型態的使用方法皆與int型態的abs()相同
```

### div(被除數, 除數)

* **定義**
    * 回傳定義在`<stdlib.h>`函式庫中的結構(**div_t**)中的值，分別為

    ```c
    int quot; // 商數
    int rem; // 餘數
    ```

* **種類**
    * 尚有`long`型態的`ldiv(long int 整數)`，結構為`ldiv_t`
    * 尚有`long long`型態的`lldiv(long long int 整數)`，結構為`lldiv_t`

* **程式範例**

```c
#include <stdio.h>      
#include <stdlib.h>    

int main () {
  div_t divresult; // 宣告結構變數
  divresult = div (38,5);
  printf ("38 div 5 => %d, remainder %d.\n", divresult.quot, divresult.rem);
  return 0;
}
// long型態與long long型態的使用方法皆與int型態的div()相同

```

### rand()

* **定義**
    * 產生隨機數字

* **性質**
    * 由於`rand()`函數的生成數字是由種子值以及算法共同決定。因此，若在不設置種子值的情況下，`rand()`將使用同一個種子值，而這也將導致程式每次執行都將產生同一個隨機數
    * 通常會搭配`srand()`來設置種子值，並且使用目前時間作為種子，以確保每次程式執行時，都能產生不同的隨機數

* **隨機數範圍例子及說明**

    * 根據以下產生隨機數的程式碼可以知道，我們主要是透過`rand()`產生的隨機數與後面數字，如100, 30，去做取餘數的動作，以得到固定範圍中的值

    ```c
    num1 = rand() % 100; // 範圍為0到99
    num2 = rand() % 100 + 1 // 範圍為1到100
    num3 = rand() % 30 + 1985 // 範圍為1985到2014
    ```

* **程式範例**

```c
#include <stdio.h>
#include <stdlib.h> // srand()
#include <time.h> // time()

int main() {
    
    srand(time(NULL)); // 確保每次運行都能獲得不同的隨機數序列

    int num1 = rand() % 100;

    printf("隨機數: %d\n", num1);

    return 0;
}
```

### srand(參數)

* **定義**
    * 初始化隨機亂數產生函數(`rand()`)

* **參數**
    * 為隨機亂數函數演算法作為種子的整數值

* **程式範例**

```c
#include <stdio.h>      
#include <stdlib.h>     
#include <time.h>       /* time */

int main () {
  printf ("First number: %d\n", rand() % 100);
  srand (time(NULL));
  printf ("Random number: %d\n", rand() % 100);
  srand (1);
  printf ("Again the first number: %d\n", rand() % 100);

  return 0;
}
```

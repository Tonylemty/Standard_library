# C語言常用函式庫

</br>
</br>

## math.h標頭檔

#### fabs(數字)

* **定義**
    * 回傳數字的**絕對值**

* **性質**
    * 預設回傳值以及參數的資料型態為`double`
    * 另有`float`型態的`fabsf()`以及`long double`型態的`fabsl()`

* **程式範例**

```c
#include <stdio.h>
#include <math.h>

int main(void) {

    printf("%f\n", fabs(-2.36));
    printf("%f\n", fabs(2.36));
    printf("%f\n", fabs(0));
    printf("%f\n", fabs(-0));
    printf("%f\n", fabs(-(-2.36)));
    printf("%f\n", fabs(-(2.36)));
    
    return 0;
}
```


#### fmax(數字1, 數字2)
    
* **定義**
    * 回傳兩個數字中的**最大值**

* **性質**
    * 預設的回傳值以及參數的資料型態為`double`
    * 另有`float`型態的`fmaxf()`以及`long double`型態的`fmaxl()`

* **程式範例**

```c
#include <stdio.h>
#include <math.h>

int main(void) {

    printf("%f\n", fmax(33, 22));
    printf("%f\n", fmax(-33, -22));
    printf("%f\n", fmax(33, -22));
    printf("%f\n", fmax(-33, 22));
    printf("%f\n", fmax(33 - 22, 22 - 33));
    printf("%f\n", fmax(33 + 22, 22 + 33));
    
    return 0;
}
```


#### fmin(數字1, 數字2)
    
* **定義**
    * 回傳兩個數字中的**最小值**

* **性質**
    * 預設回傳值以及參數的資料型態為`double`
    * 另有`float`型態的`fminf()`以及`long double`型態的`fminl()`

* **程式範例**

```c
#include <stdio.h>
#include <math.h>

int main(void) {

    printf("%f\n", fmin(33, 22));
    printf("%f\n", fmin(-33, -22));
    printf("%f\n", fmin(33, -22));
    printf("%f\n", fmin(-33, 22));
    printf("%f\n", fmin(33 - 22, 22 - 33));
    printf("%f\n", fmin(33 + 22, 22 + 33));
    
    return 0;
}
```


#### remainder(數字1, 數字2)
    
* **定義**
    * 回傳數字1除以數字2的**浮點餘數**

* **性質**
    * 預設回傳值以及參數的資料型態為`double`
    * 另有`float`型態的`remainderf()`以及`long double`型態的`remainderl()`

* **程式範例**

```c
#include <stdio.h>
#include <math.h>

int main(void) {

    printf("%f\n", remainder(33, 23.5));
    
    return 0;
}
```


#### fma(數字1, 數字2, 數字3)
    
* **定義**
    * 回傳**數字1**乘以**數字2**，再加上**數字3**的結果

* **性質**
    * 預設回傳值以及參數的資料型態為`double`
    * 另有`float`型態的`fmaf()`以及`long double`型態的`fmal()`

* **程式範例**

```c
#include <stdio.h>
#include <math.h>

int main(void) {

    printf("%f\n", fma(2, 3, 4));
    printf("%f\n", fma(-2, -3, -4));
    printf("%f\n", fma(2, -3, 4));
    printf("%f\n", fma(2, -3, -4));
    printf("%f\n", fma(-2, 3, 4));
    printf("%f\n", fma(-2, -3, 4));
    
    return 0;
}
```


#### round(數字)

* **定義**
    * 回傳數字最接近`double`型態的**整數值**，同時會自動四捨五入

* **性質**
    * 預設回傳值以及參數的資料型態為`double`
    * 另有`float`型態的`roundf()`以及`long double`型態的`roundl()`

* **程式範例**

```c
#include <stdio.h>
#include <math.h>

int main(void) {

    printf("%f\n", round(8.2));
    printf("%f\n", round(8.49));
    printf("%f\n", round(8.5));
    printf("%f\n", round(8.52));
    printf("%f\n", round(8.6));
    printf("%f\n", round(8.8));
    
    return 0;
}    
```


#### sqrt(數字)
    
* **定義**
    * 回傳數字的**平方根**

* **性質**
    * 預設回傳值以及參數的資料型態為`double`
    * 另有`float`型態的`sqrtf()`以及`long double`型態的`sqrtl()`

* **程式範例**

```c
#include <stdio.h>
#include <math.h>

int main(void) {

    printf("%f\n", sqrt(25));
    printf("%f\n", sqrt(64.0));
    printf("%f\n", sqrt(27.5));
    printf("%f\n", sqrt(30.25));
    printf("%f\n", sqrt(81.02));
    printf("%f\n", sqrt(9.3));

    return 0;
}
```


#### cbrt(數字)
    
* **定義**
    * 回傳數字的**立方根**

* **性質**
    * 預設回傳值以及參數的資料型態為`double`
    * 另有`float`型態的`cbrtf()`以及`long double`型態的`cbrtl()`

* **程式範例**

```c
#include <stdio.h>
#include <math.h>

int main(void) {

    printf("%f\n", cbrt(125.0));
    printf("%f\n", cbrt(35.937));
    printf("%f\n", cbrt(27));
    printf("%f\n", cbrt(42.2));
    printf("%f\n", cbrt(97.325));
    printf("%f\n", cbrt(88.025));
    
    return 0;
}
```


#### pow(數字, 次方)
    
* **定義**
    * 回傳數字N次方的結果

* **性質**
    * 預設回傳值以及參數的資料型態為`double`
    * 另有`float`型態的`powf()`以及`long double`型態的`powl()`

* **程式範例**

```c
#include <stdio.h>
#include <math.h>

int main(void) {

    printf("%f\n", pow(2, 3));
    printf("%f\n", pow(2, 3.2));
    printf("%f\n", pow(6, 8));
    printf("%f\n", pow(10, 6));
    printf("%f\n", pow(7.3, 5));
    printf("%f\n", pow(6.9, 9.3));
    
    return 0;
}
```


#### hypot(數字1, 數字2)

* **定義**
    * 回傳數字1與數字2平方和的**平方根**，也就是直角三角形斜邊

* **性質**
    * 預設回傳值以及參數的資料型態為`double`
    * 另有`float`型態的`hypotf()`以及`long double`型態的`hypotl()`

* **程式範例**

```c
#include <stdio.h>
#include <math.h>

int main(void) {

    printf("%f\n", hypot(3, 4));
    printf("%f\n", hypot(5, 12));
    printf("%f\n", hypot(7, 24));
    printf("%f\n", hypot(8, 15));
    printf("%f\n", hypot(9, 12));
    printf("%f\n", hypot(10, 24));
    
    return 0;
}
```


#### sin(弧度)

* **定義**
    * 回傳數字的正弦值，單位為<font color = "#E74C3C">**弧度**</font>

* **性質**
    * 預設回傳值以及參數的資料型態為`double`
    * 另有`float`型態的`sinf()`以及`long double`型態的`sinl()`

* **程式範例**
```c
#include <stdio.h>
#include <math.h>

int main(void) {

    double i = -1.0; // radian
    
    while (i <= 1.0) {
        printf("%f\n", sin(i));
        i += 0.1;
    }
    return 0;
}
```


#### cos(弧度)

* **定義**
    * 回傳數字的餘弦值，單位為<font color = "#E74C3C">**弧度**</font>

* **性質**
    * 預設回傳值以及參數的資料型態為`double`
    * 另有`float`型態的`cosf()`以及`long double`型態的`cosl()`

* **程式範例**
```c
#include <stdio.h>
#include <math.h>

int main(void)
{
    double i = -1.0; // radian
    
    while (i <= 1.0) {
        printf("%f\n", cos(i));
        i += 0.1;
    }
    
    return 0;
}
```


#### tan(弧度)

* **定義**
    * 回傳數字的正切值，單位為<font colot = "#E74C3C">**弧度**</font>

* **性質**
    * 預設回傳值以及參數的資料型態為`double`
    * 另有`float`型態的`tanf()`以及`long double`型態的`tanl()

* **程式範例**
```c
#include <stdio.h>
#include <math.h>

int main(void) {

    double i = -1.0; // radian
    
    while (i <= 1.0) {
        printf("%f\n", tan(i));
        i += 0.1;
    }
    
    return 0;
}
```


#### log(數字)

* **定義**
    * 回傳數字以常數<font color = "#E74C3C">***e***</font>為底的對數值

* **性質**
    * 預設回傳值以及參數的資料型態為`double`
    * 另有`float`型態的`logf()`以及`long double`型態的`logl()`

* **程式範例**
```c
#include <stdio.h>
#include <math.h>

int main(void) {

    double i = 1.0;
    
    while (i <= 10.0) {
        printf("%f\n", log(i));
        i += 1.0;
    }
    
    return 0;
}
```


#### log2(數字)

* **定義**
    * 回傳數字以<font color = "#E74C3C">**2**</font>為底的對數值

* **性質**
    * 預設回傳值以及參數的資料型態為`double`
    * 另有`float`型態的`log2f()`以及`long double`型態的`log2l()`

* **程式範例**
```c
#include <stdio.h>
#include <math.h>

int main(void) {
    double i = 1.0;
    
    while (i <= 10.0) {
        printf("%f\n", log2(i));
        i += 1.0;
    }
    
    return 0;
}
```


#### log10(數字)

* **定義**
    * 回傳數字以<font color = "#E74C3C">**10**</font>為底的對數值

* **性質**
    * 預設回傳值以及參數的資料型態為`double`
    * 另有`float`型態的`log10f()`以及`long double`型態的`log10l()`

* **程式範例**

```c
#include <stdio.h>
#include <math.h>

int main(void) {
    double i = 1.0;
    
    while (i <= 10.0) {
        printf("%f\n", log10(i));
        i += 1.0;
    }
    
    return 0;
}
```

#### floor(數字x)

* **定義**
    * 返回**小於**或**等於**數字x的最大整數值

* **性質**
    * 預設回傳值以及參數的資料型態為`double`
    * 另有`float`型態的`floorf()`以及`long double`型態的`floorl()`

* **程式範例**

```c
#include <stdio.h>
#include <math.h>

int main() {

    printf("%d\n", floor(2.3));
    printf("%d\n", floor(3.5));
    printf("%d\n", floor(4.0));    

    return 0;
}
```

#### ceil(數字x)

* **定義**
    * 返回**大於**或**等於**數字x的最小整數值

* **性質**
    * 預設回傳值以及參數的資料型態為`double`
    * 另有`float`型態的`ceilf()`以及`long double`型態的`ceill()`

* **程式範例**

```c
#include <stdio.h>
#include <math.h>

int main() {

    printf("%d\n", ceil(2.2));
    printf("%d\n", ceil(3.5));
    printf("%d\n", ceil(5.0));    

    return 0;
}
```

#### fmod(數字1, 數字2)

* **定義**
    * 返回數字1除以數字2的餘數

* **性質**
    * 預設回傳值以及參數的資料型態為`double`
    * 另有`float`型態的`fmodf()`以及`long double`型態的`fmodl()`

* **程式範例**

```c
#include <stdio.h>
#include <math.h>

int main() {

    printf("%d\n", fmod(9, 3));
    printf("%d\n", ceil(8, 5));
    printf("%d\n", ceil(2, 3));    

    return 0;
}
```


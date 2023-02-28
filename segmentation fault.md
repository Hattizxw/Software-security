# 为什么会出现这个错误

一般都是出现了非法的地址写法操作导致的。

### 1. 空指针访问。

如果指针为空(NULL), 那么对空指针的读写操作都会导致segmentation fault。

https://software-security-1316943030.cos.ap-nanjing.myqcloud.com/segmentation%20fault1.webp

### 2. 指针指向非法区域后的写操作。

C语言的指针指向了非法区域，然后对其写入，会带来不可预知后果，最严重的就是程序崩溃，此时也是segmentation fault。

https://software-security-1316943030.cos.ap-nanjing.myqcloud.com/segmentation%20fault2.webp

### 3. 常量空间破坏

比如常量字符串，如果修改其内容，则会出现segmentation fault。

https://software-security-1316943030.cos.ap-nanjing.myqcloud.com/segmentation%20fault3.webp

### 4. 在一些比较老的操作系统上，非对齐访问也可能导致segmentation fault。

https://software-security-1316943030.cos.ap-nanjing.myqcloud.com/segmentation%20fault4.webp

# 例子：

https://software-security-1316943030.cos.ap-nanjing.myqcloud.com/segmentation%20fault5.png

we didn’t allocate the memory to store the string, thus the pointer p is NULL! (if we are lucky!! what might happen if we aren’t?) To fix it, we need to use malloc() to allocate memory in the heap to store the string
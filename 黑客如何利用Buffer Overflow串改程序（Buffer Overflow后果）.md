https://software-security-1316943030.cos.ap-nanjing.myqcloud.com/Buffer%20Overflow4.png

https://software-security-1316943030.cos.ap-nanjing.myqcloud.com/Buffer%20Overflow5.png

代码中，我们可以看到，用户可以输入的是两个参数argc和argv

# exploit

黑客在buffur内填充满nop命令（表示跳过），并在nop中间插入malicious code（恶意代码），并输入的内存超出buffer定义的大小，**并且将return给覆盖了**

https://software-security-1316943030.cos.ap-nanjing.myqcloud.com/Buffer%20Overflow6.png

https://software-security-1316943030.cos.ap-nanjing.myqcloud.com/Buffer%20Overflow7.png

### 程序运行过程

程序从上到下，顺序执行，将agrv里面的内容复制给buffer，在执行return的时候，由于return里面的值被覆盖了，他会执行覆盖之后的内容（跳到黑客指定的位置），即图片中的0x7ff7bfeff750，先执行跳过语句，然后执行恶意代码。
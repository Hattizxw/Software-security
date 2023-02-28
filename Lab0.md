[secure.ecs.soton.ac.uk](https://secure.ecs.soton.ac.uk/noteswiki/images/COMP6236_Lab0.pdf)

# Challenge 1 - Compile a C Program

### 题目：

> Inside lab0/task1, there is a file called helloworld.c. Using online resources, find out how to compile the program using **gcc** and run it. What does the program output when it is run? 
>
> Hint: What can you learn from running the following command “man gcc”? 
>
> Hint: to run a newly compiled C program you need to prefix “./”” to the program name.

### 答案：

https://software-security-1316943030.cos.ap-nanjing.myqcloud.com/lab01.PNG

**ls:**查看本目录下所有文件

**cd 文件名**：进入文件夹

**cat 文件名：**查看文件内容

**gcc -o 编译之后的名字 编译文件的名字：**编译程序（程序转换成二进制）

**./ 文件名：**运行代码

# Challenge 2 - Extracting Strings from a Progra

### 题目：

> Inside lab0/task2 is another identical C program, but it has been compiled with a secret string which is never output. The source code is available in task2-redacted.c

task2文件夹下有两个文件tesk2（程序的二进制形式的代码）和tesk2-redacted.c（c语言形式的代码）

在tesk2-redacted.c中，有一个应该被打印出来的字符串被作者给用[REDACYED]给替换了，但是tesk2文件中有原来本应该被打印出来的字符串，我们要在tesk2中找到这个字符串到底是什么

### 答案

https://software-security-1316943030.cos.ap-nanjing.myqcloud.com/lab02.PNG

从图片上的解析我们可以看出来，被隐藏的字符串是啥

**strings 文件名：**将二进制代码文件转换成字符串形式

eg：下面图片

tesk2-redacted.c 是c语言，先将其进行编译（gcc命令）编译成二进制代码，再进行strings

https://software-security-1316943030.cos.ap-nanjing.myqcloud.com/lab03.PNG

# Challenge 3 - Decompiling a C Program

### 题目

> Inside lab0/task3, you will find a number-guessing C program. As the user, you have to guess a number, and if it’s correct, you get to see a secret string
>
> Using online resources, explore how to use objdump to decompile the binary. 
>
> What number do you need to input to make the program output the secret string? 
>
> You may find this short guide useful for understanding x86 assembly pneumonics. 
>
> What is the output of the program when you get the number correct?

tesk3-redacted.c内容如下

https://software-security-1316943030.cos.ap-nanjing.myqcloud.com/lab04.PNG

task3的二进制代码如下

https://software-security-1316943030.cos.ap-nanjing.myqcloud.com/lab05.PNG

我们需要猜测 argv[1]中的值，如果它的值和被作者加密（[REDACTED]）的值相等，则运行correct（）函数，打印被作者加密的字符串。

### 答案

https://software-security-1316943030.cos.ap-nanjing.myqcloud.com/lab06.PNG

先将task3二进制代码文件通过**objdump命令**进行**逆向工程**，转换成汇编语言

https://software-security-1316943030.cos.ap-nanjing.myqcloud.com/lab07.PNG

我们可以看出，在主函数中有两个cmp（比较），将他们（0x2和0xf398）转换成十进制（2和62360），运行task3代码

https://software-security-1316943030.cos.ap-nanjing.myqcloud.com/lab08.PNG

我们可以看出答案是62360

# Challenge 4 - Advance Decompiling in C Program

### 题目

> Inside lab0/task4 is another C program which is very similar to task 3. The source code is available in task4-redacted.c. The only difference is that this program doesn’t use a direct comparison to check the number, and instead uses a series of mathematical functions in a certain order. 
>
> Can you reverse engineer the check function using Objdump to determine what number to input for it to output the secret string?
>
> What string is output when you get the number correct?

和task3的任务一样，找数字，显示出内容

task4-redacted.c内容如下

https://software-security-1316943030.cos.ap-nanjing.myqcloud.com/lab09.PNG

task4文件逆向工程为汇编语言之后内容如下：

https://software-security-1316943030.cos.ap-nanjing.myqcloud.com/lab010.PNG

https://software-security-1316943030.cos.ap-nanjing.myqcloud.com/lab011.PNG

根据代码可以得出，0x78是经过一系列加减之后的结果，我们需要将这个数字逆着向上运算，计算出最开始的代码，0x196f不需要计算，因为他是将数字加入到了%eax内存上，其他都是在%ebp上。

运算之后，答案是44

https://software-security-1316943030.cos.ap-nanjing.myqcloud.com/lab012.PNG
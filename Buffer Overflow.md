# 定义

是针对程序设计缺陷，向程序输入缓冲区写入使之溢出的内容（通常是超过缓冲区能保存的最大数据量的数据）从而破坏程序运行并取得程序乃至系统的控制权。缓存溢出原指当某个数据超过了处理程序限制的范围时，程序出现的异常操作

# 例子

https://software-security-1316943030.cos.ap-nanjing.myqcloud.com/Buffer%20Overflow1.png

https://software-security-1316943030.cos.ap-nanjing.myqcloud.com/Buffer%20Overflow2.png

https://software-security-1316943030.cos.ap-nanjing.myqcloud.com/Buffer%20Overflow3.png

如果放544个字，就会溢出

破坏CIA的availability

I lost the availability property of the program since with a specific string longer than 511 character I can make it crash!

512（511个字加结束符）
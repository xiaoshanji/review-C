![](image/QQ截图20190823084649.png)

​			粗体是C90标准新增的关键字，斜体表示C99标准新增的关键字，粗斜体表示是C11标准新增的关键字。

![](image/QQ截图20190823101714.png)

## 数据类型

![](image/QQ截图20190824105205.png)

​		 _ Bool类型表示布尔值， _ complex和_Imaginary分别表示复数和虚数。

​	

​		位：最小的存储单元（bit），可以存储0和1。

​		字节：常用的计算机存储单位，1字节均为8位。字节的标准定义。

​		字：设计计算机时给定的自然存储单位，对于8位的微型计算机1个字长只有8位。

## 显示

​		%d：十进制

​		%o：八进制

​		%x：十六进制

​		如要显示进制前缀则用对应的%#d，%#o，%#x。显示转换时后缀只能小写。即：%ld，%lo，%lx。

​	

​		把一个类型的数据初始化给不同类型的变量时，编译器会把值装换成与变量匹配的类型，这将导致数据丢失。

## 字符串和格式化输入/输出

```c++
#include <stdio.h>
#include <string.h>

#define DENSITY 62.4

int main()
{
    float weight,volume;
    int size_of,letters;
    char name[40];
    printf("hi! what`s your first name?\n");
    
    //%s：字符串的输入输出格式，scanf的第二个参数是一个地址引用，因为数组名本身就是一个引用，所以不用加&符号，在存储时，存入数组的字符的数量是字符串长度+1，最后一个为“\0”，表示字符串结束符，所以字符串的最大长度应是数组长度-1
    scanf("%s",name);
    printf("%s,what`s your weight in pounds?\n",name);
    scanf("%f",&weight);
    size_of = sizeof name;
    
    //strlen函数在string.h头文件中，用于返回字符串的长度而不是存储字符串的数组的长度
    letters = strlen(name);	
    volume = weight / DENSITY;
    printf("well,%s,your volume is %2.2f cubic feet.\n",name,volume);

    printf("also,your first name has %d letters,\n",letters);

    printf("and we have %d bytes to store it.\n",size_of);


    return 0;
}
```

​		sizeof函数后面的圆括号的使用时机取决于运算对象是类型还是特定量，运算对象是类型时，圆括号必不可少，但对于特定量，可有可无。但就算如此，还是建议所有情况下都使用圆括号。



​		**const关键字：限定变量为只读。**

![](image/QQ截图20190827085753.png)

![](image/QQ截图20190827085859.png)

### 转换说明

![](image/QQ截图20190827090921.png)

![](image/QQ截图20190827095122.png)

![](image/QQ截图20190827095919.png)

![](image/QQ截图20190828113501.png)

![](image/QQ截图20190828114209.png)

![](image/QQ截图20190828114228.png)

​		scanf("%c",&m)与scanf(" %c",&m)的区别：前者从输入的第一个字符开始读，后者会跳过最开始的空格，从第一个非空字符开始读。


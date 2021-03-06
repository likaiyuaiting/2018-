#### 字符串拷贝1

```
@函数名称:   strdup
函数原型:   char *strdup(const char *s)
函数功能:   字符串拷贝，目的空间由该函数分配 
函数返回:   指向拷贝后的字符串指针
参数说明:   src-待拷贝的源字符串
所属文件:   <string.h>

#include <stdio.h>
#include <string.h>
#include <alloc.h>
int main()
{
  char *dup_str, *string="abcde";
  dup_str=strdup(string);
  printf("%s", dup_str);
  free(dup_str);
  return 0;
}
```

#### 字符串拷贝2

```
@函数名称:   strcpy
函数原型:   char* strcpy(char* str1,char* str2);
函数功能:   把str2指向的字符串拷贝到str1中去
函数返回:   返回str1,即指向str1的指针
参数说明:
所属文件:   <string.h>

#include <stdio.h>
#include <string.h>
int main()
{
  char string[10];
  char *str1="abcdefghi";
  strcpy(string,str1);
  printf("the string is:%s\n",string);
  return 0;
}
```


#### 字符串拷贝3

```
@函数名称:   strncpy
函数原型:   char *strncpy(char *dest, const char *src，int count)
函数功能:   将字符串src中的count个字符拷贝到字符串dest中去
函数返回:   指向dest的指针
参数说明:   dest-目的字符串，src-源字符串，count-拷贝的字符个数
所属文件:   <string.h>

#include <stdio.h>
#include <string.h>
int main()
{
  char string[10];
  char *str1="abcdefghi";
  strncpy(string,str1,3);
  string[3]='/0';
  printf("%s",string);
  return 0;
}
```

#### 字符串连接1

```
@函数名称:   strcat
函数原型:   char* strcat(char * str1,char * str2);
函数功能:   把字符串str2接到str1后面,str1最后的'/0'被取消
函数返回:   str1
参数说明:
所属文件:   <string.h>

#include <stdio.h>
#include <string.h>

int main()
{
  char buffer[80];

  strcpy(buffer,"Hello ");
  strcat(buffer,"world");
  printf("%s\n",buffer);
  return 0;
}
```

#### 字符串连接2

```
@函数名称:   strncat
函数原型:   char *strncat(char *dest, const char *src, size_t maxlen)
函数功能:   将字符串src中前maxlen个字符连接到dest中
函数返回:
参数说明:
所属文件:   <string.h>

#include <stdio.h>
#include <string.h>

char buffer[80];

int main()
{
  strcpy(buffer,"Hello ");
  strncat(buffer,"world",8);
  printf("%s/n",buffer);
  strncat(buffer,"*************",4);
  printf("%s/n",buffer);
  return 0;
}
```


#### 字符串比较1

```
@函数名称:   strcmp
函数原型:   int strcmp(char * str1,char * str2);
函数功能:   比较两个字符串str1,str2.
函数返回:   str1<str2,返回负数; str1=str2,返回 0; str1>str2,返回正数. 
参数说明:
所属文件:   <string.h>

#include <string.h>
#include <stdio.h>
int main()
{
  char *buf1="aaa", *buf2="bbb", *buf3="ccc";
  int ptr;
  ptr=strcmp(buf2, buf1);
  if(ptr>0)
    printf("buffer 2 is greater than buffer 1\n");
  else
    printf("buffer 2 is less than buffer 1\n");
  ptr=strcmp(buf2, buf3);
  if(ptr>0)
    printf("buffer 2 is greater than buffer 3\n");
  else
    printf("buffer 2 is less than buffer 3\n");
  return 0;
}
```


#### 字符串比较2

```
@函数名称:   strncmp
函数原型:   int strncmp(char *str1,char *str2,int count)
函数功能:   对str1和str2中的前count个字符按字典顺序比较
函数返回:   小于0：str1<str2，等于0：str1=str2，大于0：str1>str2
参数说明:   str1,str2-待比较的字符串，count-比较的长度
所属文件:   <string.h>

#include <string.h>
#include <stdio.h>
int main()
{
  int ptr;
  char *buf1="aaabbb",*buf2="bbbccc",*buf3="ccc";
  ptr=strncmp(buf2,buf1,3);
  if (ptr>0)
    printf("buffer 2 is greater than buffer 1");
  else
    printf("buffer 2 is less than buffer 1");
    ptr=strncmp(buf2,buf3,3);
  if (ptr>0)
    printf("buffer 2 is greater than buffer 3");
  else
    printf("buffer 2 is less than buffer 3");
  return(0);
}
```

#### 字符串查找1

```
@函数名称:   strpbrk
函数原型:   char *strpbrk(const char *s1, const char *s2)
函数功能:   在字符串s1中寻找字符串s2中任何一个字符相匹配的第一个字符的位置，空字符NULL不包括在内。
函数返回:   返回指向s1中第一个相匹配的字符的指针，如果没有匹配字符则返回空指针NULL。
参数说明:
所属文件:   <string.h>

#include <stdio.h>
#include <string.h>
int main()
{
char *p="Find all vowels";

while(p)
{
  printf("%s\n",p);
  p=strpbrk(p+1,"aeiouAEIOU");
}
return 0;
}
```


#### 字符串查找2

```
@函数名称:   strcspn
函数原型:   int strcspn(const char *s1, const char *s2)
函数功能:   统计s1中从头开始直到第一个“来自s2中的字符”出现的长度
函数返回:   长度
参数说明:
所属文件:   <string.h>

#include <stdio.h>
#include <string.h>

int main()
{
  printf("%d\n",strcspn("abcbcadef","cba"));
  printf("%d\n",strcspn("xxxbcadef","cba"));
  printf("%d\n",strcspn("123456789","cba"));
  return 0;
}
```


#### 字符串查找3

```
@函数名称:   strspn
函数原型:   int strspn(const char *s1, const char *s2)
函数功能:   统计s1中从头开始直到第一个“不来自s2中的字符”出现的长度
函数返回:   位置指针
参数说明:
所属文件:   <string.h>

#include <stdio.h>
#include <string.h>
#include <alloc.h>
int main()
{
  printf("%d\n",strspn("out to lunch","aeiou"));
  printf("%d\n",strspn("out to lunch","xyz"));
  return 0;
}
```


#### 字符串查找4

```
@函数名称:   strchr
函数原型:   char* strchr(char* str,char ch);
函数功能:   找出str指向的字符串中第一次出现字符ch的位置
函数返回:   返回指向该位置的指针,如找不到,则返回空指针
参数说明:   str-待搜索的字符串，ch-查找的字符
所属文件:   <string.h>

#include <string.h>
#include <stdio.h>
int main()
{
  char string[15];
  char *ptr, c='r';
  strcpy(string, "This is a string");
  ptr=strchr(string, c);
  if (ptr)
    printf("The character %c is at position: %d\n",c,ptr-string);
  else
    printf("The character was not found\n");
  return 0;
}
```

#### 字符串查找5

```
@函数名称:   strrchr
函数原型:   char *strrchr(const char *s, int c)
函数功能:   得到字符串s中最后一个含有c字符的位置指针
函数返回:   位置指针
参数说明:
所属文件:   <string.h>

#include <string.h>
#include <stdio.h>
int main()
{
  char string[15];
  char *ptr,c='r';
  strcpy(string,"This is a string");
  ptr=strrchr(string,c);
  if (ptr)
    printf("The character %c is at position:%d",c,ptr-string);
  else
    printf("The character was not found");
  return 0;
}
```


#### 字符串查找6

```
@函数名称:   strstr
函数原型:   char* strstr(char* str1,char* str2);
函数功能:   找出str2字符串在str1字符串中第一次出现的位置(不包括str2的串结束符)
函数返回:   返回该位置的指针,如找不到,返回空指针
参数说明:
所属文件:   <string.h>

#include <stdio.h>
#include <string.h>
int main()
{
  char *str1="Open Watcom C/C++",*str2="Watcom",*ptr;
  ptr=strstr(str1,str2);
  printf("The substring is:%s\n",ptr);
  return 0;
}
```

#### 字符串倒置

```
@函数名称:   strrev
函数原型:   char *strrev(char *s)
函数功能:   将字符串中的所有字符颠倒次序排列
函数返回:   指向s的指针 
参数说明:
所属文件:   <string.h>

#include <string.h>
#include <stdio.h>
int main()
{
  char *forward="string";
  printf("Before strrev():%s",forward);
  strrev(forward);
  printf("After strrev(): %s",forward);
  return 0;
}
```

#### 字符串填充1

```
@函数名称:   strnset
函数原型:   char *strnset(char *s, int ch, size_t n)
函数功能:   将字符串s中前n个字符设置为ch的值
函数返回:   指向s的指针
参数说明:
所属文件:   <string.h>

#include <stdio.h>
#include <string.h>
int main()
{
  char *string="abcdefghijklmnopqrstuvwxyz";
  char letter='x';
  printf("string before strnset: %s",string);
  strnset(string,letter,13);
  printf("string after strnset: %s",string);
  return 0;
}
```


#### 字符串填充2

```
@函数名称:   strset
函数原型:   char *strset(char *s, int ch)
函数功能:   将字符串s中所有字符设置为ch的值
函数返回:   指向s的指针 
参数说明:
所属文件:   <string.h>

#include <stdio.h>
#include <string.h>
int main()
{
  char string[10]="123456789";
  char symbol='c';
  printf("Before strset(): %s", string);
  strset(string, symbol);
  printf("After strset(): %s", string);
  return 0;
}
```

#### 字符串分解

```
@函数名称:   strtok
函数原型:   char *strtok(char *s1, const char *s2)
函数功能:   分解s1字符串为用特定分隔符分隔的多个字符串(一般用于将英文句分解为单词)
函数返回:   字符串s1中首次出现s2中的字符前的子字符串指针
参数说明:   s2一般设置为s1中的分隔字符
        规定进行子调用时（即分割s1的第二、三及后续子串）第一参数必须是NULL
        在每一次匹配成功后，将s1中分割出的子串位置替换为NULL(摘下链中第一个环)，因此s1被破坏了
        函数会记忆指针位置以供下一次调用
        
所属文件:   <string.h>

#include <string.h>
#include <stdio.h>
int main()
{
  char *p;
  char *buffer;
  char *delims={ " .," };

  buffer=strdup("Find words, all of them.");
  printf("%s/n",buffer);
  p=strtok(buffer,delims);
  while(p!=NULL){
    printf("word: %s\n",p);
    p=strtok(NULL,delims);
  }
  printf("%s/n",buffer);
  return 0;
}
```


#### 字符串大写转换

```
@函数名称:   strupr
函数原型:   char *strupr(char *s)
函数功能:   将字符串s中的字符变为大写
函数返回:
参数说明:
所属文件:   <string.h>

#include <stdio.h>
#include <string.h>
int main()
{
  char *string="abcdefghijklmnopqrstuvwxyz",*ptr;
  ptr=strupr(string);
  printf("%s",ptr);
  return 0;
}
```


#### 字符串小写转换

```
@函数名称:   strlwr
函数原型:   char *strlwr(char *s)
函数功能:   将字符串中的字符变为小写字符
函数返回:   指向s的指针
参数说明:
所属文件:   <string.h>

#include<string.h>
int main()
{
  char str[]="HOW TO SAY?";
  printf("%s",strlwr(str));
  return 0;
}
```


#### 字符串长度

```
@函数名称:   strlen
函数原型:   unsigned int strlen(char * str);
函数功能:   统计字符串str中字符的个数(不包括终止符'/0')
函数返回:   返回字符串的长度.
参数说明:
所属文件:   <string.h>

#include <stdio.h>
#include<string.h>
int main()
{
  char str[]="how are you!";
  printf("the lence is:%d\n",strlen(str));
  return 0;
}
```


#### 字符串错误

```
@函数名称:   strerror
函数原型:   char *strerror(int errnum)
函数功能:   得到错误信息的内容信息
函数返回:   错误提示信息字符串指针
参数说明:   errnum-错误编号
所属文件:   <string.h>

#include <stdio.h>
#include <errno.h>
int main()
{
  char *buffer;
  buffer=strerror(errno);
  printf("Error: %s",buffer);
  return 0;
}
```


#### 字符串拷贝

```
@函数名称:   memcpy
函数原型:   void *memcpy(void *dest, const void *src, size_t n)
函数功能:   字符串拷贝
函数返回:   指向dest的指针
参数说明:   src-源字符串，n-拷贝的最大长度
所属文件:   <string.h>,<mem.h>

#include <stdio.h>
#include <string.h>
int main()
{
  char src[]="******************************";
  char dest[]="abcdefghijlkmnopqrstuvwxyz0123456709";
  char *ptr;
  printf("destination before memcpy:%s\n",dest);
  ptr=memcpy(dest,src,strlen(src));
  if (ptr)
    printf("destination after memcpy:%s\n",dest);
  else
    printf("memcpy failed");
  return 0;
}
```

#### 字符串拷贝

```
@函数名称:   memccpy
函数原型:   void *memccpy(void *dest, const void *src, int c, size_t n)
函数功能:   字符串拷贝，到指定长度或遇到指定字符时停止拷贝
函数返回:
参数说明:   src-源字符串指针，c-中止拷贝检查字符，n-长度,dest-拷贝底目的字符串指针
所属文件:   <string.h>,<mem.h>

#include <string.h>
#include <stdio.h>
int main()
{
  char *src="This is the source string";
  char dest[50];
  char *ptr;
  ptr=memccpy(dest,src,'c',strlen(src));
  if (ptr)
  {
    *ptr='/0';
    printf("The character was found:%s",dest);
  }
  else
    printf("The character wasn't found");
  return 0;
}
```


#### 寻找某个字符

```
@函数名称:   memchr
函数原型:   void *memchr(const void *s, int c, size_t n)
函数功能:   在字符串中第开始n个字符中寻找某个字符c的位置
函数返回:   返回c的位置指针，返回NULL时表示未找到
参数说明:   s-要搜索的字符串，c-要寻找的字符，n-指定长度
所属文件:   <string.h>,<mem.h>

#include <string.h>
#include <stdio.h>
int main()
{
  char str[17];
  char *ptr;
  strcpy(str,"This is a string");
  ptr=memchr(str,'r',strlen(str));
  if (ptr)
  printf("The character 'r' is at position: %d",ptr-str);
  else
  printf("The character was not found");
  return 0;
}
```


#### 字符串比较

```
@函数名称:   memcmp
函数原型:   int memcmp(const void *s1, const void *s2,size_t n)
函数功能:   按字典顺序比较两个串s1和s2的前n个字节 
函数返回:   <0,=0,>0分别表示s1<,=,>s2
参数说明:   s1,s2-要比较的字符串，n-比较的长度
所属文件:   <string.h>,<mem.h>

#include <stdio.h>
#include <string.h>
int main() 
{ 
  char *buf1="ABCDE123"; 
  char *buf2="abcde456"; 
  int stat; 
  stat=memcmp(buf1,buf2,5); 
  printf("The strings to position 5 are "); 
  if(stat) printf("not "); 
  printf("the same/n"); 
  return 0; 
}
```


#### 字符串比较

```
@函数名称:   memicmp
函数原型:   int memicmp(const void *s1, const void *s2, size_t n)
函数功能:   按字典顺序、不考虑字母大小写对字符串s1,s2前n个字符比较
函数返回:   <0,=0,>0分别表示s1<,=,>s2
参数说明:   s1,s2-要比较的字符串，n-比较的长度
所属文件:   <string.h>,<mem.h>

#include <stdio.h>
#include <string.h>
int main()
{
  char *buf1="ABCDE123";
  char *buf2="abcde456";
  int stat;
  stat=memicmp(buf1,buf2,5);
  printf("The strings to position 5 are ");
  if(stat) printf("not");
  printf("the same");
  return 0;
}
```


#### 字符串拷贝

```
@函数名称:   memmove
函数原型:   void *memmove(void *dest, const void *src, size_t n)
函数功能:   字符串拷贝
函数返回:   指向dest的指针
参数说明:   src-源字符串，n-拷贝的最大长度
所属文件:   <string.h>,<mem.h>

#include <string.h>
#include <stdio.h>
int main()
{
  char dest[40]="abcdefghijklmnopqrstuvwxyz0123456789";
  printf("destination prior to memmove:%s/n",dest);
  memmove(dest+1,dest,35);
  printf("destination after memmove:%s",dest);
  return 0;
}
```

#### 字符串设置

```
@函数名称:   memset
函数原型:   void *memset(void *s, int c, size_t n)
函数功能:   字符串中的n个字节内容设置为c
函数返回:
参数说明:   s-要设置的字符串，c-设置的内容，n-长度
所属文件:   <string.h>,<mem.h>

#include <string.h>
#include <stdio.h>
#include <mem.h>
int main()
{
  char buffer[]="Hello world";
  printf("Buffer before memset:%s\n",buffer);
  memset(buffer,'*',strlen(buffer)-1);
  printf("Buffer after memset:%s",buffer);
  return 0;
}
```

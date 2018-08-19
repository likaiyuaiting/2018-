###### C++中有getline（），在string头文件下
##### 用法 ：

```
string  str；
getline （cin,str）
```

stringstream流的输入输出操作，istringstream流的输入操作，ostringstream流的输出操作(sstream头文件下）
###### 如：输入字符串，按空格分割  

```
# include <iostream>
#include <sstream>
# include<string.h>
using namespace std;
int main()
{
    string line;
    while(getline(cin,line))
    {
        string x;
        stringstream ss(line);//在line中进行输入输出
        while(ss>>x)//空格暂停，eof结束
        cout<<x<<endl;
    }
   return 0;
}
```

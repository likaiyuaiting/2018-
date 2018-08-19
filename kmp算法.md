
```
具体内容跳至csdn博客
链接：https://blog.csdn.net/Cassie_zkq/article/details/81564613
最终的kmp算法：
#include <iostream>
#include <cstring>
using namespace std;
#define maxn 100000//如果数组定义在main内，不能开太大
int main()
{
    char s1[maxn],s2[maxn];//s1文本串，s2模式串
    scanf("%s%s",s1+1,s2+1);
    int i,j,k,len1=strlen(s1+1),len2=strlen(s2+1);
    int next[maxn],nextval[maxn];
    next[1]=0;
    j=1,k=0;
    while(j<len2)
    {
        if(k==0||s2[j]==s2[k])
        {
            k++;
            j++;
            next[j]=k;
        }
        else k=next[k];
    }
    j=2;k=0;
    while(j<=len2)
    {
        k=next[j];
        if(s2[j]==s2[k])
            nextval[j]=nextval[k];
        else nextval[j]=next[j];
        j++;
    }
    i=1;j=1;//i指文本串，j指模式串
    while(i<=len1&&j<=len2)
    {
        if(j==0||s1[i]==s2[j])
        {
            i++;
            j++;
        }
        else j=nextval[j];
    }
    if(j>len2) cout<<i-len2<<endl;
    else cout<<"-1"<<endl;
    return 0;
}
```



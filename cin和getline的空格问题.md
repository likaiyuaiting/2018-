代码 如下:
int a[3];
	for(int i=0;i<3;i++)
	 cin>>a[i];
	 for(int i=0;i<3;i++)
	  cout<<a[i];
输入 ：1                   2                3
输出 ：123
空格 不是int型所以不会作为a[i]的值，只是间隔作用
int a;
cin>>a;
string s;
getline(cin,s);
输入 ：123 adsadsa
则 s会读取a前面的空格作为第一个元素
![image](https://github.com/zhangkanqi/SUANFA-notes/blob/master/photo.png)
 

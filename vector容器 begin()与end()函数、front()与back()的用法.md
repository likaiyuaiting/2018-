简单 来说begin（），end（）输出元素是需要加指针运算符（用迭代器访问元素）
代码 示例：


#include <iostream>  
#include <vector>  
using namespace std;  
int main()  
{  
    vector<char> v1;  
    vector<char>::iterator iter1;  
    vector<char>::iterator iter2;  
    v1.push_back('m');  
    v1.push_back('n');  
    v1.push_back('o');  
    v1.push_back('p');  
   
    cout << "v1.front() = " << v1.front() << endl;  
    cout << "v1.back() = " << v1.back() << endl;  
   
    iter1 = v1.begin();  
    cout << *iter1 << endl;  
    iter2 = v1.end()-1; //注意v1.end()指向的是最后一个元素的下一个位置，所以访问最后一个元素  
                        //的正确操作为：v1.end() - 1;  
    cout << *iter2 << endl;  
    return 0;  
}  
输出结果：
v1.front() = m
v1.back() = p
m
p

#include<iostream>
#include<string>
using namespace std;
class String
{
private:
int length; char str[100];
public:
String(const char* s = " ")
{
strcpy_s(str, s);
length = strlen(str);
}
void display()
{
cout << "字符串为：" << str << endl;
}
int getLength()
{
return length;
}
void strlink(String s)
{
strcat_s(str, s.str);
length = s.length + length;
}
};
int main()
{
String str1("13567"), str2("24658");
cout << "两个字符串str1,str2：" << endl;
str1.display();
str2.display();
cout << "字符串的长度为：" << str1.getLength() << "  "
<< str2.getLength() << endl;
str1.strlink(str2);
cout << "两个字符串连接后的长度为:"
<< str1.getLength() << endl;
return 0;
}
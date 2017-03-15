# C++-learning-summary
string learning and common forms
1. 关于字符串三种形式   
sizeof()函数：返回某个类型的长度，单位是字节。
strlen()函数：它从内存的某个位置（可以是字符串开头，中间某个位置，甚至是某个不确定的内存区域）开始扫描，直到碰到第一个字符串结束符'\0'为止，然后返回计数器值(长度不包含'\0')。
（1）char* a1;
sizeof(a1)=4, strlen(a1)=0。

（2）char* a2=new char[3];
sizeof(a2)=4, strlen(a2)=随机。若加入memset(a2, 0, 3); 语句，则strlen(a2)=0.

（3）char a3[]="abc";
sizeof(a3)=4(多算一位\0), strlen(a3)=3.

（4）char a4[3]={0};
sizeof(a4)=3, strlen(a4)=0.

2. 函数返回字符串及调用
函数中返回：
char* getchars()
{
    char* words=new char[WORD_LENGTH];
    memset(words, 0, WORD_LENGTH);//初始化为空指针
    char word_0[]="LOVE";
    char word_1[]="ZHUZHU";
    strcpy(words, word_0);//在word[0]的位置后赋值
    strcpy(words+10, word_1);//在word[10]的位置后赋值
	
    return words;
}
函数外调用：
char* words;
words=getchars();

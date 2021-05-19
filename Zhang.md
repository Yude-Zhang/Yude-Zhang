- 👋 Hi, I’m @Yude-Zhang
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Yude-Zhang/Yude-Zhang is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
#include<stdio.h>
/*分鱼递归函数*/
int fish(int n, int x)
{
    if((x-1)%5 == 0)
    {
        if(n == 1)
            return 1;  /*递归出口*/
        else
            return fish(n-1, (x-1)/5*4);  /*递归调用*/
    }
    return 0;  /*x不是符合题意的解，返回0*/
}
int main()
{
    int i=0, flag=0, x;
    do
    {
        i=i+1;
        x=i*5+1;  /*x最小值为6，以后每次增加5*/
        if(fish(5, x))  /*将x传入分鱼递归函数进行检验*/
        {
            flag=1;  /*找到第一个符合题意的x则置标志位为1*/
            printf("五个人合伙捕到的鱼总数为%d\n", x);
        }
    }
    while(!flag);  /*未找到符合题意的x，继续循环，否则退出循环*/
    return 0;
}

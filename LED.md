# LED

## 程序的编写  

    #include<reg52.h> //包括特殊功能寄存器定义的头文件  
    sbit LED = P2^3; //位地址的声明  
    void main()  
    {  
        LED =0  //1代表高电平，0表示低电平  
    }  

改进  
    
    #include<reg52.h>  
    sbit LED =P2^3;  
    void main()  
    {  
        while(1); //防止不能结束循环
        LED =0; 
    }
或  

     #include<reg52.h>  
     sbit LED = P2^3;  
      {  
         LED =0;  
        while(1);    
       }  

## 延迟函数  
1.短暂延迟：  
例如10 μs：  

    void Dalay10μs()  
    {  
        _NOP_();  
        _NOP_();  
        _NOP_();  
        _NOP_();  
        _NOP_();  
        _NOP_();  
    }  

2.循环空语句延时  
例如1ms延迟：  

    void delay_ms(int n)  
    {  
        int i,j;  
        for(i=0;i<1;i++)  
        {   
            for(j=0;j<123;j++);  
        }  
    }  

3.综合：  

    void Dalay1ms()  
    {  
    unsigned char i,j;  
    _nop_();    
    i=2;  
    j=199;  
    do  
    {  
        while(--j);    
    }while(--i);  
    }  
  
## 闪烁灯
原理图：  

    #include<reg52.h>  
    sbit LED =P2^3;  
    void delay_ms(int 2)  //延时函数，大概2 ms  
    {  
        int i,j;  
        for(i=0;i<2;i++)  
        {  
            for(j=0;j<123;j++);  
        }  
    }  
    void main()  
    {  
        while(1)  
        {  
            LED =1;  
            delay_ms(10);  
            LED=0;  
            delay_ms(10);  
        }  

## 流水灯  
代码：  

    #include<reg52.h>  
    #define uchar unsigned char   //对数据类型进行声明定义  
    #define uchar unsigned char   //对数据类型进行声明定义  

    void delay(uint n)  //延时n ms  
    {
        uchar i,j;
        for(i=0;i<n;i++)  
        {  
            unchar i,j;  
            for(i=0;i<n;i++)  
            {  
                for(j=0;i<n;i++)  
            }  
        }
    }  
    void main()  
    {  
        P1=0x00;  //初始化P1端口
        delay(200);  
        P1=0x02;  
        delay(200);  
        P1=0x04;  
        delay(200);  
        P1=0x04;
        delay(200);  
        P1=0x08;  
        delay(200);  
        P1=0x10；  
        delay(200);  
        P1=0x20;  
        delay(200);  
        p1=0x40;  
        delay(200);    
        P1=0x80;
        delay(200);
    }  





    



# FunnyStory
有趣的东西
#一个有趣的算法题目
  有15个瓶子，现在有四只老鼠，喝了有毒的水之后，第二天就会死。问，如何在第二天就可以判断出哪个瓶子有毒。
  
### 思路
  给15个瓶子编号，1到15，给老鼠的生存状态编号，0是第二天活着，1表示第二天该只老鼠死了。给老鼠编号1234.
  随意拿一个瓶子给老鼠喝，假设 四只老鼠占四个位置 1 2 3 4
  
  分配瓶子的话 是这样分的，按照每个瓶子转成二进制的1的位置喝。比如，0001 就是四号老鼠喝1号瓶子，0010就是3号老鼠喝2号瓶子。
  依次类推。会得到不会交叉的一个子集。通过排除法就能知道那个瓶子是有毒的。看老鼠都喝了那一瓶，那一瓶就有毒。
  
  分配方案
        老鼠1        老鼠2        老鼠3      老鼠4 

         0001(1)                                     1000(8)
         0011                                     1001(9)
         0111                                     1010(10)
         1011                                     1011(11)
         1001                                     1100(12)     
         1101                                      1101(13)
         1111                                       1110(14)
                                                   1111(15)


  
  
  
  二进制       十进制
  0000    =   0不需要
  
  0001    =   1
  0010    =   2
  0100    =   3
  1000    =   4
  0101    =   5
  
   
  1111 = 16也不需要
  
  
  最后的求解是 根据死去的老鼠的位数确定那一瓶有毒
  例如 死去的是 3号 其他都没死。 就是。0100。那就是 4号瓶子有毒。
  

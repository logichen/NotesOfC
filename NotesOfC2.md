* 用递归解决汉诺塔问题的解释

    every different time,the meaning is
    combined with the position of  variable,rather than the names
    given in the first time.only in the first time,left means start,
    mid means helper,right means goal.when we go into the second time,
    left means start,right means helper,mid means goal.we've known
    that it is true that we can solve the 'n' problem.so we can also solve
    the n-1 problem by the similar way.the left,mid,right are the same
    in logical,in hanoi(k,*,#,@),no mater what name it is,* is always
    the start,@ is always the goal,and we can always make the plates
    shift from start to goal in a same way.if we use name by meaning,
    every time,no matter what n is or which time is in the recursive,
    function hanoi is always this:
      hanoi(k,left, mid,   right) {         //use name by meaning it is hanoi(k,start,helper,goal)
        if(...){
        ...}else {hanoi(k-1,left,right,mid);//use name by meaning it is hanoi(k-1,start,helper,goal)
        move(left,right);                    //use name by meaning it is move(start,goal);
        hanoi(k-1,mid,left,right);           //use name by meaning it is hanoi(k-1,start,helper,goal)
        }
      }
    when we go into hanoi(k-1,mid,left,right),the meaning is also hanoi(k-1,start,helper,goal),but now
    it is mid->right,rather than left->right as the last time.
    then because the older transfer of position in k is correct,it can lead us into k-1 with
    no mistake,for k-1,mid,left,right,we can believe the same way can lead us into k-2 correctly,
    no matter what place the plates finally arrive in this time.there may be a question:we can use
    this method until k=2,k-1=1,then the next time,we go to 'if',execute k=1.in k=1,it may be move
    mid to right or other situation,not the same with we writen down in our code.but the code k==1
    just mean when k==1 we can act as that,it doesn't mean when we need to solve k problem,the first
    step is in that way.


* 内存模型的核心
  * 为每个函数开辟一块空间a，用来存变量的值。再开辟一块空间b，用来存各变量的地址。
  * 当在函数内部定义一个变量时,为该变量在该函数的空间a内开辟一小块固定的空间存储。
  * 在另外一个函数内部定义的变量,即便另一个函数调用了该函数,若变量未作为参数传入,对于该函数而言这些变量相当于没有定义.不同函数内定义的同名变量，在不同函数的空间a内都要重复存储，并且相互独立。
  * 若采取这样的定义,使得这个定义对于两个函数而言,都在函数外部,则这个变量可以被两个函数共用,并产生相互作用.但是如果在某函数内部重新定义了该变量,则在该函数内部为该名字的变量分配新的空间,该函数结束,空间作废.能影响另一函数的只是在它们两个函数之外定义的那个变量,或者当该函数调用了另一函数,将这个变量作为参数传入另一个函数,也可以影响另一个函数.
  * 一个被调用的函数能够影响另一个函数的变量的方式是:1.指针. 2.return
  * 主函数通过参数给被调用函数信息,被调用函数通过指针和return给主函数信息。
  * 参数


*  级联的if-else
        if(...) {
          ...
        }else if(...) {
          ...
        }else {
          ...
        }

  equivalent to:
       if(...) {
         ...
       }else {
           if(...) {
           ...
         }else {     //在满足第一个else的条件下,对于第二个if的else,
                    //等同于既非第一个if,也非第二个if的情形.
           ...
         }
       }


* &与\*
  * &:取变量的地址
  * \* :取地址的值


* const与*
  * const 在 \* 前面:1.\*p是const,不能修改\*p.
  2.可以修改i.3.可以修改p(即可以使p=&j;p++;)
    * (const int\* p=&i;)   equivalent to : (int const* p=&i;)
  * const在\*后面,即int\* const p=&i:1.指针p是一个const,不能再指向其他变量的地址,不能对p进行p++之类的运算.2.可以修改i.3.可以修改\*p.





* \*与++优先级相同.因此按先左后右的顺序进行.
    * \*p++ equivalent to \*(p++) 表示先取\*p 然后p++，而不是(\*p)这个数值++.
    *　而*(++p)表示先让p+1,然后取新的\*p


* 两个指针之差是两个指针之间元素的个数

* %s:
  * scanf("%s",pointer) 与gets(pointer)不同,使用前者,计算机只能获取第一个空格前的单词.而后者可以获得按回车前的整个句子
  * printf("%s",pointer) 可以输出多个单词组成的句子

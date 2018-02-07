# C中的三大运算
## 概念
* 语句<br>
这里把语句定义为可判断真假的陈述.
* 操作符<br>
  操作符使式子或语句输出一个结果.可以是真假或数值.
* 算术运算<br>
Arithmetic operation is an operation between numbers,
which input numbers and output numbers.
For example,the four fundamental operations of mathematics,
add,substract,multiply and divide.

* 关系运算<br>
Relational operations is an operation to judge whether
a relationship between numbers' value is ture or not.The
 relationships here means something as >,>=,==.We input a
expression such as a>b ,a==b and the operation output true
or false which is a logical symbol.But we can also use 1 to
express true and 0 to express false.

* 逻辑运算<br>
Logical operation is an operation between sevaral sentences
or expressions which can be judged as true or false.It based
on three fundamental logical relationship:
1.and.2.or.3.not.
I guess these three can be assembled to show any relationship
of logic.And it also ouput true or false.
* 总体优先级

  算术关系逻辑赋值



## 算术运算
* 种类:
  * 基本:+,_,*,/,%,fmod.
  * 次幂:a的b次方pow(a,b),二次方根:sqrt(a).
  * 对数:以e为底:log(double),以10为底:log10(double).
  * 指数:e的b次幂:exp(b).

* i++与++i与i+=1
  * i=5;t=i++,output t=5,i=6.
  * t=++i,ouput t=6,i=6.
  * i+=1,ouput i=6.
  * printf i++,output 5
  * printf ++i,output 6

## 关系运算
* 运算符的优先级
  * 后算:
    * ==
    * !=
  * 先算:
    * >
    * <=之类
  * 在以上之前算:
    * *,/,%
    * +,-
  * 即:`死则大笑瞪不得`

    (四则大小等不等)
* 异形但合法的关系表达式:
  * 由优先级导致的异形:
    * c<=a+b等价于:c<=(a+b).
    * a==b>=c等价于:先判断b>=c,若为真,b>=c这个式子表示1,若为假
    表示0.当b>=c,判断a==1是否成立,若成立,最终输出1,若不成立
    输出0;当b>=c,判断a是否等于0.
    * a=b>c:先判断b>c的真假,若真,则(b>c)==1,否则为0.然后将1或0
    赋值给a.

## 逻辑运算
* 优先级Practice:

  a=3,b=4,c=5;
  output the value of the following expressions:
    * a+b>c&&b==c

    等价于:

    1,((a+b)>c) 输出1.

    2,b==c输出0.

    3,1&&0输出0.
    * ! (x=a)&&(y=b)&&!(a+b)-2*c

    等价于:

    1,x=a输出1;y=b输出1;!(a+b)输出0

    2,!(x=a)输出0,!(a+b)-2*c即0-10,输出1

    3,0&&1&&1

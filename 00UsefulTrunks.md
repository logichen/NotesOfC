# Useful Trunks in C
* 求和:
  sum=sum+term;

* 阶乘:
  fac=fac*i;
* 交换两个数字
  temp=a;
  a=b;
  b=temp;
* 找出数组中的最小元素的位置  
      for(j=i+1;j<size;j++) {
        if(a[j]<a[min]) {
          min=j;
        }
      }
* 从i开始，所有数组元素后移一位，
      temp1=a[i];
      a[i]=insert or whatever u want;
      for(j=i+1;j<11;j++) {
        temp2=a[j];
        a[j]=temp1;
        temp1=temp2;
      }
* 空转的循环
      for(i=0;str1[i]==str2[i]&&str1[i]!='\0';i++) {
      }
* 递归=溯源+递推
* 涉及字符串复制的操作,在复制完之后须加上:  b[j]='\0';
* 在字符串中,对单词的开始或结束判定是由前一个字符和当前字符共同决定的.前一个不是alphabet,
当前是,则单词开始.前一个是alphabet,当前不是,则单词结束.前一个是alphabet,当前也是,则在当前单词内部.
前一个不是,现在也不是,则处于多个空格或标点内部.
    * 要如何在转瞬即逝的扫描中获得前一个的信息呢?
      * 对每次扫描增设一个变量,用来标识当前是字母还是其他.对于下一次扫描,就可以根据这个标识来判断上一个是什么.
      * 例一,统计一句话中有多少单词:

            int main() {
              int i,prespace=1,cnt_word=0;
              char str[50],c;
              gets(str);
              for(i=0;(c=str[i])!='\0';i++) {
                if(c==' ') {
                  prespace=1;
                }else if(prespace==1) {
                  cnt_word++;
                  prespace=0;
                }if(prespace==0) {
                  prespace=0;
                }
              }
              printf("%d\n",cnt_word );
              return 0;
            }
      * 例二,输出最长的单词:


* 若第n项可以用第n-1项表示,则可以使用同一个变量的更新来表示这种关系.
  * 即若数学上Sn=f(Sn-1),则计算机中的赋值语句为Sn=f(Sn)

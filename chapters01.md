# 第一章

* 1.1.1：编译器与解释器的区别？
  			其主要区别在于，编译器只完成从源代码到目标代码的编译。而解释器对源代码边解释边执行，且逐语句地完成解释工作。



* 1.1.2：编译器与解释器的优缺点？

  ​		编译器编译后生成的文件经过的编译器的优化，其执行效率更高，但是可移植性较差。解释器工作时边解释执行，其执行效率更低，执行时间有时可与编译后文件相差几个数量级，但是它只依赖于解释环境，所以可移植性更好。



* 1.1.3：编译器产生汇编语言而非机器语言的好处？
  			相对来说，汇编语言便于输出和调试。



* 1.1.4：对于从源到源的翻译器，为何使用C语言作为目标程序？
  			C语言的发展由来已久，几乎各大平台都有对它的支持。对比汇编语言，C语言的抽象更高级，理解和使用更方便。相对于其他高级语言来说，C语言的实现更接近底层，执行效率更高。



* 1.1.5：汇编器的任务？
  		将汇编程序作为输入，产生可重定位机器代码。



* 1.3.1：语言分类。
  （1）强制式：C，C++，Java
  （2）声明式：ML
  （3）冯-诺依曼式：C，Fortran
  （4）面向对象：C++，Java
  （5）函数式：ML，Lisp
  （6）第三代：Cobol，Fortran，C，C++，Java，VB
  （7）第四代：SQL
  （8）脚本语言：Python，VB，Perl



* 1.6.1：分析以下代码，指出赋给w, x, y, z的值。

  ```c
  int w, x, y, z;
  int i=4; int j=5;
  {
      int j=7;
      i=6;
      w=i+j;
  }
  x=i+j;
  {
      int i=8;
      y=i+j;
  }
  z=i+j;
  ```

  ​		w的值为13；x的值为11；y的值为13；z的值为11；



* 1.6.2：分析以下代码，指出赋给w, x, y, z的值。

  ```c
  int w, x, y, z;
  int i=3; int j=4;
  {
      int i=5;
      w=i+j;
  }
  x=i+j;
  {
      int j=6;
      i=7;
      y=i+j;
  }
  z=i+j;
  ```

  ​		w的值为9；x的值为7；y的值为13；z的值为11；



* 1.6.3：分析以下代码，在常规声明静态作用域规则下，给出12个声明中每一个的作用域。

  ```c
  {
      int w, x, y, z;			/*块B1*/
      {
          int x, z;			/*块B2*/
          {
              int w, x;		/*块B3*/
          }
      }
      {
          int w, x;			/*块B4*/
          {
              int y, z;		/*块B5*/
          }
      }
  }
  ```

  ​		第2行的w：块B1、块B2；

  ​		第2行的x：块B1；

  ​		第2行的y：块B1、块B2、块B3、块B4；

  ​		第2行的z：块B1、块B4；

  ​		第4行的x：块B2；

  ​		第4行的z：块B2、块B3；

  ​		第6行的w：块B3；

  ​		第6行的x：块B3；

  ​		第10行的w：块B4、块B5；

  ​		第10行的x：块B1、块B4；

  ​		第12行的y：块B5；

  ​		第12行的z：块B5；



* 1.6.4：分析以下代码，给出其打印结果。

  ```c
  #define a (x+1)
  int x=2;
  
  void b(){
      x=a;
      printf("%d\n",x);
  }
  
  void c(){
      int x=1;
      printf("%d\n",a);
  }
  
  void main(){
      b();
      c();
  }
  ```

  ​		输出应为3，2；


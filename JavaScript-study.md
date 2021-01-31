#                    JavaScript学习笔记

#### JS语法与变量

1. **JS的书写位置：**

   1. 在<body>中<script>标签，在内部写代码
   2. 将代码单独保存为**.js**文件，然后在HTML文件中，使用<script src=""></script>引入

2. **输入输出：**

   1. alert():弹出警告框   （内置函数，字符串用引号包裹）
   2. console.log():控制台输出，可以测试
   3. document.write():页面输出
   4. 输入：prompt(' ')

3. **多行一起注释===ctrl+/**

4. **学会处理报错**

   1. Uncaught SyntaxError: Invalid or unexpected

      未被捕获的语法错误：   不合法或错误的符号

   2. Uncaught ReferenceError: ** is not defined

      未捕获的引用错误：  **未被定义

5. **控制台也是一个REPL环境，可以使用它临时测试表达式的值**

   1. read读----eval执行----print打印----loop循环

6. ```
   var a = 5;
   console.log(a); //5 变量不能加引号
   ------------------------------------------
   var a = 10; //定义变量a并赋初值为10
   a = 19; //更改变量a的值为19
   console.log(a);//19
   ```

7. **变量的合法命名**

   1. 只能由字母、数字、下划线、$组成，不能以数字开头

   2. 不能是关键字或保留字

   3. 变量名大小写敏感

   4. **变量命名法**：

      1. 驼峰命名法：mathTestScore
      2. C风格：math_test_score
      3. 匈牙利命名法：iMathTestScore-----i表示变量类型是整型

   5. **变量的默认值：undefined**

      1. ```
         var a;
         console.log(a);//undefined
         a = 10;
         console.log(a);//10
         ```

      2. 变量声明提升-------**JS的特性**

         提前使用一个稍后才声明的变量而不会引发异常

         只提升定义，不提升值

         ```
         console.log(a); //只提升 var a
         var a = 10;   //变量为undefined
         console.log(a);//10
         
         ```

#### **JS基本数据类型**

1. 基本数据类型   2.复杂数据类型

2. typeof运算符，可以检测值，或变量的类型

   ```
   typeof 5;//number
   typeof '慕课网';//string
   ```

3. ![基本数据类型](C:\Users\11869\Desktop\JavaScript-study\images\基本数据类型.png)

4. **Number(数字)类型**

   1. 只要是数字就是Number类型

   2. 0可省略，0.8--.8

   3. **科学计数法**

      1. $$
         3e8 = 3*10^{8} = 300000000
         $$

         $$
         3e-4 = 3*10^{-4} = 0.0003
         $$

   4. **不同进制的数字**

      1. 二进制
         1. 0b10--2
         2. 0b111--15
      2. 8进制
         1. 017--15
      3. 16进制
         1. 0xf--15

5. 一个特殊的数字值NaN---NaN是英语“not a number”的意思，即“不是一个数”，但它是一个数字类型的值。

   typeof NaN; //number

   **若结果不能得到数字，就是NaN**
   $$
   不自等：NaN \neq NaN
   $$

   $$
   false: NaN==NaN
   $$

6. **string(字符串)类型**

   1. **字符串的拼接**

      1. 加号可以用来拼接多个字符串

         ‘imo’ + 'oc' =imooc

      2. 字符串和变量的拼接

         ```
         var year = 2020;
         var str = "北京冬奥会在" + year + "年召开";
         输出==北京冬奥会在2020年召开
         ```

      3. 空字符串

         ```
         var str = "";
         //字符串的length属性
         "我喜欢js".length; //长度为5
         ```

   2. **字符串的常用方法**

      1. charAt()方法


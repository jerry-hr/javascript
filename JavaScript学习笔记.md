#                    JavaScript学习笔记

#### JS语法与变量

1. JS的书写位置：

   1. 在<body>中<script>标签，在内部写代码
   2. 将代码单独保存为**.js**文件，然后在HTML文件中，使用<script src=""></script>引入

2. 输入输出：

   1. alert():弹出警告框   （内置函数，字符串用引号包裹）
   2. console.log():控制台输出，可以测试
   3. document.write():页面输出
   4. 输入：prompt(' ')

3. 多行一起注释===ctrl+/

4. 学会处理报错

   1. Uncaught SyntaxError: Invalid or unexpected

      未被捕获的语法错误：   不合法或错误的符号

   2. Uncaught ReferenceError: ** is not defined

      未捕获的引用错误：  **未被定义

5. 控制台也是一个REPL环境，可以使用它临时测试表达式的值

   1. read读----eval执行----print打印----loop循环

6. ```
   var a = 5;
   console.log(a); //5 变量不能加引号
   ------------------------------------------
   var a = 10; //定义变量a并赋初值为10
   a = 19; //更改变量a的值为19
   console.log(a);//19
   ```

7. 变量的合法命名

   1. 只能由字母、数字、下划线、$组成，不能以数字开头

   2. 不能是关键字或保留字

   3. 变量名大小写敏感

   4. 变量命名法：

      1. 驼峰命名法：mathTestScore
      2. C风格：math_test_score
      3. 匈牙利命名法：iMathTestScore-----i表示变量类型是整型

   5. 变量的默认值：undefined

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


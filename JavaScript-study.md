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

      2. **变量声明提升**-------**JS的特性**(预解析)

         提前使用一个稍后才声明的变量而不会引发异常

         只提升定义，不提升值

         ```
         console.log(a); //只提升 var a
         var a = 10;   //变量为undefined
         console.log(a);//10
         
         ```

#### **JS基本数据类型**

2. typeof运算符，可以检测值，或变量的类型

   ```
   typeof 5;//number
   typeof '慕课网';//string
   ```

3. ![基本数据类型](C:\Users\11869\Desktop\JavaScript-study\images\基本数据类型.png)

4. **Number(数字)类型**

   1. 只要是数字就是Number类型

   2. 0可省略，0.8=.8

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

   typeof  NaN; //number

   **若结果不能得到数字，就是NaN**
   $$
   不自等：NaN \neq NaN
   $$

   $$
   false: NaN==NaN
   $$

5. **string(字符串)类型**

   1. **字符串的拼接**

      1. 加号可以用来拼接多个字符串

         'imo' + 'oc' =imooc

      2. 字符串和变量的拼接

         ```
         var year = 2020;
         var str = "北京冬奥会在" + year + "年召开";
         输出==北京冬奥会在2020年召开
         ```

      3. 空字符串

         ```
         var str = "";
         ```
         
      4. 字符串的length属性

         ```
         "我喜欢js".length; //长度为5
         ```

   2. **字符串的常用方法**

      1. **charAt()方法**===可返回指定位置的字符

         ```
         '我喜欢js'.charAt(3); //j
         '我喜欢js'.charAt(6); //''没有第6位，所以为空
         ```

      2. **substring(a,b)方法**===得到从a开始到b结束（不包括b）的子串

         ```
         '我喜欢js'.substring(3,5); //js (3,5和5,3会自动调整顺序为3，5)
         '我喜欢js'.substring(1); //喜欢js (如果省略第二个参数，将默认到结尾)
         ```

      3. **substr(a,b)方法**===得到从a开始长度为b的子串

         ```
         '我喜欢js,也喜欢HTML'.substr(3,2); //js
         '我喜欢js,也喜欢HTML'.substr(-4,2); //HT a可以为负数，表示倒数位置(当第二个参数为负数时，返回空字符串)
         			   -2-1
         ```
         
      4. **slice(a,b)方法**===得到从a开始到b结束（不包括b）的子串

         ```
         '我喜欢js'.slice(2,3); //欢
         '我喜欢js'.slice(-3,-1); //欢j a可以为负数(a必须小于b)
         ```

      5. **toUpperCase()转为大写** 

         ```
         'i love you'.toUpperCase(); //I LOVE YOU
         ```

      6. **toLowerCase()转为小写**

         ```
         'IMOOC'.toLowerCase();//imooc
         ```

      7. **indexOf()方法**===返回某个指定的字符串值在字符串中首次出现的位置，如果要检索的字符串值没有出现，则返回-1

         ```
         'abcdeb'.indexOf('a'); //0
         'abcdeb'.indexOf('de'); //3
         'abcdeb'.indexOf('f'); //-1
         ```

6. **Boolean类型**       true      false

7. **Undefined类型** == 又是类型，又是值

   变量声明提升的情况

   在变量提升时，变量的值也是undefined

   ```
   console.log(a); //undefined
   console.log(typeof a); //undefined
   var a = 10; //此时a的值是undefined  (预解析)
   ```

8. **Null类型**===null表示“空”，它是空对象

   当我们需要将对象销毁，数组销毁或删除事件监听时，通常将它们设置为null

9. **数据类型的转换**

   ​	`其他值-------数字`

   1. **Number()函数**

      ```
      Number('123'); //123
      Number('123.4'); //123.4
      Number('23年'); //NaN (结果不是数字就是NaN)
      Number('2e3'); //2000
      Number(''); //0
      Number(true); //1
      Number(false); //0
      Number(undefined); //NaN
      Number(null); //0
      ```

   2. **parseInt()函数**===将字符串转为整数，将自动截掉第一个非数字字符后的所有字符

      ```
      parseInt('3.14'); //3
      parseInt('3.14是圆周率'); //3.14
      parseInt('圆周率是3.14'); //NaN (如果不是数字开头，就是NaN)
      ```

   3. **parseFloat()函数**===将字符串转为浮点数

      ```
      parseFloat('3.14'); //3.14
      parseFloat('3.14是圆周率'); //3.14
      parseFloat('圆周率是3.14'); //NaN
      parseFloat('3.99'); //3.99
      parseFloat(true); //NaN
      parseFloat(false); //NaN
      parseFloat('050px'); //50 (会忽略前导的零)
      ```

   ​	`其他值-------字符串`

   1. **String()函数**

      ```
      String(123); //'123'
      String(123.4); //'123.4'
      String(2e3); //'2000'
      String(NaN); //'NaN'
      String(Infinity); //'Infinity'
      String(oxf); //15
      String(true); //'true'
      String(false); //'false'
      String(undefined); //'undefined'
      String(null); //'null'
      ```

   2. **toString()方法**===几乎所有的值都有toString()方法，功能是将值转为字符串

      ```
      (6).toString(); //6 (数字要加括号)
      var a = 6;  //赋值
      a.toString(); //6
      ```

   ​	*`其他值-------布尔值`*

   1. **Boolean()函数**

      ```
      *Boolean(123); //true
      *Boolean(0); //false
      *Boolean(NaN); //false
      *Boolean(Infinity); //true
      *Boolean(-Infinity); //true
      **Boolean(''); //false
      **Boolean('abc'); //true
      **Boolean('false'); //true
      ***Boolean(undefined); //false
      ***Boolean(null); //false
      ```

10. 使用prompt()函数弹出输入框

11. 小测试

    1. parseInt('3.6'+'5.1'); //   3.65.1=3

    2. Boolean('false'); // true

    3. 0/0---NaN

    4. 4/0---Infinity

       

#### 表达式与操作符

1. **算术表达式**  (*除了加法，其余减乘除都先将字符转为数字再运算*)

   ```
   1 + 2 //3
   1 + '2' //'12'
   '1' + '2' //'12'
   3 % 9 = 3 //还是原来的被除数
   ```

2. **隐式类型转换**===如果参与数学运算的某操作数不是数字型，那么JavaScript会自动将此操作符转换为数字型(**加法除外**)

   ```
   3 * '4' //12
   3 + '4' //'34'
   隐式转换的本质是内部调用Number()函数
   true + true //2
   false + 2 //2
   3 * '2天' //NaN
   3 * '' //0
   3 * ' ' //0
   ```

3. **有关IEEE754**===在JavaScript中，有些小数的数学运算不是很精准，**例：0.1+0.2=0.300000.....4，**是因为JS使用IEEE754二进制浮点数算术标准，使个别小数“**丢失精度**”

4. ***解决办法**：在进行小数运算时，要调用数字的toFixed()方法，保留指定的小数位数

   ```
   (0.1 + 0.2).toFixed(2); // '0.30' 保留2位小数
   现在还是字符串'0.30',要转为数字  Number((0.1 + 0.2).toFixed(2));//0.30
   ```

5. 幂和开根号
   $$
   Math.pow(2,3) = 2^3
   $$

   $$
   Math.sqrt(81) = \sqrt{81}
   $$

6. 向上取整===Math.ceil()

   ```
   Math.ceil(2.4) //3
   Math.ceil(-2.4) //-2
   Math.ceil(2)  //2
   ```

7. 向下取整===Math.floor()

   ```
   Math.floor(2.4)  //2
   Math.floor(-2.4) //-3
   Math.floor(2)  //2
   ```

8. 相等和全等

   1. 两个等号：==  不比较值的类型，它会进行隐式转换后比较值是否相等

   2. 三个等号：===  不仅比较值是否相等，也比较类型是否相等

      ```
      5 == '5' //true
      5 === '5' //错误语句，值相同，类型不同
      ----------------------------------------------
      undefined == null , null == undefined //true (规定)
      undefined === null //false  (类型不同)
      ----------------------------------------------
      1. null 和 undefined 用==比较,涉及隐式强制类型转换，ES5规范中规定：
      x==y: 如果x为null,y为undefined,结果为true
      	  如果x为undefined,y为null,结果为true
      2. null 和 undefined 用===比较时，结果为false是因为类型不同
      	typeof null //object
      	typeof undefined //undefined
      ----------------------------------------------
      NaN == NaN //false (不自等，什么都不等)
      NaN === NaN //false
      ```

9. 如何判断某变量值为NaN

   isNaN()函数可以用来判断变量值是否为NaN

   ```
   isNaN(NaN) //true
   isNaN(7) //false
   isNaN(n)的作用是检测n是否为是“非数值”，返回值为Boolean类型，即isNaN(n) 返回 true or false
   ```

   **isNaN()的机理**：只要该变量传入**Number()**的执行结果是**NaN**，则**isNaN()**函数都会得到**true**

   ```
   isNaN(undefined) //true  NUmber(undefined) //NaN
   isNaN(null) //false		 Number(null)  //0
   isNaN('3天') //true	    Number('3天') //NaN
   ```

10. 不相等和不全等

    `! = 表示不相等`      `! ==  表示不全等`

    ```
    5 != 6 //true
    5 !== 6 //true
    5 != '5' //false
    5 !== '5' //true
    ```

11. javascript中无连等，3<=a<12 错误语句

    
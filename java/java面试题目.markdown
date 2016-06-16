# 基本语法
1.  一个‘.java’源文件是否可以包括多个类（不是内部类）？有什么限制？

  可以有多个类，但是只能有一个public的类，并且public的类的名称必须与文件名一致。如果没有public可不可以？可以没有public，但是只能有一个；如果public的名称与类名称不相同可不可以？不可以，必须相同；如果有多个public类可不可以？不可以；
2.  &和&&的区别？
 *  &和&&都可以看作逻辑与的运算符
 *  &&可以进行短路操作（防止空指针和条件语句中条件的数据自增）
 *  &除了布尔操作还可以进行位运算
3.  在java中如何跳出当前的多重嵌套循环？

  使用带有标号的break，还有一种方式是在外层循环体前加一个flag。

4.  switch是否能作用在byte上，是否能作用在long上，是否能作用在string上？

  byte可以，而long和string不可以。整型int和其包装类integer可以，且byte、short、char这种类型会隐式转型为int所以可以。

5.  short s1＝0；s1＝s1＋1；这句有错吗？short s1＝0；s1+=4;这句有错吗？

  这句报强制类型转化错误，因为在s1+1运算过程中会自动将类型提升int，而int赋值给short会报这错。
  但s1+＝4；这句不会报错，因为编译器会对这个进行特殊处理，so以后使用加的操作用+=啊。

6. char型变量中能不能存储一个中文汉字，为什么？

  **char c ＝ “中”;，这是种错误的语句**  or char 的unicode代表一个含义。
  java中“”代表一个字符串，而‘’代表一个字符。
  为什么一个char型变量可以代表一个中文汉字？因为char的变量就代表字符集中的一个字符，而中文字符是整个unicode编码中的一部分。
  一个char占2字节，一个字节有8位，一个位有2种可能性，所以有2的16次方种码。

7. 用最有效率的方式算出：2乘以8等于多少？

  位运算：2<<3;左移3位，就相当于2*2的3次方。

8. 设计一个一百亿计算器。

  首先，如果按照正常计算器计算，肯定是会出现越界。那么怎么解决这个问题呢？在正常的运算下肯定会发生越界。用面向对象的思想解决这个问题，这个对象就叫亿。这个对象有如下几个属性：正负、值；方法有：加减乘除。

  从题目设计者的角度出发，因为目前已经存在了解决这个问题的方法，BigInteger和BigDecimal。decimal（小数）。但题目设计者肯定不会这么简单的想让我们通过这个角度去解决这个题目。那么就有这种可能性：作者想让我们设计一个这样的对象。
9. 使用final关键词修饰一个变量时，是引用不能变，还是引用的对象不能变？
  答案一：
  使用final关键词修饰一个变量时，是指引用变量不能变化，引用变量的内容还是可以变化的。
  例如：final StringBuffer s ＝ new StringBuffer("immutable");
  执行a ＝ new StringBuffer（）；将报错。
  但是执行a.append("broken");将通过编译。
  答案二：
  如果final修饰数据时，数据就变为常量。一个变量是没有引用的。
  final修饰对象时：对象可以被改变，而对象的引用不变。
  final修饰方法是，这个方法就是最终方法。不可以被覆盖了。

  - 什么是变量？什么是常量?基本数据类型？对象？方法？
    变量有局部变量（非类内的变量）和全局变量（类内部的变量）。基本数据类型与变量或者常量没关系。在类被创建为对象时，对象的内的数据成员不能被改变时，称之为常量。能改变时称之为变量。
    类中有（字段）数据成员和函数（方法）
10. “＝＝”和equals方法究竟有什么区别？

  答案一：
  答案二：相同之处：都是用来比较字段或者对象是否相同
  不同之处：＝＝是运算符，equals是一个object内的方法。通过实现object的方法，可以比较两个对象属性是否相同，或可以比较两个对象的引用是否相同。在Object的底层，其实是用＝＝来做比较的，如果想做更多的事，必须覆盖Object的方法。很多对象都默认的重写比较的方法。
  覆盖重写和重载的区别？
  覆盖是指的子类重写父类方法。
  重载是指一个类中构造函数，函数名称相同参数类型有包含关系。
11. 静态变量和实例变量的区别？

  存储的位置不相同：静态变量存储在静态存储区，实例变量存储在堆中。
  初始化时间不相同：静态变量在对象加载到jvm时初始化。
  作用域也不相同：
12. 是否可以从一个static方法内部发出对非static方法的调用？
13. Integer与int的区别
14. Math.round(11.5)等于多少？Math.round(-11.5)等于多少？
15. 作用域public private protected，以及不写时的区别？
16. overload和override的区别？Overloaded的方法是否可以改变返回值的类型？
17. 构造器Constructor是否可以被override？
18. 接口是否可以继承接口？抽象类是否可以实现接口？抽象类是否可以继承具体类（concrete class）？抽象类中是否可以有静态的main方法？
19. 写clone()方法时，通常都有一行代码，是什么？
---
20. 面向对象的特征有哪些方面
21. java中实现多态的机制是什么？
22. abstract class和interface有什么区别？
23. abstract 的mathod是否可同时是static，是否可同时是native，是否可同时是synchronized？
24. 什么是内部类？
25. 内部类可以引用他包含类的成员吗？有没有什么限制？
26. static Nested class 和inner Class的不同。
27. Anonymous Inner Class 是否可以extends其他类，是否可以implement interface？
28. String是最基本的数据类型吗？
29. String s ＝ “hello”；s ＝ s＋“world！”；这两行代码执行后，原始的String对象中的内容到底变了没有？
---
30. 是否可以继承String？
31. String s ＝ new String(“xyz”)；创建了几个String Object？二者之间有什么区别？
32. String和StringBuffer的区别？
33. 如何把一段逗号分割的字符串转换成一个数组？
34. 数组有没有length（）这个方法？String有没有length（）这个方法？
35. Try｛｝里有一个return语句，那么紧跟在这个try后的finally｛｝里的code会不会被执行，什么时候被执行，在return前还是return后？
36. final finally finalize 的区别？
37. 运行时异常与一般异常有何异同？
38. error和exception有什么区别？
39. Java中的异常处理机制的简单原理和应用。
---
40. 给我一个你最常见到的runtime exception
41. java 语言如何进行异常处理，关键字：throws、throw、try、catch、finally分别代表什么意义？在try块中可以抛出异常吗？
42. java中有几种方法可以实现一个线程？用什么关键字修饰同步方法？stop()和suspend()方法为何不推荐使用？
43. sleep()和wait()有什么区别？
44. 同步和异步有何异同，在什么情况下分别使用他们？举例说明。
45. 下面两个方法同步吗？
46. 多线程有几种实现方法？同步有几种实现方法？
47. 启动一个线程是用run()还是start()?
48. 当一个线程进入一个对象的一个synchronized方法后，其它线程是否可以进入此对象的其他方法？
49. 线程的基本概念、线程的基本状态、以及状态之间的关系？
---
50. 简述synchronized和java.util.concurrent.locks.Lock的异同？
51. 设计4个线程，其中两个线程每次对j增加1，另外两个线程对j每次减少1.写出程序。
52. ArrayList和Vector的区别？
53. HashMap和Hashtable的区别？
54. List和Map区别？
55. List、Set、Map是否继承自Collection接口？
56. List、Map、Set三个接口，存取元素时，各有什么特点？
57. 说出ArrayList、vector、LinkedList的存储性能和特性。
58. 去掉一个Vector集合中重复的元素
59. Collection和Collections的区别。
---
60. Set里的元素是不能重复的，那么用什么方法来区分重复与否呢？是用＝＝还是equals？它们有何区别？
61. 你所知道的集合类都有哪些？主要方法？
62. 两个对象值相同（x.equals（y）＝＝true），但却可有不同的hashCode，这句话对不对？
63. java中有几种类型的流？JDK为每种类型的流提供了一些抽象类以供继承，请说出他们分别是哪些类？
64. 什么是java序列化，如何实现java序列化？
65. 描述一下JVM加载class文件的原理机制？
66. heap和stack有什么区别？
67. GC是什么？为什么要有GC？
68. 垃圾回收的优点和原理。并考虑2种回收机制。
69. 垃圾回收器的基本原理是什么？垃圾回收器可以马上回收内存吗？有什么办法主动通知虚拟机进行垃圾回收？
---
70. 什么时候用assert？
71. java中会内存泄露吗？请简单描述。
72. 下面的程序代码输出的结果是多少？
      public class smallT {
        public static void main(String args[]) {
          smallT t = new smallT();
          int b = t.get();
          System.out.println(b);
        }
        public int get{
          try {
          return 1 ;
          }
          finally {
          return 2 ;
          }
        }
      }

73. 下面的程序输出结果是多少？

        `import java.util.Date;
        public class Test extends Date{
          /**
          * @param args add by zxx ,Dec 9, 2008
          */
          public static void main(String[] args) {
            new Test().test();
          }
          public void test() {
            System.out.println( super.getClass().getName()
            );
          }
        }`


74. 说出一些常用的类、包、接口、请各举5个
75. java代码差错
# 算法与编程
76. 写一个Singleton出来
77. 算法递归题1

  一个整数，大于0，不用循环和本地变量，按照n、2n、4n、8n的顺序递增，当值大于5000时，把值按照指定顺序输出来。
  例：n＝1237
  则输出为
  1237，
  2427，
  4948，
  9896，
  9896，
  4948，
  2474，
  1237，
78. 算法递归题2

  第1个人10，第2个比第1个人大2岁，依次地退，第8个人多大？
79. 排序都有哪几种方法？请举例，用java实现一个快速排序。
---
80. 有数组a[n]，用java代码将数组元素顺序颠倒
81. 金额转换，用阿拉伯数字的金额转换成中国传统的形式如：（1011）至（一千零一拾一元整）输出。
# html&JavaScript 部分
82. 用table显示n条记录，每3行换一次颜色，即1，2，3用红色字体。4，5，6，用绿色字体。7，8，9用红色字体。
83. html的form提交之前如何验证数值不为空？为空的话提示用户并终止提交？
84. 请写出用于效验html文本框中输入的内容全部为数字的javascript代码

# java Web部分
85. http请求的get与post方式的区别？
86. 解释一下什么是servlet？
87. 说一说servlet的生命周期？
88. servlet的基本架构
89. servlet API 中forward()与redirect()的区别？
---
90. 什么情况下调用doGet()和doPost()？
91. Request对象的主要方法？
92. forward和redirect的区别？
93. request.getAttribute()和request.getParameter()有何区别？
94. jsp有哪些内置对象？作用分别是什么？分别有什么方法？
95. jsp有哪些动作？作用分别是什么？
96. JSP的常用命令
97. JSP中动态INCLUDE与静态INCLUDE的区别？
98. 两种跳转方式分别是什么？有什么区别？
99. 页面间对象传递的方法
---
100. JSP和Servlet有哪些相同点和不同点，他们之间的联系是什么？
101. MVC的各个部分都有哪些技术来实现？如何实现？
102. 我们在web应用开发过程中经常遇到输出某种编码的字符，如ISO8859-1等，如何输出一个某种编码的字符串？
103. 现在输入n个数字，以逗号分开，然后可选择升或者降序排序；按提交键就在另一个页面显示按什么排序，结果为提供reset
# 数据库部分
104. 数据库三范式是什么？
105. union和union all有什么不同？
106. oracle关联查询题目1
107. 什么是存储过程和如何编写
108. 注册jdbc驱动程序的三种方式
109. 用jdbc如何调用存储过程
---
110. JDBC中的PreparedStatement相比Statement的好处
111. 写一个用JDBC连接并访问oracle数据的程序代码
112. Class.ForName的作用？为什么要用？
113. 大数据量下的分页解决方法。
114. 用JDBC查询学生成绩单，把主要代码写出来
115. 这段代码有什么不足之处？
        try｛
          Connection conn ＝ 。。。；
          Statement stmt ＝ 。。。；
          ResultSet rs ＝ stmt.executeQuery("select ＊ from table")；
          while（rs.next（））｛
          ｝
        ｝catch（Exception ex）｛
        ｝
116. 说出数据连接池的工作机制是什么？
117. 为什么要用ORM？和JDBC有何不一样？
# XML部分
118. xml有哪些解析技术？区别是什么？
119. 你在项目中用到了XML技术的哪些方面？如何实现的？
---
120. 用jdom解析xml文件时如何解决中文问题？如何解析？
121. 编程用java解析XML的方式。
122. XML文档定义有哪几种形式？它们之间有何本质区别？解析XML文档有哪几种方式？
# J2EE部分
123. BS与CS的联系与区别。
124. 应用服务器与WEB server的区别？
125. 应用服务器有哪些？
126. J2EE是什么？
127. J2EE是技术还是平台还是框架？什么是J2EE
128. 请对以下在J2EE中常用的名词进行解释（或简单描述）
129. 如何给weblogic指定内存大小？
---
130. 如何设定web logic的热启动模式（开发模式）与产品发布模式？
131. 如何启动时不需输入用户名与密码？
132. 在weblogic管理制台中对一个应用域（或者说是一个网站，domain）进行jms及ejb或连接池等相关信息进行配置后，实际保存在什么文件中？
133. 说说web logic中一个Domain的缺省目录结构？比如要将一个简单的helloworld.jsp放入何目录下，然后在浏览器上就可打入http://zhuji：端口号／／helloworld.jsp就可以看到运行结果了？又比如这其中用到一个自己写的javaBean该如何办？
134. 在web logic中发布ejb需涉及到哪些配置文件
135. 如何在web logic中进行ssl配置与客户端的认证配置或说说j2EE（标准）进行ssl配置？
136. 如何查看在web logic在已经发布的ejb？
# EJB 部分
137. ejb是基于那些技术实现的？并说出SessionBean何EntityBean的区别，StatefulBean和StatelessBean的区别。
138. 简要讲一下EJB的7个Transaction Level？
139. EJB与JAVA BEAN的区别？
---
140. EJB包括（SessionBean，EntityBean）说出他们的生命周期，及如何管理事物的？
141. EJB容器提供的服务
142. EJB的激活机制
143. EJB的几种类型
144. 客服端调用EJB对象的几个基本步骤
# webService部分
145. WEB SERVICE名词解释。JSWDL开发包的介绍。JAXP、JAXM的解释。SOAP、UDDI，WSDL解释。
146. CORBA是什么？用途是什么？
# 流行的框架与新技术
147. 谈谈Struts中的Action servlet
148. Struts优缺点
149. struts的应用（如struts架构）
---
150. hibernate中的update()和saveOrupdate()的区别，Session的load()和get()的区别。
151. 简述Hibernate和JDBC的优缺点？如何书写一个one to many配置文件。
152. iBatis与Hibernate有什么不同？
153. 介绍一下Hibernate的二级缓存
154. Spring的依赖注入是什么意思？给一个Bean 的message属性，字符串类型，注入值为“Hello”的XML配置文件该怎么写？
155. Jdo是什么？
156. 什么是Spring的IOC AOP
157. Struts的工作流程
158. Spring与EJB的区别？
# 软件工程与设计模式
159. UML方面
---
160. j2ee常用的设计模式？说明工厂模式
161. 开发中都用到了哪些设计模式？用在什么场合？
# Linux
162. LINUX下线程，GDI类的解释。

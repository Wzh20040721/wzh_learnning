# JAVA学习笔记
## JAVAEE学习基础

### 语法基础

#### 数据类型
整数类型：
![image_2.png](image_2.png)

浮点数类型：
![image_1.png](image_1.png)

布尔类型：boolean
1个字节来存储

字符类型：string、char
2个字节来存储

### 表达式和运算符

#### 算数运算符

![image_3.png](image_3.png)
![image_4.png](image_4.png)

<table>
<tr><td>前缀表达式</td> <td>后缀表达式</td></tr>
<tr><td>先运算，后赋值 </td> <td>先赋值，后运算 </td></tr>
</table>

#### 布尔逻辑运算符
布尔逻辑运算符用于对布尔值进行布尔逻辑运算。其中，&&、‖为二元运算符，实现逻辑与、逻辑或；!为一元运算符，实现逻辑非；^为二元运算符，实现逻辑的异或运算。

对或运算（‖），如果左边表达式的值为true，则整个表达式的结果为true，不必对运算符右边的表达式再进行运算；同样，对与运算（&&），如果左边表达式的值为false，则不必对右边的表达式求值，整个表达式的结果为false。


### 类型转换

#### 自动转换
java中一般能够从小类型自动转化为大类型，类型大的内存不一定大，如：
* long类型是整数类型，他需要8个字节来存储，而float类型是浮点数，它只需要4个自己来存储，但在运算时，是由long类型数据转换为float类型数据

这里所提到的大类型指的是精度大。下面是自动转化的规则：
* byte & short op int -> int
* 精度从小到大排序： byte < short < int < long < float < double
* char op byte short int -> int
* char op long -> long
* boolean类型，该类型不能转换为整数类型和浮点数类型以及字符类型，但可以转换为字符串类型。

#### 强制转换
如果需要大转小需要强制转换：
<code> loat f = (float)32.5/10;
或者float f = 32.5f/10;</code>

### JAVA流程控制

#### if语句

<tabs>
    <tab title="二选一">
        <tabs>
            <tab title="语法">
                <code-block> 
                    if(x > y)
		        max = x;//只有一条表达式语句，省略了大括号。
                    else 
		        max = y;
                </code-block>
            </tab>
            <tab title="流程图">
                <img src="image_6.png" alt="liuchengtu"/>     
            </tab>
        </tabs>
    </tab>
    <tab title="多选一">
        <tabs>
            <tab title="语法">
                <code-block> 
                if(condition 1) {
                    语句块1
                } else if(condition 2) {
                   语句块2
                } else if(condition 3) {
                   ...
                } else if(condition n) {
                   语句块n
                } else {
                   语句块M
                }
                </code-block>
            </tab>
            <tab title="流程图">
                <img src="image_7.png" alt="liuchengtu2"/>
            </tab>
        </tabs>
    </tab>
</tabs>

### 面向对象编程基础
#### 类与对象的实现
1.抽象一个类，类定义的三要素:类标识、属性说明、类的方法

2.定义类：
    class 类标识符{
    声明属性
    定义方法
}

3.定义类示例：
<code-block>
    class Radio {
        boolean on;
        double freq;
        int vol;
        void chgVol(int offset) {
            //此处添加实现代码
        }
        void chgFreq(double offset) {
            //此处添加实现代码
        }
    }
</code-block>

4.创建对象： 类名 对象名 = new 类名（）；

5.访问对象的数据成员：使用域操作符“.”来去访问（读取和修改）对象的状态；同样通过域操作符“.”还可以去调用对象的成员方法。

6.构造方法：构造方法可以重载，可以定义多个具有不同参数的构造方法。也可以继承，即子类可以继承父类的构造方法

7.构造方法示例：
<code-block>
    Radio(boolean o, double f, int v) {
        on = o;
        freq = f;
        vol = v;
    }
</code-block>

8.构造方法初始化对象状态值:
<code-block>
    Radio r1 = new Radio(true, 99.8, 28);
    Radio r2 = new Radio(false, 89.2, 99);
</code-block>

9.使用成员方法模拟对象行为
<code-block>
    void chgVol(int offset) {
       if(!on)//判断是否开机
          return;//没有开机，不做处理直接返回
       vol += offset;//计算最终音量
       if(vol < 0)//判断是否小于最小值0
          vol = 0;
       if(vol > 100) //判断是否大于最大值100
          vol = 100;
    }
    main()函数中的对收银机调音的调用代码如下：
    Radio r = new Radio(true, 99.8, 0);
    r.chgVol(-10);
</code-block>


#### 值传递与地址传递
1.把两个对象变量指向相同的内存单元
<tabs>
    <tab title="codes">
        <code-block>
        Radio r1 = new Radio(true, 99.8, 18);
        Radio r2 = r1;
        </code-block>
    </tab>
    <tab title="示意图">
        <img src="image_8.png" alt="shiyitu3"/>
    </tab>
</tabs>

2.包装类:用于把基本类型数据转换为对应的对象类型
<tabs>
    <tab title="基本类型与其对应类型">
        <img src="image_9.png" alt="shiyitu4"/>
        <p>  </p>
    </tab>
    <tab title="对象类型及其转换基本类型方法">
        <img src="image_10.png" alt="shiyitu5"/>
    </tab>
    <tab title="特殊的string类型">
        <table>
            <tr><td>基本数据类型</td><td>对象类型</td><td>转化方法</td></tr>
            <tr><td>string</td><td>String</td><td>String.valueOf()</td></tr>
        </table>
    </tab>
</tabs>

#### 其他类型数据成员






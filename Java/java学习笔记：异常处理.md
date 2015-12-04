1：声明异常：在java中，当前执行的语句必属于某个方法，java解释器调用main方法开始执行每一个程序，每个方法都必须用`throws`声明它可能抛出的必检异常的类型。这称为声明异常，因为任何代码都可能发生系统错误或者运行时错误，但是`Error`和`RuntimeException`称为免检异常，即我们不用声明，但是其他异常我们就必须声明了。
```
public void myMethod() throws IOException
//关键字throws表明myMethod方法可能会抛出IOException，如果一个方法可能抛出多个异常，那就在关键字throws后面添加一个逗号分隔的异常列表：
public void myMethod()
throws Exception1,Exception2,Exception3...
注意：
1：如果某方法没有在父类中声明异常，那么就不能在子类中对其进行覆盖来声明异常。
2：声明一个异常用throws，抛出异常用throw。
```
2：java中`Throwable`类是所有异常类的根，所有的java异常类都直接或者间接的继承自`Throwable`，可以通过扩展`Exctption`和`Exception`子类来创建自己的异常类。java中将异常分为三种主要的类型：
- 系统错误：java虚拟机抛出，用Error类表示。比如`VirtualMachineError`表示java虚拟机中断或者没有继续运行所需要的资源。
- 异常：用Exception类表示，描述的是由程序和外部环境所引起的错误，这些错误能被程序捕并且做出相应的处理。比如`IOException`表示无效的输入等与输入输出有关的操作。
- 运行时错误：由RuntimeException类表示的，比如`NullPointerException`表示企图通过一个null应用变量访问一个对象。  

已经说过系统错误和运行时错误属于免检异常，其他异常属于必检异常。  
3：`finally`字句  
有时候，无论异常是否出现或者是否被捕获，都希望执行一些代码，比如常见的是用于I/O程序设计中，为了确保一个文件在所有情况下均被关闭，可能在`finally`字句中放置一条文件关闭语句，这样可以保证资源被释放。  
4：自定义异常类：有时我们需要自己定义一个属于自己的异常类。基本声明如下：
```
public class myException extends Exception
```
我们要实现它的构造方法，它的父类默认有下面的构造方法：
```
+Exception()   //构造一个无消息的异常
+Exception(message:String) //构造一个带有特定消息的异常。
```
5：一般情况下，异常处理将错误处理代码从正常的程序设计任务中分离开来，这样可以使得程序更加容易阅读。
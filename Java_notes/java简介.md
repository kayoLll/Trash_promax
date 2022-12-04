### JDK

- java：这个可执行程序其实就是JVM，运行Java程序，就是启动JVM，然后让JVM执行指定的编译后的代码；
- javac：这是Java的编译器，它用于把Java源码文件（以`.java`后缀结尾）编译为Java字节码文件（以`.class`后缀结尾）；
- jar：用于把一组`.class`文件打包成一个`.jar`文件，便于发布；
- javadoc：用于从Java源码中自动提取注释并生成文档；
- jdb：Java调试器，用于开发阶段的运行调试。

~~~java
public class Hello {
    //定义了一个class 类名为hello，public表示类是公开的
    //{ }中是类的定义；类中定义了一个名为main的方法，用()括起来的是方法参数，参数类型是String[]，参数名是args
    public(公开的) static(静态的) void(返回类型) main(String[] args) {
        // Java程序的固定入口方法 程序总是从main方法开始执行
        System.out.println("Hello, world!");
    }
}
~~~


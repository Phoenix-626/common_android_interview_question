1. [java int与integer的区别?](https://www.cnblogs.com/shenliang123/archive/2011/10/27/2226903.html)

    int与integer的区别从大的方面来说就是基本数据类型与其包装类的区别

    `int` 是基本类型，直接存数值，而 `integer` 是对象，用一个引用指向这个对象
    a. Java 中的数据类型分为基本数据类型和复杂数据类型, int 是前者而integer 是后者（也就是一个类）；因此在类进行初始化时int类的变量初始为0.而Integer的变量则初始化为null.
    
    b.初始化时, int i =1；Integer i= new Integer(1);(要把integer 当做一个类看)；但由于有了`自动装箱和拆箱`, 使得对Integer类也可使用:
    
    ```java
    Integer i= 1；
    ```

2.  [int、char、long各占多少字节数?](https://blog.csdn.net/nyistzp/article/details/12029917)

    `char` 在 java 中是 `2` 个字节，java 采用 `unicode`，2个字节(byte)来表示一个字符; `short` 2个字节; `int` 4个字节; `long` 8个字节; `float` 4个字节; `double` 8个字节

3. [在UTF-8中，一个汉字为什么需要三个字节?](https://www.cnblogs.com/web21/p/6092414.html)
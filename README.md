# 记录一下初学 Java 时容易遇到的问题

## 1. Scanner 使用问题

- `Scanner in = new Scanner(System.in);`<br>
  这是最常用的 Scanner 语句，但是并不是只能这样写。这里涉及到一个关于对象创建的问题。
  - Scanner 是类名，Scanner in 的这个 in，其实是创建出来的对象名，我们其实可以随便取这个对象的名字，只是一般我们用 in。比如我写`Scanner innnnnn = new Scanner(System.in);`也是可以的。
    - 但是后面的那个 in 就不一样了，System.in 可不能改名字，这个是固定的。
      - 我们在后面调用的时候也要注意，调用的应该是我们创建的对象名，而不是常用的`in.nextInt();`<br>
      ```Java
      Scanner innnnnn = new Scanner(System.in); //从Scanner类创建名为innnnnn的对象
      int i = innnnnn.nextInt(); //创建整形变量i，将下一个键盘输入赋值给i
      System.out.println(i); //输入i的值
      innnnnn.close(); // 最后记得 对象名.close 来关闭Scanner输入
      ```

## 2. 函数(方法)的使用
- Java里的函数被称为方法，方法的使用和C语言有很大不同。一般我们会把所需要的函数定义在main方法前，包裹在外层Class里。  
  - 比如我现在有一个类，名为App，我想在main方法里调用前面我定义的方法function1。那我需要先new一个App的对象出来，也就是 `App testxx = new App();`，然后`testxx.function1`，这样我才能正常调用function1。在C里因为没有对象的概念，所以可以直接function1。
    - ```Java
      public class App {
          int function1() {
              int a = 1;
              int b = 2;
              int c = a + b;
              return c;
          }
          public static void main(String[] args) {
              App testxx = new App();
              int i = testxx.function1();
              System.out.println(i);
          }
      }
      ```
      `输出：3`

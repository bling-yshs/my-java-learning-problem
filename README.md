# 记录一下初学Java时容易遇到的问题  

## 1. Scanner使用问题
 - `Scanner in = new Scanner(System.in);`<br>
 这是最常用的Scanner语句，但是并不是只能这样写。这里涉及到一个关于对象创建的问题。
    - Scanner是类名，Scanner in的这个in，其实是创建出来的对象名，我们其实可以随便取这个对象的名字，只是一般我们用in。比如我写`Scanner innnnnn = new Scanner(System.in);`也是可以的。
        - 但是后面的那个in就不一样了，System.in可不能改名字，这个是固定的。
            -   我们在后面调用的时候也要注意，调用的应该是我们创建的对象名，而不是常用的`in.nextInt();`<br>
            ```Java
            Scanner innnnnn = new Scanner(System.in);
            int i = innnnnn.nextInt();
            System.out.println(i);
            innnnnn.close();
            ```  
            -   最后记得`对象名.close`
```java
class User {
    private String name;

    // 私有构造方法：禁止外部直接通过 new 创建对象
    private User(String name) {
        this.name = name;
    }

    // 静态工厂方法：属于类本身，而非实例
    public static User createUser(String name) {
        return new User(name); // 在静态方法内调用私有构造方法
    }
}

// 使用：
User user = User.createUser("张三"); // 直接通过类名调用静态方法
```
### **调用过程详解**
1. **调用静态方法**  
   通过类名 `User` 直接调用静态工厂方法 `createUser`，并传入参数 `"张三"`：
   ```java
   User user = User.createUser("张三");
   ```

2. **静态方法内部处理**  
   静态方法 `createUser` 接收参数 `name`，然后调用 `User` 类的私有构造方法：
   ```java
   public static User createUser(String name) {
       return new User(name); // 这里调用了私有构造方法
   }
   ```

3. **私有构造方法创建对象**  
   私有构造方法接收 `name` 参数，并初始化 `User` 对象的内部状态：
   ```java
   private User(String name) {
       this.name = name; // 将传入的 name 赋值给字段
   }
   ```

4. **返回新对象**  
   最终，静态方法将新创建的 `User` 对象返回给调用方，完成对象的创建。


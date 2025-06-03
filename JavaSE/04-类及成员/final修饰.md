### 1. final修饰类

- **`表示这个类不能被继承，没有子类。`**
- 提高安全性，提高程序的可读性。
- 例如：String类、System类、StringBuffer类


### 2. final修饰方法

- **`表示这个方法不能被子类重写。`**
- 例如：Object类中的getClass()


```java
class Father{
	public final void method(){
		System.out.println("father");
	}
}
class Son extends Father{
	public void method(){//错误
		System.out.println("son");
	}
}
```

### 3. final修饰基本类型字段

- **`表示常量，一旦赋值，它的值就不能被修改。`**

- 初始化要求

  - **成员变量**：`final` 修饰的成员变量必须在声明时或构造方法中初始化。

  - **静态变量**：`final static` 修饰的变量通常在声明时或静态初始化块中初始化。

  - **局部变量**：在方法内部声明的 `final` 变量必须在使用前被赋值，且只能赋值一次。

修饰成员变量：

```java
public final class Test2
{
  public static int totalNumber = 5;
  public final int ID;

  public Test2()
  {
    ID = ++totalNumber; // 可在构造器中给final修饰的“变量”赋值
  }

  public static void main(String[] args)
  {
    junitTest t = new junitTest();
    System.out.println(t.ID);
  }
}

```

修饰局部变量：

```java
public class TestFinal {
    public static void main(String[] args){
        final int MIN_SCORE ;
        MIN_SCORE = 0;
        final int MAX_SCORE = 100;
        MAX_SCORE = 200; //非法
    }
}
```

### 4. final修饰引用类型字段

- **`表示其引用地址不可更改，但引用对象的内部状态仍可修改。`**

例如，`final` 修饰的数组可以修改其元素值，但不能将其指向另一个数组。


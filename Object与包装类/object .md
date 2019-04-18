# object 类

- 所有java类的父类

- Object o = 任何对象

- Object类中的方法可以继承给所有子类，是所有对象都具有的方法

- getclass()返回对象的实际类型   class 对象（反射介绍）

  ```
  package testObject;
  
  public class TestObject {
      public static void main(String[] args) {
          Animal a1 = new Dog();
          Animal a2 = new Cat();
          System.out.println(a1 instanceof Dog );
          System.out.println(a2 instanceof Dog );
          System.out.println(a1.getClass());
      }
  
  }
  
  class Animal {
  
  }
  
  class Dog extends Animal {
  
  }
  
  class Cat extends Animal {
  }
  // 输出结果
  //true
  //false
  //class testObject.Dog
  
  ```

- tostring()  print 打印对象等同于打印对象的tostring（）的 返回值    可以覆盖tostring （） 改变输出格式

  ```
  package testObject;
  
  public class TestObject {
      public static void main(String[] args) {
          Animal a1 = new Dog();
          Animal a2 = new Cat();
  //        System.out.println(a1 instanceof Dog );
  //        System.out.println(a2 instanceof Dog );
  //        System.out.println(a1.getClass());
          Student s  = new Student("zj",40);
          System.out.println(s);            // 打印对象s  s会调用tostring（） 查看println()
          System.out.println(s.toString());
      }
  
  }
  
  class Animal {
  
  }
  
  class Dog extends Animal {
  
  }
  
  class Cat extends Animal {
  }
  class Student {
      private String name;
      private int age;
  
      public Student(String name, int age) {
          this.name = name;
          this.age = age;
      }
  }
  // 输出结果
  //testObject.Student@64c64813
  //testObject.Student@64c64813
  
  覆盖tostring（） 改变对象的输出
  class Student {
      private String name;
      private int age;
  
      public Student(String name, int age) {
          this.name = name;
          this.age = age;
      }
  
      @Override
      public String toString() {
          return  "name="+name+"  age="+age;
      }
  }
  //name=zj  age=40
  //name=zj  age=40
  ```






​      

```
        int a = 10;
        int b = 10;
        System.out.println(a == b); // 基本类型变量值相同
        Student s1 = new Student("zh",40);
        Student s2 = new Student("zh",40);
        System.out.println(s1 == s2); // 引用型变量判断其地址
```

!["运行结果"](C:\Users\颖宝\AppData\Roaming\Typora\typora-user-images\1554619537235.png)

- == 对于基本类型变量 是判断其存储本身值  对于引用型变量 是判断其对象的存储地址

- equals() 判断两个对象的内容是否相同

  - public boolean equals (Object o): s1.equals(s2); 判断s1 和s2 内容是否相同

  - ```
            String s1 = new String("abc");
            String s2 = new String("abc");
            System.out.println(s1==s2);
            System.out.println(s1.equals(s2)); // 字符串类的equals 已经重写了
    ```

  - ![](C:\Users\颖宝\AppData\Roaming\Typora\typora-user-images\1554620020066.png)

  - ```
            int a = 10;
            int b = 10;
            System.out.println(a == b);
            Student s1 = new Student("zh",40);
            Student s2 = new Student("zh",40);
            System.out.println(s1 == s2);
            System.out.println(s1.equals(s2));// 此处是业务逻辑 源码
            //public boolean equals(Object obj) {
            //return (this == obj);
            // }需要覆盖 Oblect.equals  由用户自己定义 相等的逻辑
            
    ```

    ```
     // 覆盖equals方法判断this对象和o对象是否相同
       public boolean equals(Object o){
            if (this==o)return true;
            if (o==null)return false;
            if (this.getClass()!= o.getClass())
                return false;
            Student s = (Student)o;
            if (this.name.equals(((Student) o).name)&& this.age==((Student) o).age)return  true;
            else return  false;
        }
    ```

    ```
    // 编辑器生成的 equals（）
        @Override
        public boolean equals(Object o) {
            if (this == o) return true;
            if (o == null || getClass() != o.getClass()) return false;
            Student student = (Student) o;
            return age == student.age &&
                    Objects.equals(name, student.name);
        }
    ```

    ![](C:\Users\颖宝\AppData\Roaming\Typora\typora-user-images\1554620323185.png)

    

- finalize()
  - 垃圾回收 ：jvm自动回收垃圾对象，释放相应的内存空间
  - 垃圾对象的认定： 零引用算法
  - 垃圾对象的回收时机：延迟回收策略
  - finalize（）:对象被垃圾回收的时候，由垃圾收集器自动调用

​          
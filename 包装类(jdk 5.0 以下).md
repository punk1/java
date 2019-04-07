# 包装类(jdk 5.0 以下)

- ```
  package testinteger;
  
  public class TestInteger {
      public static void main(String[] args){
          // int Integer
          int i = 10;
          Integer a = new Integer(i);
          System.out.println(a);
      }
  
  }
  
  ```

- 8 种基本类型的包装类（对象形式）

   

  |   int   |  Integer  |
  | :-----: | :-------: |
  |  byte   |   Byte    |
  |  short  |   Short   |
  |  float  |   Float   |
  | double  |  Double   |
  |  long   |   Long    |
  |  char   | character |
  | boolean |  Boolean  |

  - 前6种为数值类  Number子类

    

- int a ---->获取 一个Integer对象 

  - new Integer()
  - Integer.valueof()

  ```
  package testinteger;
  
  public class TestInteger {
      public static void main(String[] args){
          // int Integer
          int i = 10;
          Integer a = new Integer(i);
          Integer b = Integer.valueOf(i);
          System.out.println(b);
  
          Integer a1 = new Integer(12);
          Integer a2 = new Integer(12);
          System.out.println(a1==a2);
  
          Integer a3 = Integer.valueOf(12);
          Integer a4 = Integer.valueOf(12);
          System.out.println(a3==a4);
      }
  
  }
  ```

  ![](C:\Users\颖宝\AppData\Roaming\Typora\typora-user-images\1554623724777.png)

  ```
  // valueof ()  low = -128 high = 127 
   public static Integer valueOf(int i) {
          if (i >= IntegerCache.low && i <= IntegerCache.high)
              return IntegerCache.cache[i + (-IntegerCache.low)];
          return new Integer(i);
      }
      
      // 对 -128 到 127 建立了数组 相当于缓存   不在此范围的才会新创建对象
  ```

  - 当Integer.valueof ()数据处于 -128 到 127 时，返回数组 位置  

  - ```
            Integer a3 = Integer.valueOf(12);
            Integer a4 = Integer.valueOf(12);
            System.out.println(a3==a4);
    
            Integer a5 = Integer.valueOf(128);
            Integer a6 = Integer.valueOf(128);
            System.out.println(a5==a6);
    // true
    // false
    ```

    

- Integer a----->int a  a.intvalue()

  - ```
            int i = a5.intValue();
            System.out.println(i);
    ```



## 自动拆箱，装箱

-  由编译器完成基本类型的和包装类之间的转换

```
        Integer a = 10; // Integer a = Integer.valueof(10)
        int i = a;      // int i = a.intvalue()
        System.out.println(++a);// a= Integer.valueof(a.intvalueof()+1)
        // 11
```




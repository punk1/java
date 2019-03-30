# java-自动类型转换

- 如果操作数中有一个 即位 它的类型  按优先级从高到低（double,float,long ,int）

- 如果操作数中没有int ,均为short，byte ，计算结果仍旧为int

- 任何类型与string相加时，实为拼接，结果自动提升为string

  ```
  public class Main {
  
      public static void main(String[] args)
      {
          int a = 100;
          String s = "qwe";
          s=s+a;
          System.out.println(s);
      }
  }
  
  ```

  # 数组

  - 作为可变长参数

    - 参数表中只能有一个可变长参数，且必须时最后一个参数

    ```
    import java.util.Arrays;
    
    public class Main {
    
        public static void main(String[] args) {
    
            System.out.println(add(1, 2, 3));
            System.out.println(add(1, 2));
            System.out.println(add(1));
            System.out.println(add());
        }
    
        // 0-n 个int
        private static int add(int... a) {   // 此时a 即位数组
            int result = 0;
            for (int i = 0; i < a.length; i++) {
                result += a[i];
            }
            return result;
        }
    }
    
    ```

  - 
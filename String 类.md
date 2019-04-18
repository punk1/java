# String 类

- toCharArray():转成字符数组

- new String(char[] cs):用字符数组 构造字符串

- toUpperCase()/toLowerCase()  大小写转换

-  contains(String s)  判断s子串是否存在

- startsWith（String s）:判断 s子串 是否 开头 

- endsWith(String s): 判断 s子串 是否结尾

- indexOf(Stirng s) :判断s子串最早出现的下标

- lastIndexOf(String s)返回 s子串 最后出现的下标

- replace (String s1, String s2) 将s1子串替换为 s2子串

- subString(int a,int b):返回 字符串 a下标 到b下标的 子串 （包含a下标 不包含 b下标）

  ```
          String s = "abc";------>放入常量池
          String s1 = "abc";
          System.out.println(s1==s);
          // true
  
  ```

  ```
         String s = "a"+"b"+"c";// 编译器直接算好 只有一个 对象 没有中间对象
         String s1= "a";           // 这种会产生 中间对象
         s1=s1+"b";
         s1= s1+"c";
         System.out.println(s1);
  ```

  

# StringBuilder类

- 可变字符串 对象

- ```
          String s = "a";
        
          StringBuilder sb = new StringBuilder(s);
          sb.append("b").append("c");
          s= sb.toString();
          System.out.println(sb);
  ```

  
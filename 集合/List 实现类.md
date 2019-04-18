#  List 实现类

- ArrayList
  - 数组实现 查询快 增删慢    线程不 安全 并发效率高
- Vector
  - 数组实现  线程安全  并发效率低

- LinkedList 链表实现

  - 查询慢 增删快

  - ```
    package TestLinkedList;
    
    import java.util.LinkedList;
    
    public class testlinkedlist {
        public static void main(String[] args){
            LinkedList list = new LinkedList();
            list.add("liu");
            list.add("zhao");
            list.add("tan");
            list.addFirst("yun");
            for (Object o :list){
                System.out.println(o);
            }
        }
    }
    
    ```

    
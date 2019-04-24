# Future   Callable

- Callable 接口 相比 Runnable 接口 ，可以抛出异常，获得返回值

  - Future 对象 ，用来获取到 Callable 对象中的call方法的返回值 
    - 获取方法
    - Future<V> f1
    - f1.get()  获取到值（结果只能在计算完成后get‘进行检索，如有必要，阻塞，直到准备就绪）

- - ```
    package TestSychoronized;
    
    import java.util.concurrent.*;
    
    public class TestCallable {
        public static void main(String[] args) throws ExecutionException, InterruptedException {
            ExecutorService es = Executors.newCachedThreadPool();
    
            Callable<Integer> task1 = new Callable<Integer>() {
                @Override
                public Integer call() throws Exception {
                    int result = 0;
                    for (int i = 1; i < 100; i+=2) {
                        result += i;
                        Thread.sleep(100);
                    }
                    return result;
                }
            };
            Callable<Integer> task2 = new Callable<Integer>() {
                @Override
                public Integer call() throws Exception {
                    int result = 0;
                    for (int i = 2; i < 100; i+=2) {
                        result += i;
                        Thread.sleep(100);
                    }
                    return result;
                }
            };
    
            Future<Integer> f1 = es.submit(task1);
            Future<Integer> f2 = es.submit(task2);
            System.out.println("");
    
            int result = f1.get()+f2.get();
            System.out.println(result);
    
    
        }
    }
    
    ```

    


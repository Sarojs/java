# java
Threading

1. In how many ways can thread be created in Java SpringBoot?
    - @Async (@EnableAsync)
    - ThreadPoolExecutor
    - ExecutorService service = Executors.newFixedThreadPool(5); service.execute(task);
    - Thread and Runnable
    - CompletableFuture.supplyAsync(task, taskExecutor);
  
2. What is optimal number for a ThreadPool size? How to get number of cores available on the system?
   - Runtime().getRuntime.getAvailableProcessor()
3. types of thread pools
  - fixedThreadPool
  - cachedThreadPool(),
  - scheduledThreadPool(),
  - singleThreadedExecutor()
4. Runnable interface vs Callable interface (run(), call())
5. Concurrency vs Parallelism
6. ForkJoinPool
7. FunctionalInterface
  - single abstract method (ex. Consumer, Function, Runnable
8. What are the advantages and disadvantages of Collections.synchronizedCollection(Collection<T>)
9. java.util.concurrent
  - ConcurrentHashMap(shared cache), CopyOnWriteArrayList, CopyOnWriteArraySet, ConcurrentLinkedQueue(Producer-consumer, task queues)
10. @EnableScheduling
    - Enables scheduling support for methods annotated with @Scheduled
10. @RestControllerAdvice, @Primary, @Qualifier
11. @ConfigurationProperties(prefix = "app"), @Value
11. @PropertySource
  - Specifies a custom properties file to load into the Spring environment. @PropertySource("classpath:custom.properties")
11. @Bean @ConditionalOnProperty(name = "app.cache.enabled", havingValue = "true")
    - Conditionally includes beans or configurations based on properties, classes, or other conditions.
11. @Profile
11. GET, POST, PUT, DELETE, PATCH
12. N+1 problem
13. @Transactional
14. equals(), ==, hashCode()

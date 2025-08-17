# java
Threading

1. In how many ways can thread be created in Java SpringBoot?
    - @Async (@EnableAsync)
    - ThreadPoolExecutor
    - ExecutorService service = Executors.newFixedThreadPool(5); service.execute(task);
    - Thread and Runnable
    - CompletableFuture.supplyAsync(task, taskExecutor);
  
2. What is optimal number for a ThreadPool size? How to get number of cores available on the system?
   - Runtime.getRuntime().availableProcessors()
3. Types of thread pools
  - fixedThreadPool
  - cachedThreadPool
  - scheduledThreadPool
  - singleThreadedExecutor
4. Runnable interface vs Callable interface (run(), call())
Ans:
The Runnable and Callable interfaces in Java are both used to represent tasks that can be executed by a thread, but they have important differences.

The Runnable interface is older and simpler. It defines a single method, run(), which does not return a result and cannot throw a checked exception. You typically use Runnable when you want to execute code concurrently but do not need a result from the task.

The Callable interface, introduced in Java 5, is more flexible. It defines a single method, call(), which can return a result and throw checked exceptions. This makes Callable suitable for tasks that produce a result or might fail with an exception. When you submit a Callable to an ExecutorService, it returns a Future object, which you can use to retrieve the result or handle exceptions.

In summary, use Runnable for simple tasks that do not return a result, and use Callable when you need the task to return a value or throw an exception.

5. Concurrency vs Parallelism
6. ForkJoinPool
7. FunctionalInterface
  - single abstract method (ex. Consumer, Function, Runnable)
8. What are the advantages and disadvantages of Collections.synchronizedCollection(Collection<T>)
9. java.util.concurrent
  - ConcurrentHashMap (shared cache), 
  CopyOnWriteArrayList, CopyOnWriteArraySet, ConcurrentLinkedQueue (Producer-consumer, task queues)
10. @EnableScheduling
    - Enables scheduling support for methods annotated with @Scheduled
11. @RestControllerAdvice, @Primary, @Qualifier
12. @ConfigurationProperties(prefix = "app"), @Value
13. @PropertySource
  - Specifies a custom properties file to load into the Spring environment. @PropertySource("classpath:custom.properties")
14. @Bean @ConditionalOnProperty(name = "app.cache.enabled", havingValue = "true")
    - Conditionally includes beans or configurations based on properties, classes, or other conditions.
15. @Profile
16. GET, POST, PUT, DELETE, PATCH
17. N+1 problem
18. @Transactional
19. equals(), ==, hashCode()
20. How will you handle shutdown of a service when it is already processing a request?
Ans:
Set below properties in application.properties file.
server.shutdown=graceful // This stops any new incoming requests (returns 503 - Service Unavailable) and allows already running requests to finish for the time defined by below property.
spring.lifecycle.timeout-per-shutdown-phase=30s

21. How to configure the available threads in spring boot application to handle concurrent requests?
Ans: Set below properties to allow more threads to run concurrently.
server.tomcat.max-threads=200    // default is 200. Thread pool size for the service.
server.tomcat.accept-count=100    // Maximum number of requests that will wait for any thread to be available to be assigned to the request. Is used when all threads are occupied by incoming requests.

22. What is the flow of an http request?
Ans: client > network > server port (Tomcat) > Servlet Container > DispatcherServlet > Filters, if any (Authentication) > Controller > Request Mapping > Service layer > Response building > DispatcherServlet > network > client


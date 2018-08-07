# String Builder vs String buffer:

Another beauty of Java, it provides two classes to break the immutable nature. Both String buffer and String builder is like a String, but mutable. It means their object values can be changed after they are created. String Builder was introduced in JDK 1.5 whereas, String buffer is available since with the version 1.0.

Both provides much of the same functionality like strings. But what makes it better one with the other. Let us understand the difference better between both with the following example:


```
public class SampleStringTest{
public static void main(String[] args){
 long startTime = System.currentTimeMillis();
 StringBuilder sb1 = new StringBuilder("Hello");
 for (int i=0; i<10000; i++){
  sb1.append("world");}
 System.out.println("Time taken by StringBuilder: " +    (System.currentTimeMillis() - startTime) + "ms");
 startTime = System.currentTimeMillis();
 StringBuffer sb2 = new StringBuffer("Hello");
 for (int i=0; i<10000; i++){
 sb2.append("world");}
 System.out.println("Time taken by StringBuffer: " +  (System.currentTimeMillis() - startTime) + "ms");}
}
```

The result will be,

Time taken by StringBuilder: 0ms

Time taken by StringBuffer: 15ms

We can now say from the result that performance of StringBuilder is more efficient than StringBuffer. Another major difference is that StringBuffer is synchronized (i.e) thread safe , while StringBuilder is non-synchronized and not thread safe.

More about synchronized, StringBuffer is synchronized which means multiple threads can access, and modify it without any problem, whereas StringBuilder is not synchronized by default and can be accessed only by a single thread.

Which is best to use and when?

* If you need a string, which can be modifiable, and only one thread is accessing and modifying it, you can use StringBuilder.
* If you need a string, which can be modifiable, and multiple threads are accessing and modifying it, then go for StringBuffer.


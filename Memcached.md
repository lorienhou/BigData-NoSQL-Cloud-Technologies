Open source, high-performance, distributed memory caching system intended to speed up dynamic web applications by reducing the database load.
Key-value dictionary of strings, objects, etc (a big hash table), stored in the memory, resulting from database calls, API calls, or page rendering.
It's NOT:
a persistent data store/database/object cache/fault-tolerant/highly available.

Start Memcached with specific port, username and as daemon:
$memcached -p 11111 -U 11111 -u user -d

To use Memcached in java, need spymemcached jar.

Connect to Memcached directly:
$telnet HOST PORT

Connect to Memcached from java:
```java
import net.spy.memcached.MemcachedClient;
import java.net.*;

public class MemcachedJava {
   public static void main(String[] args) {
      try{
         // Connecting to Memcached server on localhost
         MemcachedClient mcc = new MemcachedClient(new InetSocketAddress("127.0.0.1", 11211));
         System.out.println("Connection to server sucessful.");
         
         // Shutdowns the memcached client
         mcc.shutdown();
         
      }catch(Exception ex){
         System.out.println( ex.getMessage() );
      }
   }
}
```

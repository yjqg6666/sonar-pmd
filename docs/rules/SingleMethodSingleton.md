# SingleMethodSingleton
**Category:** `pmd`<br/>
**Rule Key:** `pmd:SingleMethodSingleton`<br/>


-----

<p>
  Some classes contain overloaded getInstance. The problem with overloaded getInstance methods is that the instance
  created using the overloaded method is not cached and so, for each call and new objects will be created for every
  invocation.
</p>

<p>Examples:</p>
<pre>
public class Singleton {
  private static Singleton singleton = new Singleton( );

  private Singleton() { }

  public static Singleton getInstance( ) {
    return singleton;
  }

  public static Singleton getInstance(Object obj) {
    Singleton singleton = (Singleton) obj;
    return singleton; //violation
  }
}
</pre>

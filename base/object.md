```java

java.lang.Object

public class Object {

    public boolean equals(Object obj) // сравнивает, оыбчно переобпределяют
    public native int hashCode(); // вместе с equals переобпределяют

    protected  Object clone()
    public String toString()

    public final native Class<?> getClass();
    public final native void notify();
    public final native void notifyAll();
    public final void wait()

}


```
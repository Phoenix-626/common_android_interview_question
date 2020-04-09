1. java中 `==` 和 `equals` 和 `hashCode` 的区别
```java
public class Object {
    public boolean equals(Object obj) {
        return (this == obj);
    }

    public int hashCode() {
        return identityHashCode(this);
    }

    // Package-private to be used by j.l.System. We do the implementation here
    // to avoid Object.hashCode doing a clinit check on j.l.System, and also
    // to avoid leaking shadow$_monitor_ outside of this class.
    /* package-private */ static int identityHashCode(Object obj) {
        int lockWord = obj.shadow$_monitor_;
        final int lockWordStateMask = 0xC0000000;  // Top 2 bits.
        final int lockWordStateHash = 0x80000000;  // Top 2 bits are value 2 (kStateHash).
        final int lockWordHashMask = 0x0FFFFFFF;  // Low 28 bits.
        if ((lockWord & lockWordStateMask) == lockWordStateHash) {
            return lockWord & lockWordHashMask;
        }
        return identityHashCodeNative(obj);
    }
}
```
[How to implement hashCode ?](https://www.baeldung.com/java-hashcode)

2. [String、StringBuffer、StringBuilder区别](https://www.geeksforgeeks.org/string-vs-stringbuilder-vs-stringbuffer-in-java/)
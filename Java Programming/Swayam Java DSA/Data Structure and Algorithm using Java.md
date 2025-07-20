## Generic Method

```java
import java.io.;
import java.util.;
class DemoClass{
	<T> void genericPrint(T t){
		System.out.println(t);
	}
}
public class Array{
	public static void main(String[] args){
		DemoClass aobj= new DemoClass();
		aobj.genericPrint("Hello");
		aobj.genericPrint(234);
		aobj.genericPrint(434.445);

	}
}
```

It can handle all data types.

## Generic Static Method

```java
import java.io.*;
import java.util.*;
class staticgeneric{
	static <T> void genericPrint(T t){
		System.out.println(t.getClass().getName() + " "+ t);
	}
}
public class Array{
	public static void main(String[] args){
		staticgeneric.genericPrint("hello");
		staticgeneric.genericPrint(1233);
		staticgeneric.genericPrint(434.4545);
	}
}
```


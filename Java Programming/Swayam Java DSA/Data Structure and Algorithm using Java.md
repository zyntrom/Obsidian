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

Its does not require to create an instance of the class (Because its static)

### Example Program:

```java
import java.io.*;
import java.util.*;
class Box<T>{
	T value;
	Box(T value){
		this.value=value;
	}
}
public class Array{
	
	public static <T> void swap(Box<T> x, Box<T> y){
		T temp;
		temp=x.value;
		x.value=y.value;
		y.value=temp;
	}
	public static void main(String[] args){
		
		Box<Integer >x=new Box<>(56);
		Box<Integer >y= new Box<>(676);
		System.out.println("x : "+x.value+" "+"y : "+y.value);
		swap(x,y);
		System.out.println("x : "+x.value+" "+"y : "+y.value);
	}
}
```

Generic < T > Swap Program (Change the Integer to Any data Type)
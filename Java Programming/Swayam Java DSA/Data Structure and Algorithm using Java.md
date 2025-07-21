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

- Generic < T > Swap Program (Change the Integer to Any data Type)

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

- Generic Program to wrap tow objects:

```java
import java.io.*;
import java.util.*;
class Box<T>{
	T value;
	Box(T value){
		this.value=value;
	}
}

class Person{
	String name;
	double mark;

	Person(String name,double mark){
		this.name=name;
		this.mark=mark;
	}
	public String toString(){
		return name +" : "+ mark;
	}
}
public class Array{
	public static <T> void swap(Box<T> x,Box<T> y ){
		T t= x.value;
		x.value=y.value;
		y.value=t;
	}
	public static void main(String[] args){
		Box<Person >x =new Box<>(new Person("Alen",343.454));
		Box<Person >y= new Box<>(new Person("Lajeesh",656.343));

		System.out.println(x.value+" "+y.value);
		swap(x,y);
		System.out.println(x.value+" "+y.value);
	}
}
```

## Variable Number of Arguments

- Method 1: (Arrays)

```java
import java.io.*;
import java.util.*;
public class Array{
	public static <T> void varargsMethod1(T v[]){
		System.out.println("The number of args "+v.length+" ,The elements are :");

		for(int i=0;i<v.length;i++){
			System.out.print(v[i]+" ");
		}
		System.out.println();
	}
	public static void main(String[] args){
		Integer x[]={1,2,3,4};
		Integer y[]={1,2,3}; 
		Integer z[]={1,2};
		
		varargsMethod1(x);
		varargsMethod1(y);
		varargsMethod1(z);
	}
}
```

- Method 2: (Ellipsis)

```java
import java.io.;
import java.util.;
public class Array{
	public static <T> void vararg(T ...v){
		System.out.println("The var length "+v.length);
		for(T i: v){
			System.out.print(i+" ");
		}
		System.out.println();
	} 
	public static void main(String[] args){
		vararg(1,4,-1,"ssfs");
		vararg("34","878");
		vararg(76.565,576.343);
	}
}
```

- Method 3: (Object)

```java
import java.io.;
import java.util.;
public class Array{
	public static void varargs(Object ...obj){
		for(Object i: obj){
			System.out.print(i+" ");
		}
		System.out.println();
	}
	public static void main(String args){
		varargs(1,3,"sds",343.343);
		varargs(1232,"dvdsdds",433343.343);
		varargs(832,3,"sds",343.343);
	}
} 
```

## Generic Class 

```java
import java.io.*;
import java.util.*;
class SpecArray<T>{
	T a[];
	SpecArray(T a[]){
		this.a=a;
	}
	void printint(){
		for(T i:a){
			System.out.print(i+" ");
		}
		System.out.println();
	}
	void reverseInt(){
		int j=a.length-1;
		for(int i=0;i<j;i++){
			T temp=a[i];
			a[i]=a[j];
			a[j]=temp;
			j--;
		}
	}
}
public class Array{

	public static void main(String[] args){
		Object a[]= {"2323",344.454,3454,'D'};
		SpecArray<Object> arr= new SpecArray<>(a);
		arr.printint();
		arr.reverseInt();
		arr.printint();
	}
}
```

## Passing Two Values to Generic Class

```java
import java.io.*;
import java.util.*;
class Generic2<T, V>{
	T obj1;
	V obj2;

	Generic2(T obj1, V obj2){
		this.obj1=obj1;
		this.obj2=obj2;
	}

	void print(){
		System.out.print(obj1+" "+obj2);
	} 
}
public class Array{
	public static void main(String[] args){
		
		Generic2<Integer, String> a=new Generic2<>(1,"Hello");

		a.print();
	}
}  
```
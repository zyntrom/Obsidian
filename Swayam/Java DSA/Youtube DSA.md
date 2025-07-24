- Dynamic Array:

```java
import java.io.;
import java.util.;
class DynamicArray <T> implements Iterable <T>{
	T arr[];
	int capacity=0;
	int len=0;

	DynamicArray(){
		this(16);
	}
	DynamicArray(int capacity){
		this.capacity=capacity;
		arr= (T[]) new Object[capacity]; 
	}
	int size(){
		return len;
	}
	boolean isEmpty(){
		return size()==0;
	}
	T get(int index){
		return arr[index];
	}
	void set(int index,T elem){
		arr[index]=elem;
	}
	void clear(){
		for(int i=0;i<capacity;i++){
			arr[i]=null;
		}
		len=0;
	}
	void add(T elem){
		if(len+1>=capacity){
			if(capacity==0){
				capacity=1;
			}else{
				capacity*=2;
				T new_array[]= (T[])new Object[capacity];
				for(int i=0;i<len;i++){
					new_array[i]=arr[i];
				}
				arr=new_array;
			}
		}
		arr[len++]=elem;
	
	}
	T removeAt(int rm_index){
		if(rm_index>=len ||rm_index<0) throw new IndexOutOfBoundsException();
		T data= arr[rm_index];
		T[] new_array= (T[]) new Object[len-1];
		for(int i=0,j=0;i<capacity;j++,i++){
			if(rm_index==i)j--;
			else{
				new_array[j]=arr[i];
			}
		}
		arr=new_array;
		capacity=len-1;
		return data;
	}
	boolean remove(Object obj){
		for(int i=0;i<len;i++){
			if(arr[i].equals(obj)){
				removeAt(i);
				return true;
			}
			
		}
		return false;
	}
	int indexOf(Object obj){
		for(int i=0;i<len;i++){
			if(arr[i].equals(obj)){
				return i;
			}
		}	
		return -1;
	}
	boolean contains(Object obj){
		return (indexOf(obj) != -1);
	}
	@Override public java.util.Iterator <T> iterator(){
		return new java.util.Iterator<T>() {
			int index=0;
			public boolean hasNext() {return index<len;}
			public T next() {return arr[index++];}
		};
	}
	@Override public String toString(){
		if(len==0) return "[]";
		else{
			StringBuilder sr= new StringBuilder(len).append("[");
			for(int i=0;i<len-1;i++){
				sr.append(arr[i]+", ");
			}
			return sr.append(arr[len-1]+"]").toString();
		}
	}
}
public class Array{
	public static void main(String[] args){
			
		DynamicArray<Object> arr = new DynamicArray<>();
		arr.add("Hello");
		arr.add(1);
		System.out.println(arr);
	}
}   
```

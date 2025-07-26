![[Pasted image 20250726122213.png]]
## Dynamic Array:

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

## Linked List: (ChatGpt Ver.)

```java
import java.io.*;
import java.util.*;
class Node{
	int data;
	Node next;
	Node(int data){
		this.data=data;
		this.next=null;
	}
}
class Linked{
	Node head;
	void add(int data){
		Node newNode = new Node(data);
		if(head==null){
			head=newNode;
			return;
		}
		Node curr=head;
		while(curr.next!=null){
			curr=curr.next;
		}
		curr.next=newNode;
				
	}
	void print(){
		Node curr = head;
		while(curr!=null){
			System.out.print(curr.data+"->");
			curr=curr.next;
		}
		System.out.print("null");
	}
	void delete(int value){
		if(head==null) return;
		if(head.data==value){
			head=head.next;
			return;
		}
		Node curr=head;
		while(curr.next!=null && curr.next.data!=value){
			curr=curr.next;
		}
		if(curr.next!=null){
			curr.next=curr.next.next;
		}
	}

}
public class Linkedlist{
	public static void main(String[] args){
		Linked arr= new Linked();
		arr.add(844);
		arr.add(343);
		arr.add(8);
		arr.print();
		arr.delete(343);
		arr.print();
	}
}
```

## Doubly Linked List :(ChatGpt)

```java
import java.io.*;
import java.util.*;
class Node{
	int data;
	Node next;
	Node prev;

	Node(int data){
		this.data=data;
		this.next=null;
		this.prev=null;
	}

}
class DoubleLinked{
	Node head;
	void add(int data){
		Node newNode= new Node(data);
		if(head==null){
			head=newNode;
			return;
		}

		Node curr=head;
		while(curr.next!=null){
			curr=curr.next;
		}
		curr.next=newNode;
		newNode.prev=curr;
	}
	void delete(int value){
		if(head==null)return;
		Node curr=head;
		if(head.data==value){
			head=head.next;
			if(head!=null){
				head.prev=null;
			}
			return;
		}
		while(curr!=null && curr.data!=value){
			curr=curr.next;
		}
		if(curr==null) return;

		if(curr.prev!=null) curr.prev.next=curr.next;
		if(curr.next!=null) curr.next.prev=curr.prev;
	}
	void printNext(){
	Node curr = head;
	while(curr != null){
		System.out.print(curr.data);
		if(curr.next != null)
			System.out.print("<->");
		curr = curr.next;
	}
	System.out.println("<->null\n");
	}
	
	void printPrev(){
		if(head == null) return;

		Node curr = head;
		// Go to the last node
		while(curr.next != null){
			curr = curr.next;
		}
		System.out.print("null<->");
		while(curr != null){
			System.out.print(curr.data);
			if(curr.prev != null)
				System.out.print("<->");
			curr = curr.prev;
			}
		System.out.println();
	}
}
	
public class Linkedlist{
	public static void main(String[] args){
		DoubleLinked arr= new DoubleLinked();	
		arr.add(23);
		arr.add(876);
		arr.add(233);
		arr.add(2);

		arr.printNext();
		arr.printPrev();

		arr.delete(876);

		arr.printNext();
		arr.printPrev();

	}
}
```

## Stack  (ChatGpt)

```java
import java.io.*;
import java.util.*;

class Stack{
	int maxSize=100;
	int stack[] = new int[maxSize];
	int top=-1;
	void push(int value){
		if(top==maxSize-1){
			System.out.print("Statck Overflow");
			return;
		}
		top++;
		stack[top]=value;
	}
	int pop(){
		if(top==-1){
			System.out.print("Stack underflow");
			return -1;
		}
		int val= stack[top];
		top--;
		return val;
	}
	int peek(){
		if(top==-1){
			System.out.print("Stack is empty");
			return -1;
		}
		return stack[top];
	}
	boolean isEmpty(){
		return top==-1;
	}
	void print(){
		for(int i=top;i>=0;i--){
			System.out.print(stack[i]+" ");
		}
		System.out.println();
	}
}
public class Linkedlist{
	public static void main(String[] args){
		Stack stack= new Stack();

		stack.push(23);
		stack.push(454);
		stack.push(27878);
		stack.push(3);

		stack.print();
		System.out.println(stack.pop());
		System.out.println(stack.pop());
		stack.print();
	}
}
```

## Queue (ChatGpt)

```java
import java.io.*;
import java.util.*;
class Queue{
	int maxSize= 100;
	int[] queue=new int[maxSize];
	int front=0;
	int rear=-1;

	void enqueue(int value){
		if(rear==maxSize-1){
			System.out.print("Queue Overflow");
			return;
		}
		rear++;
		queue[rear]=value;
	}
	int dequeue(){
		if(front>rear){
			System.out.print("Queue is underflow");
			return -1;
		}
		int val= queue[front];
		front++;
		return val;
	}
	int peek(){
		if(front>rear){
			System.out.print("Queue is empty");
			return -1;
		}
		int val=queue[front];
		return val;
	}
	boolean isEmty(){
		return front>rear;
	}
	void printQueue(){
		for(int i=front;i<=rear;i++){
			System.out.print(queue[i]+" ");
		}
		System.out.println();
	}
}
public class Linkedlist{
	public static void main(String[] args){
		Queue qu= new Queue();
		qu.enqueue(233);
		qu.enqueue(3);
		qu.enqueue(656);
		qu.enqueue(4576);
		qu.printQueue();
		System.out.println(qu.dequeue());
		System.out.println(qu.dequeue());	
		qu.printQueue();
	}
}
```

## Circular Queue

```java
import java.io.*;
import java.util.*;
class CQueue{
	int size;
	int front,rear;
	int[] queue;
	CQueue(int size){
		this.size=size;
		front =-1;
		rear=-1;
		queue =new int[size];
	}
	void enqueue(int data){
		if((rear+1)%size==front){
			System.out.print("Queue is Full");
			return;
		}
		if(front==-1){
			front=0;
		}
		rear=(rear+1)%size;
		queue[rear]=data;
	}
	int dequeue(){
		if(front==-1){
			System.out.print("Queue is empty");
			return -1;
		}
		int val=queue[front];
		if(front==rear){
			front=rear=-1;
		}
		else{
			front =(front+1)%size;
		}
		return val;
	}
	void print(){
		if(front==-1){
			System.out.print("Queue is Empty");
			return;
		}
		int i=front;
		while(true){
			
			System.out.print(queue[i]+" ");
			if(i==rear){ break;}
			i=(i+1)%size;
		}
		System.out.println();
	}
}
public class CirQueue{
	public static void main(String[] args){
		CQueue queue= new CQueue(4);
		queue.enqueue(45);		 
		queue.enqueue(676);		
		queue.enqueue(7);
		queue.print();
		System.out.println(queue.dequeue());
		System.out.println(queue.dequeue());
		queue.print();
	}
}
```
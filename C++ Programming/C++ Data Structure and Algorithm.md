- Linked List:

```c++
#include<iostream> 
using namespace std;
struct Node{
	int data;
	Node* next=NULL;
};
void insertData(Node*& head,int value){
	Node* newNode= new Node();

	newNode->data=value;
	newNode->next=NULL;

	if(head==NULL){
		head=newNode;
	}
	else{
		Node* curr=head;
		while(curr->next!=NULL){
			curr=curr->next;
		}
		curr->next=newNode;
	}

}
void print(Node*& head){
	Node* curr=head;
	while(curr!=NULL){
		cout<<curr->data<<" ";
	}
	cout<<endl;
}

int main(){
	Node* list=NULL;
	insertData(list, 20);
	insertData(list, 2);
	insertData(list, 67);
	insertData(list, 98);

	print(list);
	return 0;

}
```


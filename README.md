# EXPERIMENT 19
# AIM:
To study and implement linked list.

# THEORY:
A linked list is a basic data structure in computer science that stores a collection of elements, with each element (node) pointing to the next one, forming a sequence. Unlike arrays, linked lists have dynamic memory allocation, which allows them to grow and shrink as needed.

Types of Linked Lists

Singly Linked List: Each node points to the next node in the list, and the last node points to nullptr.

Doubly Linked List: Each node points to both the next and the previous node, allowing traversal in both directions.

Circular Linked List: The last node points back to the first node, forming a circle.

Basic Operations

Insertion: Adding a node to the list at the beginning, middle, or end.

Deletion: Removing a node from the list based on its value or position.

Traversal: Visiting each node in the list to display or process its data.

1.LINKED LIST:
```
#include<iostream>
using namespace std; 
 
 class Link {
    public:
    int data;
    Link* next;
    Link(int num) {
        data=num;
        next=NULL;
    }
 };
 void insert_head(Link* &head, int data) {
    Link* new_node=new Link(data);
    new_node->next = head; 
    head = new_node;
 }
 void disp(Link* head) {
    Link* temp = head;
    while(temp!=NULL) { 
        cout<<temp->data<<"->";
        temp = temp->next;
    } 
    cout<<"NULL"<<endl;
 }
 int main() {
    Link* head = NULL;
    insert_head(head, 30);
    disp(head);
    insert_head(head, 32);
    disp(head);
    insert_head(head, 35);
    disp(head);
    //l1.disp(); 
 }
```
OUTPUT:

![image](https://github.com/user-attachments/assets/7692c4eb-049c-4974-985d-348e371af11c)


2.INSERTING, DISPLAYING, AND DELETING LINKED LIST NODES.:
```
#include<iostream>
using namespace std; 
 
class Link {
    public:
    int data;
    Link* next;
    Link(int num) {
        data = num;
        next = NULL;
    }
};
// Function to insert a new node at the head of the list
void insert_head(Link* &head, int data) {
    Link* new_node = new Link(data);
    new_node->next = head; 
    head = new_node;
}
// Function to display the linked list
void disp(Link* head) {
    Link* temp = head;
    while(temp != NULL) { 
        cout << temp->data << "->";
        temp = temp->next;
    } 
    cout << "NULL" << endl;
}
// Function to delete a node with a specific value
void delete_node(Link* &head, int value) {
    if(head == NULL) {
        cout << "List is empty, nothing to delete." << endl;
        return;
    }
    Link* temp = head;
    Link* prev = NULL;

    // If the node to be deleted is the head node
    if(temp != NULL && temp->data == value) {
        head = temp->next; // Change the head
        delete temp;       // Free memory
        return;
    }
    // Search for the node to be deleted, keeping track of the previous node
    while(temp != NULL && temp->data != value) {
        prev = temp;
        temp = temp->next;
    }
    // If the node was not found
    if(temp == NULL) {
        cout << "Node with value " << value << " not found." << endl;
        return;
    }
    // Unlink the node from the linked list
    prev->next = temp->next;
    // Free memory
    delete temp;
}
int main() {
    Link* head = NULL;
    insert_head(head, 30);
    disp(head);
    insert_head(head, 32);
    disp(head);
    insert_head(head, 35);
    disp(head);
    // Delete a node
    delete_node(head, 32); // Deleting node with value 32
    disp(head);
    delete_node(head, 35); // Deleting node with value 35
    disp(head);
    delete_node(head, 100); // Attempting to delete a non-existent node
    disp(head);
}
```
OUTPUT:

![image](https://github.com/user-attachments/assets/6d7ce469-a865-44de-9ad5-cc69d8bc7802)


# CONCLUSION:
The experiment successfully demonstrated the importance and efficiency of linked lists in C++ programming. The implementation highlighted the advantages of linked lists in terms of dynamic memory management and operation efficiency, while also emphasizing the need for careful pointer management to avoid memory leaks or crashes. This experiment forms a crucial step toward understanding more advanced data structures and algorithms.


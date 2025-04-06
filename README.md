
******************* DSA-Lab-Task ******************* 
################### LAB#01 ###################
             ********** TASK 01  **********
          
#include<iostream>
using namespace std;
int main() {
    int arr[8] = {10, 20, 30, 40, 50, 60, 70, 80};
    cout << "Original array: ";
    for (int i = 0; i < 8; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;
    for (int i = 0; i < 7; i++) {
        arr[i] = arr[i + 1];
    }
    arr[6] = 0;
    cout << "Array after deleting the first and last elements: ";
    for (int i = 0; i < 7; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;
    return 0;
}
                 ********** TASK 02  **********
#include <iostream>
using namespace std;
int main() {
    int arr[8] = {10, 20, 30, 40, 50, 60, 70, 80};
    int index, newValue;
    cout << "Original array: ";
    for (int i = 0; i < 8; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;
    cout << "Enter the index : ";
    cin >> index;
    if (index >= 0 || index < 8) {
        cout << "Enter the new value: ";
        cin >> newValue;
        arr[index] = newValue;
        cout << "Updated array: ";
        for (int i = 0; i < 8; i++) {
            cout << arr[i] << " ";
        }
        cout << endl;
    } else {
        cout << "Invalid index." << endl;
    }
    return 0;
}
                  ********** TASK 03  **********
#include <iostream>
using namespace std;
int main() {
    int arr[8] = {10, 20, 30, 40, 50, 60, 70, 80};
    cout << "Original array: ";
    for (int i = 0; i < 8; i++) {
        cout << arr[i] << " " << endl;
    }
    cout << "enter elements in reverse order:";
    for (int i = 7; i > 0; i--) {
        cout << arr[i] << " " << endl;
    }
    return 0;
}
                ################### LAB#02 ###################
                      ********** TASK 01  **********
            
#include <iostream>
using namespace std;
int main()
{
    int arr[5] = {10, 20, 30, 40, 50};
    int *ptr = arr;
    for (int i = 0; i < 5; ++i)
{
        cout << "Element" << i+1 <<" : " << *ptr << endl;
        ptr++;
    }
    return 0;
}
                        ********** TASK 02  **********
#include <iostream>
using namespace std;
void change(int *a, int *b) {
    int temp = *a;  
    *a = *b;        
    *b = temp;      
}
int main() {
    int x = 5, y = 10;
    cout << "Before changing x: "<<endl;
cout<<  x << " y = " << y << endl;
    change(&x, &y);
    cout << "After changing x:"<<endl;
cout << x << " y = " << y << endl;
    return 0;
}
                ################### LAB#03 ###################
                       ********** TASK 01  **********
#include <iostream>
using namespace std;
int main() {
    int n;
    cout << "Enter the size of the array: ";
    cin >> n;
    int* arr = new int[n];
    cout << "Enter " << n << " elements: ";
    for (int i = 0; i < n ; i++) {
        cin >> arr[i];
}
 for (int i = 0; i < n ; i++)
 {
      int even=0, odd=0;
        if (arr[i] % 2 == 0)
            even++;
        else
            odd++;
        }
    }
    cout << "even numbers: " << even << endl;
    cout << "odd numbers: " << odd << endl;
    delete[] arr;
    return 0;
}
                       ********** TASK 02  **********
#include <iostream>
using namespace std;
int main()
 {
    int n;
    cout << "Enter number of elements: ";
    cin >> n;
    int* arr = new int[n];
    cout << "Enter numbers: ";
     for (int i = 0; i < n ; i++)
{
    cin >> arr[i];
}
    int max = arr[0], min = arr[0];
    for (int i = 1; i < n; i++) {
        cin >> arr[i];
        if (arr[i] > max) max = arr[i];
        if (arr[i] < min) min = arr[i];
    }
    cout << "Maximum: " << max  << endl;
    cout << "Minimum: " << max  << endl;
    delete[] arr;
    return 0;

                ################### LAB#04 ###################
                       ********** TASK 01  **********
  #include <iostream>
using namespace std;
struct Node {
    int data;
    Node* next;
};
void insertEnd(Node*& head, int value) {
    Node* newNode = new Node;
    newNode->data = value;
    newNode->next = nullptr;
    if (head == nullptr) {
        head = newNode;
        return;
    }
    Node* temp = head;
    while (temp->next != nullptr) {
        temp = temp->next;
    }

    temp->next = newNode;
}
void display(Node* head) {
    Node* temp = head;
    while (temp != nullptr) {
        cout << temp->data << " -> ";
        temp = temp->next;
    }
    cout << "NULL\n";
}
int main() {
    Node* head = nullptr; 
    insertEnd(head, 10);
    insertEnd(head, 20);
    insertEnd(head, 30);
    insertEnd(head, 40);
    cout << "Linked List: ";
    display(head);
    return 0;
} 

                    ********** TASK 02  **********
   #include <iostream>
using namespace std;
struct Node {
    int data;
    Node* next;
};
void insertEnd(Node*& head, int data) {
    Node* newNode = new Node{data, nullptr};
    if (!head) {
        head = newNode;
        return;
    }
    Node* temp = head;
    while (temp->next)
        temp = temp->next;
    temp->next = newNode;
}
void display(Node* head) {
    Node* temp = head;
    while (temp) {
        cout << temp->data << " -> ";
        temp = temp->next;
    }
    cout << "NULL\n";
}
void deleteStart(Node*& head) {
    if (!head) {
        cout << "List is empty!\n";
        return;
    }
    Node* temp = head;
    head = head->next;
    delete temp;
}
void deleteAtPosition(Node*& head, int pos) {
    if (!head) {
        cout << "List is empty!\n";
        return;
    }
    if (pos == 1) {
        deleteStart(head);
        return;
    }
    Node* temp = head;
    for (int i = 1; temp && i < pos - 1; i++)
        temp = temp->next;
    
    if (!temp || !temp->next) {
        cout << "Position out of range!\n";
        return;
    }

    Node* toDelete = temp->next;
    temp->next = temp->next->next;
    delete toDelete;
}
void deleteEnd(Node*& head) {
    if (!head) {
        cout << "List is empty!\n";
        return;
    }
    if (!head->next) {
        delete head;
        head = nullptr;
        return;
    }
    Node* temp = head;
    while (temp->next->next)
        temp = temp->next;
    delete temp->next;
    temp->next = nullptr;
}
int main() {
    Node* head = nullptr;
    insertEnd(head, 10);
    insertEnd(head, 20);
    insertEnd(head, 30);
    insertEnd(head, 40);
    insertEnd(head, 50);
    insertEnd(head, 60);

    cout << "Original List: ";
    display(head);
    deleteStart(head);
    cout << "After deleting start node: ";
    display(head);
    deleteAtPosition(head, 4);
    cout << "After deleting node at position 4: ";
    display(head);
    deleteEnd(head);
    cout<<"After deleting last node:";
    display(head);
    return 0;
}                   

                 ################### LAB#05 ###################
                       ********** TASK 01  **********

  #include <iostream>
using namespace std;
struct Node {
    int data;
    Node* next;
    Node* prev;
};
void print_data(Node* head) {
    if (head == NULL) {
        cout << "Linked list is empty" << endl;
        return;
    }
    Node* ptr = head;
    while (ptr != NULL) {
        cout << ptr->data << " ";
        ptr = ptr->next;
    }
    cout << endl;
}
Node* at_start(Node* head) {
    if (head == NULL) {
        cout << "The list is empty." << endl;
        return NULL;
    }
    Node* temp = head;
    head = head->next;  
    if (head != NULL) {
        head->prev = NULL; 
    }
    delete temp;  
    return head;  
}
int main() {
    Node* node1 = new Node();
    Node* node2 = new Node();
    Node* node3 = new Node();
    cout << "Enter value for Node 1: ";
    cin >> node1->data;
    node1->prev = NULL;
    node1->next = node2;

    cout << "Enter value for Node 2: ";
    cin >> node2->data;
    node2->prev = node1;
    node2->next = node3;
    cout << "Enter value for Node 3: ";
    cin >> node3->data;
    node3->prev = node2;
    node3->next = NULL;
    Node* head = node1; 
    head = at_start(head);
    cout << "Linked list after deleting first node: ";
    print_data(head);
    while (head != NULL) {
        Node* temp = head;
        head = head->next;
        delete temp;  
    }
return 0;
}

                      ********** TASK 02  **********

#include <iostream>
using namespace std;
struct Node {
int data;
Node* next;
Node* prev;
};
void print_data(Node* head) {
Node* temp = head;
while (temp != NULL) {
cout << temp->data << " ";
temp = temp->next;
}
cout << endl;
}
Node* at_position(Node* head, int position) {
if (head == NULL) {
cout << "The list is empty, nothing to delete." << endl;
return NULL;
}
Node* temp = head;
int count = 0;
while (temp != NULL) {
count++;
temp = temp->next;
}
if (position < 1 || position > count) {
cout << "Invalid position!" << endl;
return head;
}
temp = head;
if (position == 1) {
head = head->next;
if (head != NULL) {
head->prev = NULL;
}
delete temp;
return head;
}
for (int i = 1; temp != NULL && i < position; i++) {
temp = temp->next;
}
if (temp->prev != NULL) {
temp->prev->next = temp->next;
}
if (temp->next != NULL) {
temp->next->prev = temp->prev;
}
delete temp;
return head;
}
int main() {
Node* node1 = new Node{60, nullptr, nullptr};
Node* node2 = new Node{70, nullptr, node1};
Node* node3 = new Node{80, nullptr, node2};
Node* node4 = new Node{90, nullptr, node3};
node1->next = node2;
node2->next = node3;
node3->next = node4;
Node* head = node1;
cout << "Original linked list: ";
print_data(head);
int position;
cout << "Enter position to delete: ";
cin >> position;
head = at_position(head, position);
cout << "Linked list after deletion: ";
print_data(head);
while (head != NULL) {
Node* temp = head;
head = head->next;
delete temp;
}
return 0;
}

                      ********** TASK 03  **********

#include <iostream>
using namespace std;
struct Node {
int data;
Node* next;
Node* prev;
};
void print_data(Node* head) {
if (head == NULL) {
cout << "Linked list is empty" << endl;
return;
}
Node* ptr = head;
while (ptr != NULL) {
cout << ptr->data << " ";
ptr = ptr->next;
}
cout << endl;
}
Node* at_end(Node* head) {
if (head == NULL) {
cout << "The list is empty." << endl;
return NULL;
}
if (head->next == NULL) {
delete head;
return NULL;
}
Node* temp = head;
while (temp->next != NULL) {
temp = temp->next;
}
temp->prev->next = NULL;
delete temp;
return head;
}
int main() {
Node* node1 = new Node;
Node* node2 = new Node;
Node* node3 = new Node;
Node* node4 = new Node;
cout << "Enter value for Node 1: ";
cin >> node1->data;
node1->prev = NULL;
node1->next = node2;
cout << "Enter value for Node 2: ";
cin >> node2->data;
node2->prev = node1;
node2->next = node3;
cout << "Enter value for Node 3: ";
cin >> node3->data;
node3->prev = node2;
node3->next = node4;
cout << "Enter value for Node 4: ";
cin >> node4->data;
node4->prev = node3;
node4->next = NULL;
Node* head = node1;
cout << "Original linked list: ";
print_data(head);
head = at_end(head);
cout << "Linked list after deleting the last node: ";
print_data(head);
while (head != NULL) {
Node* temp = head;
head = head->next;
delete temp;
}
return 0;
}

                ################### LAB#05 ###################
                       ********** TASK 01  **********

#include <iostream>
using namespace std;

struct Node {
    int data;
    Node* next;
    Node* prev;
};

Node* head = NULL;

void insertAtStart(int value) {
    Node* newNode = new Node();
    newNode->data = value;

    if (head == NULL) {
        newNode->next = newNode;
        newNode->prev = newNode;
        head = newNode;
    } else {
        Node* tail = head->prev;

        newNode->next = head;
        newNode->prev = tail;

        tail->next = newNode;
        head->prev = newNode;

        head = newNode;
    }
}

void display() {
    if (head == NULL) {
        cout << "List is empty." << endl;
        return;
    }

    Node* temp = head;
    cout << "Circular Doubly Linked List: "<<endl;
    do {
        cout << temp->data << " ";
        temp = temp->next;
    } while (temp != head);
    cout << endl;
}


int main() {
    insertAtStart(60);
    insertAtStart(70);
     insertAtStart(80);
    display();  

    return 0;
} 
                   ********** TASK 02  **********

#include <iostream>
using namespace std;

struct Node {
    int data;
    Node* next;
    Node* prev;
};

Node* head = NULL;

void insertAtPosition(int value, int position) {
    Node* newNode = new Node();
    newNode->data = value;

    if (head == NULL && position == 1) {
        newNode->next = newNode;
        newNode->prev = newNode;
        head = newNode;
        return;
    }

    if (position == 1) {
        Node* tail = head->prev;
        newNode->next = head;
        newNode->prev = tail;
        tail->next = newNode;
        head->prev = newNode;
        head = newNode;
        return;
    }

    Node* temp = head;
    int count = 1;

    while (count < position - 1 && temp->next != head) {
        temp = temp->next;
        count++;
    }

    Node* nextNode = temp->next;
    newNode->next = nextNode;
    newNode->prev = temp;
    temp->next = newNode;
    nextNode->prev = newNode;
}

void display() {
    if (head == NULL) {
        cout << "List is empty." << endl;
        return;
    }

    Node* temp = head;
    cout << "Circular Doubly Linked List: "<<endl;
    do {
        cout << temp->data << " ";
        temp = temp->next;
    } while (temp != head);
    cout << endl;
}

int main() {
    insertAtPosition(60, 1);
    insertAtPosition(70, 2);
    insertAtPosition(80, 1);
    insertAtPosition(90, 3);

    display();  

    return 0;
} 
            ********** TASK 03  **********

#include <iostream>
using namespace std;
struct Node {
    int data;
    Node* next;
    Node* prev;
};
Node* head = NULL;
void insertAtEnd(int value) {
    Node* newNode = new Node();
    newNode->data = value;
    if (head == NULL) {
        newNode->next = newNode;
        newNode->prev = newNode;
        head = newNode;
    } else {
        Node* tail = head->prev;

        newNode->next = head;
        newNode->prev = tail;

        tail->next = newNode;
        head->prev = newNode;
    }
}
void display() {
    if (head == NULL) {
        cout << "List is empty." << endl;
        return;
    }

    Node* temp = head;
    cout << "Circular Doubly Linked List: ";
    do {
        cout << temp->data << " ";
        temp = temp->next;
    } while (temp != head);
    cout << endl;
}
int main() {
    insertAtEnd(60);
    insertAtEnd(70);
    insertAtEnd(80);
    display();  
    return 0;
}
           ############### deletion  ##############
                 ********** TASK 01  **********

#include <iostream>
using namespace std;
struct Node {
    int data;
    Node* next;
    Node* prev;
};

Node* head = NULL;

void insertAtEnd(int value) {
    Node* newNode = new Node();
    newNode->data = value;
    if (head == NULL) {
        newNode->next = newNode;
        newNode->prev = newNode;
        head = newNode;
    } else {
        Node* tail = head->prev;
        newNode->next = head;
        newNode->prev = tail;
        tail->next = newNode;
        head->prev = newNode;
    }
}
void deleteAtStart() {
    if (head == NULL) {
        cout << "List is empty.\n";
        return;
    }

    if (head->next == head) {
        delete head;
        head = NULL;
    } else {
        Node* temp = head;
        head = head->next;
        head->prev = temp->prev;
        temp->prev->next = head;
        delete temp;
    }
}

void display() {
    if (head == NULL) {
        cout << "List is empty.\n";
        return;
    }

    Node* temp = head;
    do {
        cout << temp->data << " ";
        temp = temp->next;
    } while (temp != head);
    cout << endl;
}

int main() {
    insertAtEnd(60);
    insertAtEnd(70);
    insertAtEnd(80);

    cout << "Before deletion: ";
    display();

    deleteAtStart();

    cout << "After deletion: ";
    display();

    return 0;
}
                ********** TASK 02  **********

#include <iostream>
using namespace std;
struct Node {
    int data;
    Node* next;
    Node* prev;
};
Node* head = NULL;
void insertAtEnd(int value) {
    Node* newNode = new Node();
    newNode->data = value;
    if (head == NULL) {
        newNode->next = newNode;
        newNode->prev = newNode;
        head = newNode;
    } else {
        Node* tail = head->prev;
        newNode->next = head;
        newNode->prev = tail;
        tail->next = newNode;
        head->prev = newNode;
    }
}
void deleteAtPosition(int position) {
    if (head == NULL) {
        cout << "List is empty.";
        return;
    }
    Node* temp = head;
    int count = 1;
    while (count < position && temp->next != head) {
        temp = temp->next;
        count++;
    }
    if (count != position) {
        cout << "Position out of range.";
        return;
    }
    if (temp == head && temp->next == head) {
        delete temp;
        head = NULL;
    } else {
        temp->prev->next = temp->next;
        temp->next->prev = temp->prev;

        if (temp == head) {
            head = temp->next;  
        }
        delete temp;
    }
}
void display() {
    if (head == NULL) {
        cout << "List is empty.";
        return;
    }
    Node* temp = head;
    do {
        cout << temp->data << " ";
        temp = temp->next;
    } while (temp != head);
    cout << endl;
}

int main() {
    insertAtEnd(60);
    insertAtEnd(70);
    insertAtEnd(80);
    insertAtEnd(90);

    cout << "Before deletion: ";
    display();

    deleteAtPosition(3);

    cout << "After deletion: ";
    display();

    return 0;
}
                ********** TASK 03  **********

#include <iostream>
using namespace std;
struct Node {
    int data;
    Node* next;
    Node* prev;
};
Node* head = NULL;

void insertAtEnd(int value) {
    Node* newNode = new Node();
    newNode->data = value;
    if (head == NULL) {
        newNode->next = newNode;
        newNode->prev = newNode;
        head = newNode;
    } else {
        Node* tail = head->prev;
        newNode->next = head;
        newNode->prev = tail;
        tail->next = newNode;
        head->prev = newNode;
    }
}
void deleteAtEnd() {
    if (head == NULL) {
        cout << "List is empty.";
        return;
    }
    if (head->next == head) {
        delete head;
        head = NULL;
    } else {
        Node* tail = head->prev;
        Node* newTail = tail->prev;
        newTail->next = head;
        head->prev = newTail;
        delete tail;
    }
}
void display() {
    if (head == NULL) {
        cout << "List is empty.";
        return;
    }

    Node* temp = head;
    do {
        cout << temp->data << " ";
        temp = temp->next;
    } while (temp != head);
    cout << endl;
}

int main() {
    insertAtEnd(60);
    insertAtEnd(70);
    insertAtEnd(80);

    cout << "Before deletion: ";
    display();

    deleteAtEnd();

    cout << "After deletion: ";
    display();

    return 0;
}



         



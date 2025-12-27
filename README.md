1.InItIalIzatIon of malloc() functIon Into zero.
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
int main()
{
int n=5;
int*arr=(int *)malloc(n*sizeof(int));
if(arr==NULL) 
{
printf("Memory allocation failed\n");
return 1;
}
memset(arr,0,n*sizeof(int));
for (int i = 0; i < n; i++) 
{
printf("%d ",arr[i]);
}
free(arr);
printf("program output:success\n");
system("getmac");
return 0;
}
2.checking whether the junk value is initialised by 
a) calloc() function.
#include <stdio.h>
#include <stdlib.h>
int main()
{
 int n = 5;
 int *ptr;
 ptr = (int *)calloc(n, sizeof(int));
if (ptr == NULL)
{
 printf("Memory not allocated\n");
 return 1;
 }
printf("Values after calloc allocation:\n");
for (int i = 0; i < n; i++) 
{
 printf("ptr[%d] = %d\n", i, ptr[i]);
 }
free(ptr);
printf("program output:success\n");
system("getmac");
return 0;
}
B) malloc() function.
#include <stdio.h>
#include <stdlib.h>
int main()
{
int n = 5;
int *ptr;
ptr=(int*)malloc(n*sizeof(int));
if(ptr==NULL)
{
printf("Memory not allocated\n");
return 1;
}
printf("Values after malloc allocation:\n");
3.printing the address of the pointer.
#include <stdio.h>
#include <stdlib.h>
int main() 
{
int a = 10;
int *p = &a;
printf("Value of a = %d\n", a);
printf("Address of a = %p\n", (void *)&a);
printf("Value stored in pointer p (address of a) = %p\n", (void *)p);
printf("Address of pointer p = %p\n", (void *)&p);
printf("program output: success\n");
system("getmac");
return 0;
}
for (int i = 0; i < n; i++)
{
printf("ptr[%d] = %d\n", i, ptr[i]);
}
free(ptr);
printf("program output:success\n");
system("getmac");
return 0;
}
4.selection sort with dynamic memory allocation.
#include <stdio.h>
#include <stdlib.h>
int main()
{
int n, i, j, min, temp;
int *arr;
printf("Enter number of elements: ");
scanf("%d", &n);
arr = (int *)malloc(n * sizeof(int));
if (arr == NULL)
{
printf("Memory allocation failed\n");
return 1;
}
printf("Enter %d elements:\n", n);
for (i = 0; i < n; i++)
{
scanf("%d", &arr[i]);
}
for (i = 0; i < n - 1; i++)
{
min = i;
for (j = i + 1; j < n; j++)
{
if (arr[j] < arr[min])
{
min = j;
}
}
temp = arr[i];
arr[i] = arr[min];
arr[min] = temp;
}
printf("Sorted array:\n");
for (i = 0; i < n; i++)
{
printf("%d ", arr[i]);
}
free(arr);
printf("program output:success\n");
system("getmac");
return 0;
}
5.selection sort without dynamic memory allocation.
#include <stdio.h>
#include <stdlib.h>
int main()
{
int n, i, j, min, temp;
int arr[100];
printf("Enter number of elements: ");
scanf("%d", &n);
printf("Enter %d elements:\n", n);
for (i = 0; i < n; i++)
{
scanf("%d", &arr[i]);
}
for (i = 0; i < n - 1; i++)
{
min = i;
for (j = i + 1; j < n; j++)
{
if (arr[j] < arr[min])
{
min = j;
}
}
temp = arr[i];
arr[i] = arr[min];
arr[min] = temp;
}
printf("Sorted array:\n");
for (i = 0; i < n; i++)
{
printf("%d ", arr[i]);
}
printf("program output:success\n");
system("getmac");
return 0;
}
6. Declaration of two-dimensional array using dynamic memory allocation.
#include <stdio.h>
#include <stdlib.h>
int main()
{
int rows, cols;
int **arr;
printf("Enter number of rows and columns: ");
scanf("%d %d", &rows, &cols);
arr = (int **)malloc(rows * sizeof(int *));
for (int i = 0; i < rows; i++)
{
arr[i] = (int *)malloc(cols * sizeof(int));
}
printf("Enter elements:\n");
for (int i = 0; i < rows; i++)
for (int j = 0; j < cols; j++)
scanf("%d", &arr[i][j]);
printf("2D Array:\n");
for (int i = 0; i < rows; i++)
{
for (int j = 0; j < cols; j++)
printf("%d ", arr[i][j]);
printf("\n");
}
for (int i = 0; i < rows; i++)
free(arr[i]);
free(arr);
printf("program output:success\n");
system("getmac");
return 0;
}
7.Pattern matching.
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
int main()
{
char text[200], pattern[50];
int i, j, found = 0;
printf("Enter the text: ");
fgets(text, sizeof(text), stdin);
text[strcspn(text, "\n")] = 0; 
printf("Enter the pattern: ");
fgets(pattern, sizeof(pattern), stdin);
pattern[strcspn(pattern, "\n")] = 0;
int n = strlen(text);
int m = strlen(pattern);
for (i = 0; i <= n - m; i++) 
{
for (j = 0; j < m; j++)
{
if (text[i + j] != pattern[j])
break;
}
if (j == m)
{
printf("Pattern found at position %d\n", i);
found = 1;
}
}
if (!found)
printf("Pattern not found\n");
printf("program output:success\n");
system("getmac");
return 0;
}
8.self-referential structure.
#include <stdio.h>
#include <stdlib.h>
struct Node
{
 int data;
 struct Node *next; 
};
int main()
{
 struct Node *head = NULL;
 struct Node *second = NULL;
 struct Node *third = NULL;
 head = (struct Node *)malloc(sizeof(struct Node));
 second = (struct Node *)malloc(sizeof(struct Node));
 third = (struct Node *)malloc(sizeof(struct Node));
 head->data = 10;
 head->next = second;
 second->data = 20;
 second->next = third;
 third->data = 30;
 third->next = NULL;
 struct Node *ptr = head;
 printf("Linked List: ");
 while (ptr != NULL)
 {
 printf("%d -> ", ptr->data);
ptr = ptr->next;
 }
 printf("NULL\n");
 free(head);
 free(second);
 free(third);
 printf("program output:success\n");
 system("getmac");
 return 0;
}
9.pre-Increment and post-Increment
#include <stdio.h>
#include <stdlib.h>
int main()
{
 int x = 10;
 printf("Initial value of x = %d\n", x);
 printf("Pre-increment (++x) = %d\n", ++x);
 printf("After pre-increment, x = %d\n", x);
 printf("Post-increment (x++) = %d\n", x++);
 printf("After post-increment, x = %d\n", x);
 printf("program output:success\n");
 system("getmac");
 return 0;
}
10.pre-decrement and post-decrement.
#include <stdio.h>
#include <stdlib.h>
int main()
{
 int x = 10;
 printf("Initial value of x = %d\n", x);
 printf("Pre-decrement (--x) = %d\n", --x);
 printf("After pre-decrement, x = %d\n", x);
 printf("Post-decrement (x--) = %d\n", x--);
 printf("After post-decrement, x = %d\n", x);
 printf("program output:success\n");
 system("getmac");
 return 0;
}
11.regular queues.
#include <stdio.h>
#include <stdlib.h>
#define MAX 5
int queue[MAX];
int front = -1, rear = -1;
void enqueue(int item)
{
 if (rear == MAX - 1)
 {
 printf("Queue Overflow\n");
 return;
 }
 if (front == -1)
 front = 0;
 rear++;
 queue[rear] = item;
 printf("%d inserted\n", item);
}
void dequeue()
{
 if (front == -1 || front > rear)
 {
 printf("Queue Underflow\n");
 return;
 }
 printf("%d deleted\n", queue[front]);
front++;
}
void display()
{
 if (front == -1 || front > rear)
 {
 printf("Queue is empty\n");
 return;
 }
 printf("Queue elements: ");
 for (int i = front; i <= rear; i++)
 printf("%d ", queue[i]);
 printf("\n");
}
int main()
{
 int choice, item;
 while (1)
 {
 printf("\n1.Enqueue\n2.Dequeue\n3.Display\n4.Exit\n");
 printf("Enter choice: ");
 scanf("%d", &choice);
 printf("program output:success\n");
 system("getmac");
 return 0;
 switch (choice)
 {
 case 1:printf("Enter element: ");
 scanf("%d", &item);
 enqueue(item);
 break;
 case 2:
 dequeue();
 break;
 case 3:
 display();
 break;
 case 4:
 return 0;
 default:
 printf("Invalid choice\n");
}
}
}
12.operations of linked lists.
a) traversal
#include <stdio.h>
#include <stdlib.h>
struct Node
{
 int data;
 struct Node *next;
};
int main()
{
 struct Node *head = NULL, *second = NULL, *third = NULL;
 struct Node *temp;
 head = (struct Node *)malloc(sizeof(struct Node));
 second = (struct Node *)malloc(sizeof(struct Node));
 third = (struct Node *)malloc(sizeof(struct Node));
 head->data = 10;
 head->next = second;
 second->data = 20;
 second->next = third;
 third->data = 30;
 third->next = NULL;
 temp = head;
 printf("Linked List elements: ");
 while (temp != NULL)
{
printf("%d ", temp->data);
 temp = temp->next;
 }
 free(head);
 free(second);
 free(third);
 printf("program output:success\n");
 system("getmac");
 return 0;
}
B) Insertion
#include <stdio.h>
#include <stdlib.h>
struct Node
{
 int data;
 struct Node *next;
};
struct Node* insert_begin(struct Node *head, int value)
{
 struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));
 newNode->data = value;
 newNode->next = head;
 return newNode;
}
struct Node* insert_end(struct Node *head, int value)
{
 struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));
 newNode->data = value;
 newNode->next = NULL;
 if (head == NULL)
 return newNode;
 struct Node *temp = head;
 while (temp->next != NULL)
 temp = temp->next;
 temp->next = newNode;
 return head;
}
void display(struct Node *head)
{
 struct Node *temp = head;
 printf("Linked List: ");
 while (temp != NULL)
 {
 printf("%d -> ", temp->data);
 temp = temp->next;
 }
 printf("NULL\n");
}
int main()
{
 struct Node *head = NULL;
 head = insert_begin(head, 10);
 head = insert_begin(head, 5);
 head = insert_end(head, 20);
 head = insert_end(head, 30);
 display(head);
 printf("program output:success\n");
 system("getmac");
 return 0;
}
c)deletion
#include <stdio.h>
#include <stdlib.h>
struct Node
{
 int data;
 struct Node *next;
};
struct Node* insert_end(struct Node *head, int value)
{
 struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));
 newNode->data = value;
 newNode->next = NULL;
 if (head == NULL)
 return newNode;
 struct Node *temp = head;
 while (temp->next != NULL)
 temp = temp->next;
 temp->next = newNode;
 return head;
}
struct Node* delete_begin(struct Node *head)
{
 if (head == NULL)
 {
 printf("List is empty\n");
 return NULL;
 }
 struct Node *temp = head;
 head = head->next;
 printf("Deleted element: %d\n", temp->data);
 free(temp);
 return head;
}
struct Node* delete_end(struct Node *head)
{
if (head == NULL)
 {
 printf("List is empty\n");
 return NULL;
 }
 if (head->next == NULL)
 {
 printf("Deleted element: %d\n", head->data);
 free(head);
 return NULL;
 }
 struct Node *temp = head;
 while (temp->next->next != NULL)
 temp = temp->next;
 printf("Deleted element: %d\n", temp->next->data);
 free(temp->next);
 temp->next = NULL;
 return head;
}
void display(struct Node *head)
{
 struct Node *temp = head;
 printf("Linked List: ");
 while (temp != NULL) {
 printf("%d -> ", temp->data);
 temp = temp->next;
 }
 printf("NULL\n");
}
int main()
{
 struct Node *head = NULL;
 head = insert_end(head, 10);
 head = insert_end(head, 20);
 head = insert_end(head, 30);
 display(head);
 head = delete_begin(head);
 display(head);
 head = delete_end(head);
 display(head);
 printf("program output:success\n");
 system("getmac");
 return 0;
}
13.linked list using stacks.
#include <stdio.h>
#include <stdlib.h>
struct Node
{
 int data;
 struct Node *next;
};
struct Node *top = NULL;
void push(int value) 
{
 struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));
 newNode->data = value;
 newNode->next = top;
 top = newNode;
 printf("%d pushed into stack\n", value);
}
void pop() 
{
 if (top == NULL)
 {
 printf("Stack Underflow\n");
 return;
 }
 struct Node *temp = top;
 printf("%d popped from stack\n", temp->data);
 top = top->next;
free(temp);
}
void display() 
{
 if (top == NULL)
 {
 printf("Stack is empty\n");
 return;
 }
 struct Node *temp = top;
 printf("Stack elements (Top → Bottom): ");
 while (temp != NULL) {
 printf("%d ", temp->data);
 temp = temp->next;
 }
 printf("\n");
}
int main()
{
 push(10);
 push(20);
 push(30);
 display(); 
 pop(); 
 display();
 printf("program output:success\n");
 system("getmac");
return 0;
}
14.linked list using queues.
#include <stdio.h>
#include <stdlib.h>
struct Node
{
 int data;
 struct Node* next;
};
struct Queue 
{
 struct Node *front, *rear;
};
struct Queue* createQueue() 
{
 struct Queue* q = (struct Queue*)malloc(sizeof(struct Queue));
 q->front = q->rear = NULL;
 return q;
}
void enqueue(struct Queue* q, int val)
{
 struct Node* temp = (struct Node*)malloc(sizeof(struct Node));
 temp->data = val; temp->next = NULL;
 if (!q->rear) q->front = q->rear = temp;
 else { q->rear->next = temp; q->rear = temp; }
}
int dequeue(struct Queue* q) 
{
 if (!q->front) return -1;
struct Node* temp = q->front;
 int val = temp->data;
 q->front = q->front->next;
 if (!q->front) q->rear = NULL;
 free(temp);
 return val;
}
void display(struct Queue* q) 
{
 struct Node* temp = q->front;
 while (temp) 
{ 
 printf("%d ", temp->data); temp = temp->next;
}
 printf("\n");
}
int main()
{
 struct Queue* q = createQueue();
 enqueue(q, 10); enqueue(q, 20); enqueue(q, 30);
 display(q);
 printf("Dequeued: %d\n", dequeue(q));
 display(q);
 enqueue(q, 40);
 display(q);
 printf("program output:success\n");
system("getmac");
return 0;
}
15.time taken by arrays and linked lists during 
Insertion and deletion.
#include <stdio.h>
#include <stdlib.h>
#include <time.h>
struct Node 
{
 int data;
 struct Node* next;
};
void insertLinkedList(struct Node** head, int value)
{
 struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
 newNode->data = value;
 newNode->next = *head;
 *head = newNode;
}
void deleteLinkedList(struct Node** head)
{
 if (*head == NULL) return;
 struct Node* temp = *head;
 *head = (*head)->next;
 free(temp);
}
int main()
{
int n = 100000; 
 int *arr = (int*)malloc(n * sizeof(int));
 struct Node* head = NULL;
 clock_t start, end;
 double time_taken;
 start = clock();
 for (int i = 0; i < n; i++) 
 {
 for (int j = i; j > 0; j--)
 arr[j] = arr[j - 1];
 arr[0] = i;
 }
 end = clock();
 time_taken = ((double)(end - start)) / CLOCKS_PER_SEC;
 printf("Array insertion at beginning: %f seconds\n", time_taken);
 start = clock();
 for (int i = 0; i < n; i++)
 {
 for (int j = 0; j < n - i - 1; j++)
 arr[j] = arr[j + 1];
 }
 end = clock();
 time_taken = ((double)(end - start)) / CLOCKS_PER_SEC;
 printf("Array deletion from beginning: %f seconds\n", time_taken);
 start = clock();
 for (int i = 0; i < n; i++)
 insertLinkedList(&head, i);
 end = clock();
 time_taken = ((double)(end - start)) / CLOCKS_PER_SEC;
printf("Linked list insertion at beginning: %f seconds\n", time_taken);
 start = clock();
 for (int i = 0; i < n; i++)
 deleteLinkedList(&head);
 end = clock();
 time_taken = ((double)(end - start)) / CLOCKS_PER_SEC;
 printf("Linked list deletion from beginning: %f seconds\n", time_taken);
 free(arr);
 printf("program output:success\n");
 system("getmac");
 return 0;
}
}
16.sparse matrIx.
#include <stdio.h>
#include <stdlib.h>
struct Element
{
 int row;
 int col;
 int value;
};
int main()
{
 int m, n, i, j, k = 0;
 printf("Enter number of rows and columns: ");
 scanf("%d %d", &m, &n);
 int matrix[m][n];
 printf("Enter the matrix elements:\n");
 for (i = 0; i < m; i++)
 for (j = 0; j < n; j++)
 scanf("%d", &matrix[i][j]);
 int count = 0;
 for (i = 0; i < m; i++)
 for (j = 0; j < n; j++)
 if (matrix[i][j] != 0) count++;
 struct Element* sparse = (struct Element*)malloc(count * sizeof(struct Element));
 for (i = 0; i < m; i++) {
 for (j = 0; j < n; j++) {
 if (matrix[i][j] != 0) {
 sparse[k].row = i;
sparse[k].col = j;
 sparse[k].value = matrix[i][j];
 k++;
 }
 }
 }
 printf("\nSparse Matrix Representation (row col value):\n");
 for (i = 0; i < count; i++)
 printf("%d %d %d\n", sparse[i].row, sparse[i].col, sparse[i].value);
 free(sparse);
 printf("program output:success\n");
 system("getmac");
 return 0;
}
17.polynomial representation.
#include <stdio.h>
#include <stdlib.h>
struct Term {
int coeff;
int exp;
struct Term* next;
};
struct Term* createTerm(int coeff, int exp) {
struct Term* newTerm = (struct Term*)malloc(sizeof(struct Term));
newTerm->coeff = coeff;
newTerm->exp = exp;
newTerm->next = NULL;
return newTerm;
}
void insertTerm(struct Term** head, int coeff, int exp) {
struct Term* newTerm = createTerm(coeff, exp);
if(*head == NULL) {
*head = newTerm;
return;
}
struct Term* temp = *head;
while(temp->next != NULL)
temp = temp->next;
temp->next = newTerm;
}
void displayPolynomial(struct Term* head) {
struct Term* temp = head;
while(temp != NULL) {
printf("%dx^%d", temp->coeff, temp->exp);
if(temp->next != NULL)
printf(" + ");
temp = temp->next;
}
printf("\n");
}
int main()
{
struct Term* poly = NULL;
int n, coeff, exp;
printf("Enter number of terms in the polynomial: ");
scanf("%d", &n);
for(int i = 0; i < n; i++) {
printf("Enter coefficient and exponent of term %d: ", i+1);
scanf("%d %d", &coeff, &exp);
insertTerm(&poly, coeff, exp);
}
printf("\nPolynomial: ");
displayPolynomial(poly);
printf("program output:success\n");
system("getmac");
return 0;
}
18.creatIon of BInarY tree.
#include <stdio.h>
#include <stdlib.h>
struct Node
{
int data;
struct Node* left;
struct Node* right;
};
struct Node* createNode(int value) {
struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
newNode->data = value;
newNode->left = NULL;
newNode->right = NULL;
return newNode;
}
void displayTree(struct Node* root) {
if(root != NULL) {
displayTree(root->left);
printf("%d ", root->data);
displayTree(root->right);
}
}
int main() {
struct Node* root = createNode(1);
root->left = createNode(2);
root->right = createNode(3);
root->left->left = createNode(4);
root->left->right = createNode(5);
printf("Binary Tree (Inorder Traversal): ");
displayTree(root);
printf("\n");
printf("program output:success\n");
system("getmac");
return 0;
}
19.Binary tree using array.
#include <stdio.h>
#include <stdlib.h>
int main() {
int n;
printf("Enter number of nodes in the binary tree: ");
scanf("%d", &n);
int tree[n];
printf("Enter %d elements:\n", n);
for(int i = 0; i < n; i++) {
scanf("%d", &tree[i]);
}
printf("\nBinary Tree (Level Order): ");
for(int i = 0; i < n; i++) {
printf("%d ", tree[i]);
}
printf("\n");
printf("\nParent -> Left Child, Right Child\n");
for(int i = 0; i < n; i++) {
int left = 2*i + 1;
int right = 2*i + 2;
printf("%d -> ", tree[i]);
if(left < n) printf("%d ", tree[left]);
else printf("NULL ");
if(right < n) printf("%d", tree[right]);
else printf("NULL");
printf("\n");
}
printf("program output:success\n");
system("getmac");
return 0;
}
20.Binary tree using queues.
#include <stdio.h>
#include <stdlib.h>
#define MAX 100
struct Node {
int data;
struct Node* left;
struct Node* right;
};
struct Node* queue[MAX];
int front = 0, rear = 0;
void enqueue(struct Node* node) {
queue[rear++] = node;
}
struct Node* dequeue() {
return queue[front++];
}
int isEmpty() {
return front == rear;
}
struct Node* createNode(int value) {
struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
newNode->data = value;
newNode->left = newNode->right = NULL;
return newNode;
}
void inorder(struct Node* root) {
if(root != NULL) {
inorder(root->left);
printf("%d ", root->data);
inorder(root->right);
}
}
int main()
{
int value;
printf("Enter root node value: ");
scanf("%d", &value);
struct Node* root = createNode(value);
enqueue(root);
while(!isEmpty()) {
struct Node* temp = dequeue();
int leftVal, rightVal;
printf("Enter left child of %d (-1 for no child): ", temp->data);
scanf("%d", &leftVal);
if(leftVal != -1) {
temp->left = createNode(leftVal);
enqueue(temp->left);
}
printf("Enter right child of %d (-1 for no child): ", temp->data);
scanf("%d", &rightVal);
if(rightVal != -1) {
temp->right = createNode(rightVal);
enqueue(temp->right);
}
}
printf("\nBinary Tree (Inorder Traversal): ");
inorder(root);
printf("\n");
printf("program output:success\n");
system("getmac");
return 0;
}
21.Insertion of nodes
#include <stdio.h>
#include <stdlib.h>
struct Node
{
 int data;
 struct Node *left, *right;
};
struct Node* createNode(int value) 
{
 struct Node* node = (struct Node*)malloc(sizeof(struct Node));
 node->data = value;
 node->left = node->right = NULL;
 return node;
}
struct Node* insert(struct Node* root, int value) {
 if (root == NULL)
 return createNode(value);
 if (value < root->data)
 root->left = insert(root->left, value);
 else
 root->right = insert(root->right, value);
 return root;
}
void inorder(struct Node* root)
{
if (root == NULL) return;
 inorder(root->left);
 printf("%d ", root->data);
 inorder(root->right);
}
int main()
{
 struct Node* root = NULL;
 root = insert(root, 10);
 insert(root, 5);
 insert(root, 20);
 insert(root, 3);
 insert(root, 7);
 printf("Inorder traversal: ");
 inorder(root);
 printf("program output:success\n");
 system("getmac");
 return 0;
}
22.deletions of nodes.
#include <stdio.h>
#include <stdlib.h>
struct Node 
{
 int data;
 struct Node *left, *right;
};
struct Node* newNode(int val)
{
 struct Node* n = (struct Node*)malloc(sizeof(struct Node));
 n->data = val;
 n->left = n->right = NULL;
 return n;
}
struct Node* insert(struct Node* root, int val)
{
 if (root == NULL) return newNode(val);
 if (val < root->data)
 root->left = insert(root->left, val);
 else
 root->right = insert(root->right, val);
 return root;
}
struct Node* minValue(struct Node* root)
{
 while (root->left)
root = root->left;
 return root;
}
struct Node* delete(struct Node* root, int key) 
{
 if (root == NULL) return root;
 if (key < root->data)
 root->left = delete(root->left, key);
 else if (key > root->data)
 root->right = delete(root->right, key);
 else {
 if (root->left == NULL)
 return root->right;
 else if (root->right == NULL)
 return root->left;
 struct Node* temp = minValue(root->right);
 root->data = temp->data;
 root->right = delete(root->right, temp->data);
 }
 return root;
}
void inorder(struct Node* root) 
{
 if (root)
 {
 inorder(root->left);
 printf("%d ", root->data);
 inorder(root->right);
}
}
int main() 
{
 struct Node* root = NULL;
 root = insert(root, 40);
 insert(root, 20);
 insert(root, 60);
 insert(root, 10);
 insert(root, 30);
 printf("Before deletion: ");
 inorder(root);
 root = delete(root, 20);
 printf("\nAfter deletion: ");
 inorder(root);
 printf("program output:success\n");
 system("getmac");
 return 0;
}
23. depth search tree.
#include <stdio.h>
#include <stdlib.h>
int n;
int adj[10][10];
int visited[10];
void DFS(int v)
{
 int i;
 printf("%d ", v);
 visited[v] = 1;
 for (i = 0; i < n; i++)
 {
 if (adj[v][i] == 1 && visited[i] == 0)
 DFS(i);
 }
}
int main()
{
 int i, j, start;
 printf("Enter number of vertices: ");
 scanf("%d", &n);
 printf("Enter adjacency matrix:\n");
 for (i = 0; i < n; i++)
 for (j = 0; j < n; j++)
 scanf("%d", &adj[i][j]);
 printf("Enter starting vertex: ");
 scanf("%d", &start);
 DFS(start);
 printf("program output:success\n");
 system("getmac");
 return 0;
}
24.Breadth search tree
#include <stdio.h>
#include <stdlib.h>
int n;
int adj[10][10];
int visited[10];
int queue[10];
int front = 0, rear = -1;
void BFS(int start)
{
 int i, v;
 queue[++rear] = start;
 visited[start] = 1;
 while (front <= rear) 
 {
 v = queue[front++];
 printf("%d ", v);
 for (i = 0; i < n; i++)
 {
 if (adj[v][i] == 1 && visited[i] == 0) 
 {
 queue[++rear] = i;
 visited[i] = 1;
 }
 }
 }
}
int main() 
{
 int i, j, start;
 printf("Enter number of vertices: ");
 scanf("%d", &n);
 printf("Enter adjacency matrix:\n");
 for (i = 0; i < n; i++)
 for (j = 0; j < n; j++)
 scanf("%d", &adj[i][j]);
 printf("Enter starting vertex: ");
 scanf("%d", &start);
 BFS(start);
 printf("program output:success\n");
 system("getmac");
 return 0;
}
25. level order.
#include <stdio.h>
#include <stdlib.h>
struct Node
{
 int data;
 struct Node *left, *right;
};
struct Node* newNode(int val) 
{
 struct Node* n = (struct Node*)malloc(sizeof(struct Node));
 n->data = val;
 n->left = n->right = NULL;
 return n;
}
struct Node* queue[20];
int front = 0, rear = -1;
void enqueue(struct Node* node)
{
 queue[++rear] = node;
}
struct Node* dequeue()
{
 return queue[front++];
}
void levelOrder(struct Node* root) 
{
 if (root == NULL) return;
 enqueue(root);
while (front <= rear) 
 {
 struct Node* temp = dequeue();
 printf("%d ", temp->data);
 if (temp->left)
 enqueue(temp->left);
 if (temp->right)
 enqueue(temp->right);
 }
}
int main()
{
 struct Node* root = newNode(1);
 root->left = newNode(2);
 root->right = newNode(3);
 root->left->left = newNode(4);
 root->left->right = newNode(5);
 printf("Level Order Traversal: ");
 levelOrder(root);
 printf("program output:success\n");
 system("getmac");
 return 0;
}
26.dfs and Bfs using adjacencY list.
#include <stdio.h>
#include <stdlib.h>
struct Node 
{
 int vertex;
 struct Node* next;
};
struct Node* adj[10];
int visited[10];
int n;
struct Node* createNode(int v) 
{
 struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
 newNode->vertex = v;
 newNode->next = NULL;
 return newNode;
}
void addEdge(int src, int dest)
{
 struct Node* newNode = createNode(dest);
 newNode->next = adj[src];
 adj[src] = newNode;
 newNode = createNode(src);
 newNode->next = adj[dest];
 adj[dest] = newNode;
}
void DFS(int v)
{
 struct Node* temp = adj[v];
 printf("%d ", v);
 visited[v] = 1;
 while (temp != NULL) 
 {
 if (!visited[temp->vertex])
 DFS(temp->vertex);
 temp = temp->next;
 }
}
void BFS(int start)
{
 int queue[10], front = 0, rear = -1;
 struct Node* temp;
 visited[start] = 1;
 queue[++rear] = start;
 while (front <= rear)
 {
 int v = queue[front++];
 printf("%d ", v);
 temp = adj[v];
 while (temp != NULL)
 {
 if (!visited[temp->vertex]) 
 {
 visited[temp->vertex] = 1;
queue[++rear] = temp->vertex;
 }
 temp = temp->next;
 }
 }
}
int main()
{
 int i, edges, u, v, start;
 printf("Enter number of vertices: ");
 scanf("%d", &n);
 for (i = 0; i < n; i++)
 adj[i] = NULL;
 printf("Enter number of edges: ");
 scanf("%d", &edges);
 for (i = 0; i < edges; i++) 
 {
 scanf("%d %d", &u, &v);
 addEdge(u, v);
 }
 printf("Enter starting vertex: ");
 scanf("%d", &start);
 for (i = 0; i < n; i++)
 visited[i] = 0;
 printf("DFS: ");
 DFS(start);
 for (i = 0; i < n; i++)
 visited[i] = 0;
 printf("\nBFS: ");
BFS(start);
 printf("program output:success\n");
 system("getmac");
 return 0;
}
27.circular linked list operations.
#include <stdio.h>
#include <stdlib.h>
struct Node 
{
 int data;
 struct Node* next;
};
struct Node* head = NULL;
void insert(int val)
{
 struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
 newNode->data = val;
 if (head == NULL) 
 {
 head = newNode;
 newNode->next = head;
 return;
 }
 struct Node* temp = head;
 while (temp->next != head)
 temp = temp->next;
 temp->next = newNode;
 newNode->next = head;
}
void deleteNode(int key) 
{
 struct Node *temp = head, *prev = NULL;
 if (head == NULL) return;
if (head->data == key)
 {
 while (temp->next != head)
 temp = temp->next;
 if (temp == head) 
 {
 free(head);
 head = NULL;
 }
 else 
 {
 temp->next = head->next;
 free(head);
 head = temp->next;
 }
 return;
 }
 prev = head;
 temp = head->next;
 while (temp != head && temp->data != key)
 {
 prev = temp;
 temp = temp->next;
 }
 if (temp->data == key) 
 {
 prev->next = temp->next;
 free(temp);
 }
}
void display() {
 if (head == NULL) return;
 struct Node* temp = head;
 do {
 printf("%d ", temp->data);
 temp = temp->next;
 }
 while (temp != head);
}
int main() {
 insert(10);
 insert(20);
 insert(30);
 printf("Circular List: ");
 display();
 deleteNode(20);
 printf("\nAfter deletion: ");
 display();
 printf("program output:success\n");
 system("getmac");
 return 0;
}
28.comparsIon of two strIngs usIng BuIlt-In functIons.
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
int main()
{
 char str1[50], str2[50];
 printf("Enter first string: ");
 scanf("%s", str1);
 printf("Enter second string: ");
 scanf("%s", str2);
 if (strcmp(str1, str2) == 0)
 printf("Strings are equal");
 else
 printf("Strings are not equal");
printf("program output:success\n");
 system("getmac");
return 0;
}
29. linked list Insertion In the middle and 
 deletion in the middle.
#include <stdio.h>
#include <stdlib.h>
struct Node 
{
 int data;
 struct Node* next;
};
struct Node* insertEnd(struct Node* head, int val)
{
 struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
 newNode->data = val;
 newNode->next = NULL;
 if (head == NULL) return newNode;
 struct Node* temp = head;
 while (temp->next)
 temp = temp->next;
 temp->next = newNode;
 return head;
}
struct Node* insertMiddle(struct Node* head, int val) 
{
 struct Node *slow = head, *fast = head;
 struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
 newNode->data = val;
if (head == NULL)
 {
 newNode->next = NULL;
 return newNode;
 }
 while (fast && fast->next)
 {
 fast = fast->next->next;
 slow = slow->next;
 }
 newNode->next = slow->next;
 slow->next = newNode;
 return head;
}
struct Node* deleteMiddle(struct Node* head) 
{
 struct Node *slow = head, *fast = head, *prev = NULL;
 if (head == NULL || head->next == NULL)
 return NULL;
 while (fast && fast->next) 
 {
 fast = fast->next->next;
 prev = slow;
 slow = slow->next;
 }
 prev->next = slow->next;
 free(slow);
 return head;
}
void display(struct Node* head) 
{
 while (head)
 {
 printf("%d -> ", head->data);
 head = head->next;
 }
 printf("NULL\n");
}
int main() 
{
 struct Node* head = NULL;
 head = insertEnd(head, 10);
 head = insertEnd(head, 20);
 head = insertEnd(head, 30);
 head = insertEnd(head, 40);
 printf("Original list: ");
 display(head);
 head = insertMiddle(head, 25);
 printf("After insertion at middle: ");
 display(head);
 head = deleteMiddle(head);
 printf("After deletion at middle: ");
 display(head);
 printf("program output:success\n");
 system("getmac");
 return 0;
}
30.traversal BInarY tree.
#include <stdio.h>
#include <stdlib.h>
struct Node
{
 int data;
 struct Node *left, *right;
};
struct Node* newNode(int val)
{
 struct Node* node = (struct Node*)malloc(sizeof(struct Node));
 node->data = val;
 node->left = node->right = NULL;
 return node;
}
void inorder(struct Node* root)
{
 if (root == NULL) return;
 inorder(root->left);
 printf("%d ", root->data);
 inorder(root->right);
}
void preorder(struct Node* root)
{
 if (root == NULL) return;
 printf("%d ", root->data);
 preorder(root->left);
 preorder(root->right);
}
void postorder(struct Node* root)
{
 if (root == NULL) return;
 postorder(root->left);
 postorder(root->right);
 printf("%d ", root->data);
}
int main()
{
 struct Node* root = newNode(1);
 root->left = newNode(2);
 root->right = newNode(3);
 root->left->left = newNode(4);
 root->left->right = newNode(5);
 printf("Inorder Traversal: ");
 inorder(root);
 printf("\nPreorder Traversal: ");
 preorder(root);
 printf("\nPostorder Traversal: ");
 postorder(root);
 printf("program output:success\n");
 system("getmac");
 return 0;
}
31. sparse matrix using linked lists.
#include <stdio.h>
#include <stdlib.h>
struct Node 
{
 int row, col, value;
 struct Node* next;
};
struct Node* head = NULL;
void insert(int r, int c, int val)
{
 struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
 newNode->row = r;
 newNode->col = c;
 newNode->value = val;
 newNode->next = NULL;
 if (head == NULL) 
 {
 head = newNode;
 return;
 }
 struct Node* temp = head;
 while (temp->next != NULL)
 temp = temp->next;
 temp->next = newNode;
}
void display()
{
 struct Node* temp = head;
 printf("Row Col Value\n");
 while (temp != NULL) 
 {
 printf("%d %d %d\n", temp->row, temp->col, temp->value);
 temp = temp->next;
 }
}
int main() 
{
 int m, n, i, j, val;
 printf("Enter rows and columns: ");
 scanf("%d %d", &m, &n);
 printf("Enter matrix elements:\n");
 for (i = 0; i < m; i++) {
 for (j = 0; j < n; j++) {
 scanf("%d", &val);
 if (val != 0)
 insert(i, j, val);
 }
 }
 printf("\nSparse Matrix (Linked List Representation):\n");
 display();
 printf("program output:success\n");
 system("getmac");
 return 0;
}
32. check for modulo division, queue full and queue 
empty for circular queues.
#include <stdio.h>
#include <stdlib.h>
#define SIZE 5
int queue[SIZE];
int front = -1, rear = -1;
int isFull()
{
 return ((rear + 1) % SIZE == front);
}
int isEmpty()
{
 return (front == -1);
}
void enqueue(int value)
{
 if (isFull())
 {
 printf("Queue is Full\n");
 return;
 }
 if (front == -1)
 front = 0;
 rear = (rear + 1) % SIZE;
 queue[rear] = value;
 printf("Inserted %d\n", value);
}
void dequeue()
{
if (isEmpty())
 {
 printf("Queue is Empty\n");
 return;
 }
 printf("Deleted %d\n", queue[front]);
 if (front == rear)
 front = rear = -1;
 else
 front = (front + 1) % SIZE;
}
void display()
{
 int i;
 if (isEmpty())
 {
 printf("Queue is Empty\n");
 return;
 }
 printf("Queue elements: ");
 i = front;
 while (i != rear)
 {
 printf("%d ", queue[i]);
 i = (i + 1) % SIZE;
 }
 printf("%d\n", queue[i]);
}
int main()
{
 enqueue(10);
 enqueue(20);
 enqueue(30);
 enqueue(40);
 enqueue(50);
 display();
 dequeue();
 dequeue();
 enqueue(60);
 enqueue(70);
 display();
printf("program output:success\n");
system("getmac");
return 0;
}

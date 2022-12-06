1.MUL:
#include <stdio.h>
int main()
{
   int x, y;
   int product = 0;
   printf("Enter two numbers:\n");
   scanf("%d%d", &x, &y);
   while(y != 0)
   {
      product += x;
      y--;
   }
   printf("\nProuduct = %d\n", product);
   return 0;
}

2. REC MUL
       #include <stdio.h>
#include <stdlib.h>
int product(int,int); 
int main()
{
    int num1,num2,result; 
    printf("Enter two number to find their product\n");
    scanf("%d %d",&num1,&num2);  
    result=product(num1,num2);
    printf("Product of %d and %d is %d\n",num1,num2,result);
}
int product(int a, int b)  
{
    if(a<b)
    {
        return product(b,a);
    }
    else if(b!=0)
	{
            return (a+product(a,b-1));

    }
    else{
        return 0;
    }
}
3.TOWERS OF HANOI
#include<stdio.h>
#include<stdlib.h>
void main()
{
	int n_disks;
	printf("enter the no.of disks:");
	scanf("%d",&n_disks);
	towers_hanoi(n_disks, 'A','C','B');
}
void towers_hanoi(int n_disks,char source,char dest,char aux)
{
	if(n_disks==1)
	{
		printf("move disk %d from %c to %c\n",n_disks,source,dest);
		return;
	}
 
    towers_hanoi(n_disks-1,source,aux,dest);
    printf("move disk %d from %c to %c\n",n_disks,source,dest);
    towers_hanoi(n_disks-1,aux,dest,source);
}
4.ACKKERMAN
#include<stdio.h>
int acker(int , int );
void main()
{
    int m,n,res=0;
    printf("enter the value of m and n:",m,n);
    scanf("%d%d",&m,&n);
    res=acker(m,n);
    printf("result: %d",res);
    }
	int acker(int m, int n)
{
    if (m == 0)
	{
        return n + 1;
    }
    else if((m > 0) && (n == 0))
	{
        return acker(m - 1, 1);
    }
    else if((m > 0) && (n > 0))
	{
        return acker(m - 1, acker(m, n - 1));
    }
}


5.BINARY TO DEC
#include<stdio.h>
int BinaryToDecimal(int n)
{
    if(n==0)
        return 0;
    else
        return (n% 10 + 2* BinaryToDecimal(n / 10));
}
int main()
{
    int n;
    printf("Enter the Binary Value:");
    scanf("%d",&n);
    printf("Decimal Value of Binary number is: %d",BinaryToDecimal(n));
}
6.DECTOBIN
#include <stdio.h>
int find(int n)
{
	if (n == 0)
		return 0;
	else
		return (n % 2 + 10 *find(n / 2));
}
int main()
{
	int n;
    printf("Enter the Decimal Value:");
    scanf("%d",&n);
    printf("Binary Value of Deimal number is: %d",find(n));
}

7.GCD
#include<stdio.h>
int gcd(int x,int y)
{
	int r=0,a,b;
	a=(x>y)?x:y;
	b=(x<y)?x:y;
	r=b;
	while(a%b!=0)
	{
		r=a%b;
		b=r;
		a=b;
	}
	return r;
	}
	int main()
	{
		int x,y,result;
		printf("enter 2 numbers:");
		scanf("%d%d",&x,&y);
		result=gcd(x,y);
		printf("gcd is %d",result);
	}



8.PRIME OR NOT
#include<stdio.h>
int main()
{
	int n,i,flag=0;
	printf("enter the number:");
	scanf("%d",&n);
	if(n==0 || n==1)
	{
		flag=1;
	}
	for(i=2;i<n/2;i++)
	{
		if(n%i==0)
		{
			flag=1;
			break;
		}
		else
		{
			flag=0;
		}
	}
	if(flag==1)
	printf("non-prime");
	else
	printf("prime");
}



9.PRIME FACTORS
#include<stdio.h>
int main()
{
	int i,j,n,isprime;
	printf("enter a num to print PF::");
	scanf("%d",&n);
	printf("all prime factors of %d are:\n",n);
	for(i=2;i<=n;i++)
	{
		if(n%i==0)
		{
			isprime=1;
			for(j=2;j<=i/2;j++)
			{
			if(i%j==0)
			{
			isprime=0;
			break;	
			}
		}
		if(isprime==1)
		printf("%d ",i);
	}
}
}

10.BINOMIAL COEFFICIENT

#include<stdio.h>
int main()
{
	int n,k;
	printf("enter n and k values::");
	scanf("%d %d",&n,&k);
	printf("Value of c(%d, %d) is %d ", n, k,bincoef(n, k));
	return 0;
}
int bincoef(int n,int k)
{
	   if(k>n)
	   return 0;
	   if(k==0||k==n)
	   return 1;
	   return bincoef(n-1,k-1)+bincoef(n-1,k);
}
11.NUMBER PATTERN
#include<stdio.h>
#include<conio.h>
int main()
{
	int n,i,j;
	printf("enter the no of rows:");
	scanf("%d",&n);
	 for(i=1;i<=n;i++)  
    {  
        for(j=1;j<=i;j++)  
        {  
            printf("%d",i);  
        }  
        printf("\n");  
    }  
      
    return 0;  
}  
12.PALINDROME PYRAMID

13.HALLOW SQUARE PATTERN
#include<stdio.h>
#include<conio.h>
int main()
{
	int i,j,n,m;
	printf("enter n,m");
	scanf("%d%d",&n,&m);
	for(i=1;i<=n;i++){
		for(j=1;j<=m;j++){
		if(i==1||i==n||j==1||j==m)
			printf("*");
			else
			printf(" ");
		}
		
	printf("\n");}
	
	
}
14.SOLID SQUARE PATTERN
#include <stdio.h>  
 int main()  
{  
    int n,i,j;  
    printf("Enter the number of rows");  
    scanf("%d",&n);  
    for(i=0;i<n;i++)  
    {  
        for(j=0;j<n;j++)  
        {  
            printf("*");  
        }  
        printf("\n");  
    }   
    return 0;  
}  
15.2 STACKS IN SINGLE ARRAY
#include <stdio.h>  
#define SIZE 10  
 int array[SIZE];  // declaration of array type variable.  
int top1 = -1;  
int top2 = SIZE;  
   
//Function to push data into stack1  
void push1 (int data)  
{  
// checking the overflow condition  
  if (top1 < top2 - 1)  
  {  
      top1++;  
    array[top1] = data;  
  }  
  else  
  {  
    printf ("Stack is full");  
  }  
}  
// Function to push data into stack2  
void push2 (int data)  
{  
// checking overflow condition    
if (top1 < top2 - 1)  
  {  
    top2--;  
    array[top2] = data;   
  }  
  else  
  {  
    printf ("Stack is full..\n");  
  }  
}  
   
//Function to pop data from the Stack1  
void pop1 ()  
{  
// Checking the underflow condition   
 if (top1 >= 0)  
  {  
    int popped_element = array[top1];  
    top1--;  
     
    printf ("%d is being popped from Stack 1\n", popped_element);  
  }  
  else  
  {  
    printf ("Stack is Empty \n");  
  }  
}  
// Function to remove the element from the Stack2  
void pop2 ()  
{  
// Checking underflow condition    
if (top2 < SIZE)  
  {  
      int popped_element = array[top2];  
    top2--;  
     
    printf ("%d is being popped from Stack 1\n", popped_element);  
  }  
  else  
  {  
    printf ("Stack is Empty!\n");  
  }  
}  
   
//Functions to Print the values of Stack1  
void display_stack1 ()  
{  
  int i;  
  for (i = top1; i >= 0; --i)  
  {  
    printf ("%d ", array[i]);  
  }  
  printf ("\n");  
}  
// Function to print the values of Stack2  
void display_stack2 ()  
{  
  int i;  
  for (i = top2; i < SIZE; ++i)  
  {  
    printf ("%d ", array[i]);  
  }  
  printf ("\n");  
}  
   
int main()  
{  
  int ar[SIZE];  
  int i;  
  int num_of_ele;  
   
  printf ("We can push a total of 10 values\n");  
   
  //Number of elements pushed in stack 1 is 10  
  //Number of elements pushed in stack 2 is 10  
   
// loop to insert the elements into Stack1    
for (i = 1; i <= 5; ++i)  
  {  
    push1(i);  
    printf ("Value Pushed in Stack 1 is %d\n", i);  
  }  
// loop to insert the elements into Stack2.    
for (i = 6; i <= 10; ++i)  
  {  
    push2(i);  
    printf ("Value Pushed in Stack 2 is %d\n", i);  
  }  
   
  //Print Both Stacks  
  display_stack1 ();  
 display_stack2 ();  
   
  //Pushing on Stack Full  
  printf ("Pushing Value in Stack 1 is %d\n", 6);  
  push1 (6);  
   
  //Popping All Elements from Stack 1  
  num_of_ele = top1 + 1;  
  while (num_of_ele)  
  {  
    pop1 ();  
    --num_of_ele;  
  }  
   
  // Trying to Pop the element From the Empty Stack  
  pop1 ();  
   
  return 0;  
}
16.INFIX TO POSTFIX
#include<stdio.h>
#include<ctype.h>
char stack[100]; 
int top = -1;
void push(char x)
{
    stack[++top] = x;
}

char pop()
{
    if(top == -1)
        return -1;
    else
        return stack[top--];
}

int priority(char x)
{
    if(x == '(')
        return 0;
    if(x == '+' || x == '-')
        return 1;
    if(x == '*' || x == '/')
        return 2;
    return 0;
}

int main()
{
    char exp[100];
    char *e, x;
    printf("Enter the expression : ");
    scanf("%s",exp);
    printf("\n");
    e = exp;
    
    while(*e != '\0')
    {
        if(isalnum(*e))
            printf("%c ",*e);
        else if(*e == '(')
            push(*e);
        else if(*e == ')')
        {
            while((x = pop()) != '(')
                printf("%c ", x);
        }
        else
        {
            while(priority(stack[top]) >= priority(*e))
                printf("%c ",pop());
            push(*e);
        }
        e++;
    }
    
    while(top != -1)
    {
        printf("%c ",pop());
    }return 0;
}
17.INFIX TO PREFIX
#include<stdio.h>
#define max 100
#include<string.h>
#include<ctype.h>
int top=-1, a[max];
void push(char x)
{
    a[++top]=x;
}
char pop()
{ if(top==-1)
return -1;
else
return a[top--];
}

int prcd(char c)
{   if(c==')')
    return 0;
    else if(c=='+'||c=='-')
    return 1;
    else if(c=='*'||c=='/')
    return 2;
}
void infixtoprefix(char infix[max],char prefix[max])
{
    char temp,x;
    int i=0,j=0;
    strrev(infix);
    while(infix[i]!='\0')
    {
        temp=infix[i];
       if(isalnum(temp))
        {
            prefix[j++]=temp;
        }
        else if(temp==')')
         push(temp);
        else if(temp=='(')
            {
         while((x=pop())!=')')
         {
          prefix[j++]=x;
           }
          }
        else
        {  while(prcd(a[top])>=prcd(temp))
            {prefix[j++]=pop();}
                push(temp);
        }
        i++;
    }
    while(top!= -1)
    prefix[j++]=pop();
    prefix[j]='\0';
    strrev(prefix);
}
main()
{
    char infix[max],prefix[max];
    printf("Enter the infix expression\n");
    gets(infix);
    printf("The infix expression is %s\n",infix);
    infixtoprefix(infix, prefix);
    printf("The prefix expression is %s\n",prefix);
}
18.QUEUE USING 2 STACKS
#include<stdio.h>  
#define N 5  
int stack1[5], stack2[5]; 
int top1=-1, top2=-1;   
int count=0,i;  
void push1(int data)  
{   
 if(top1==N-1)  
{  
   printf("\n Stack is overflow...");  
}  
else  
{  
   top1++;   
   stack1[top1]=data;  
}  
}  
int pop1()  
{     
if(top1==-1)  
{  
   printf("\nStack is empty..");  
}  
else  
{  
   int a=stack1[top1];    
   top1--;  
   return a;   
}  
}   
void push2(int x)  
{    
if(top2==N-1)  
{  
   printf("\nStack is full..");  
}  
else  
{  
    top2++;   
    stack2[top2]=x;
}  
}   
int pop2()  
{  
   int element = stack2[top2];  
   top2--;
   return element;  
}   
void enqueue(int x)  
{  
    push1(x);  
    count++;  
}  
void dequeue()  
{  
   if((top1==-1) && (top2==-1))  
{  
   printf("\nQueue is empty");  
}  
else  
{  
  for(i=0;i<count;i++)  
  {  
     int element = pop1();  
     push2(element);  
  }  
int b= pop2();  
printf("\nThe dequeued element is %d", b);  
printf("\n");  
count--;  
for(i=0;i<count;i++)  
{  
   int a = pop2();  
   push1(a);   
}  
}}   
void display()  
{  
   for(i=0;i<=top1;i++)  
  {  
     printf("%d ", stack1[i]);  
  }  
}  
int main()  
{  
   enqueue(10);  
   enqueue(20);  
   enqueue(30);  
   dequeue();  
   enqueue(40);  
   display();  
}  
19. REVERSE OF A LL
#include<stdio.h>
#include<stdlib.h>
struct node
{
	int data;
	struct node *next;
};
void display(struct node *head)
{
	if(head == NULL)return;
	display(head->next);
	printf("%d ",head->data);
}
int main()
{
	struct node *head, *prev,*p;
	int n,i;
	printf("Enter size of linked list: ");
	scanf("%d",&n);
	head = NULL;
	for(i=0;i<n;i++)
	{
		p = (node *) malloc(sizeof(struct node));
		printf("Enter data: ");
		scanf("%d",&p->data);
		p->next = NULL;
		if(head==NULL)head=p;
		else prev->next=p;
		prev=p;
		
	}
display(head);
}
20.BINARY NO REPRESENTATION USING LL
from collections import deque
def generate(n):
    q = deque()
    q.append(1)
    for i in range(n):
        front = str(q.popleft())
        print(front)
        q.append(front+'0')
        q.append(front+'1')
n = int(input("Enter n : "))
generate(n)

21.SWAPPING OF NODES OF LL WITHOUT SWAPPING DATA
#include <stdio.h>
#include <stdlib.h>
struct Node {
	int data;
	struct Node* next;
};
void swapNodes( int x, int y,struct Node** head_ref)
{
	if (x == y)
		return;
	struct Node *prevX = NULL, *currX = *head_ref;
	while (currX && currX->data != x) {
		prevX = currX;
		currX = currX->next;
	}
	struct Node *prevY = NULL, *currY = *head_ref;
	while (currY && currY->data != y) {
		prevY = currY;
		currY = currY->next;
	}
	if (currX == NULL || currY == NULL)
		return;
	if (prevX != NULL)
		prevX->next = currY;
	else 
		*head_ref = currY;
	if (prevY != NULL)
		prevY->next = currX;
	else
		*head_ref = currX;

	struct Node* temp = currY->next;
	currY->next = currX->next;
	currX->next = temp;
}
void push(struct Node** head_ref, int new_data)
{
	struct Node* new_node
		= (struct Node*)malloc(sizeof(struct Node));


	new_node->data = new_data;


	new_node->next = (*head_ref);

	(*head_ref) = new_node;
}

void printList(struct Node* node)
{
	while (node != NULL) {
		printf("%d ", node->data);
		node = node->next;
	}
}

int main()
{
	struct Node* start = NULL;
	push(&start, 6);
	push(&start, 5);
	push(&start, 4);
	push(&start, 3);
	push(&start, 2);
	push(&start, 1);

	printf("\n Linked list before calling swapNodes() ");
	printList(start);

	swapNodes(1,6,&start);

	printf("\n Linked list after calling swapNodes() ");
	printList(start);

	return 0;
}


22.CONCATE 2 CIRCULAR LL
#include<stdio.h>
#include<stdlib.h>
struct node
{
    int info;
    struct node *link;
};
struct node *create_list(struct node *last);
void display(struct node *last);
struct node *addtoempty(struct node *last,int data );
struct node *addatend(struct node *last,int data);
struct node *concat(struct node *last1,struct node *last2);
main( )
{
    struct node *last1=NULL,*last2=NULL;
    last1=create_list(last1);
    last2=create_list(last2);
    printf("First list is :  ");
    display(last1);
    printf("Second list is :  ");
    display(last2);
    last1=concat(last1, last2);
    printf("Concatenated list is  : ");
    display(last1);
}
struct node *concat( struct node *last1,struct node *last2)
{
    struct node *ptr;
    if(last1==NULL)
    {
        last1=last2;
        return last1;
    }
    if(last2==NULL )  
        return last1;
    ptr=last1->link;
    last1->link=last2->link;
    last2->link=ptr;
    last1=last2;
    return last1;
}
struct node *create_list(struct node *last)
{
    int i,n;
    int data;
    printf("Enter the number of nodes : ");
    scanf("%d",&n);
    last=NULL;
    if(n==0)
        return last;
    printf("Enter the element to be inserted : ");
    scanf("%d",&data);
    last=addtoempty(last,data);
       
    for(i=2;i<=n;i++)
    {
        printf("Enter the element to be inserted : ");
        scanf("%d",&data);
        last=addatend(last,data);   
    }
    return last;
}
void display(struct node *last)
{
    struct node *p;
    if(last==NULL)
    {
        printf("List is empty\n");
        return;
    }
    p=last->link;  
    do
    {
        printf("%d ", p->info);
        p=p->link;
    }while(p!=last->link);
    printf("\n");
}
struct node *addtoempty(struct node *last,int data)
{
    struct node *tmp;
    tmp = (struct node *)malloc(sizeof(struct node));
    tmp->info = data;
    last = tmp;
    last->link = last;
    return last;
}
struct node *addatend(struct node *last,int data)
{
    struct node *tmp;
    tmp = (struct node *)malloc(sizeof(struct node));
    tmp->info = data;
    tmp->link = last->link;
    last->link = tmp;
    last = tmp;
    return last;
}
23.MIN MAX OF A CIRCULAR LL
#include <stdio.h>  
#include <string.h>  
#include <stdlib.h>   
struct node{ 
    int data;  
    struct node *next;  
};  
struct node *head = NULL;  
struct node *tail = NULL;  
void add(int data)
{  
    struct node *newNode = (struct node*)malloc(sizeof(struct node));  
    newNode->data = data;  
    if(head == NULL)
    {
        head = newNode;  
        tail = newNode;  
        newNode->next = head;  
    }else
	{  
        tail->next = newNode;  
        tail = newNode;  
        tail->next = head;  
    }  
}   
void minNode()
{  
    struct node *current = head;  
    int min = head->data;  
    if(head == NULL) {  
        printf("\nList is empty");  
    }  
    else {  
         do{  
             if(min > current->data) {  
                 min = current->data;  
             }  
             current= current->next;  
        }
		while(current != head);  
        printf("Minimum value node in the list: %d", min);  
    }  
}  
void maxNode() {  
    struct node *current = head;  
    int max = head->data;  
    if(head == NULL) {  
        printf("\nList is empty");  
    }  
    else {  
         do{  
             if(max < current->data) {  
                 max = current->data;  
             }  
             current= current->next;  
            }while(current != head);  
        printf("\nMaximum value node in the list: %d", max);  
    }  
}  
      
int main()  
{  
    add(5);  
    add(20);  
    add(10);  
    add(1);  
    minNode();  
    maxNode();    
   return 0;  
}  

24. 2 BINARY TREES ARE IDENTICAL OR NOT
#include <stdio.h>
#include <stdlib.h>
struct node {
	int data;
	struct node* left;
	struct node* right;
};
struct node* newNode(int data)
{
	struct node* node= (struct node*)malloc(sizeof(struct node));
	node->data = data;
	node->left = NULL;
	node->right = NULL;
	return (node);
}
int identicalTrees(struct node* a, struct node* b)
{
	if (a == NULL && b == NULL)
		return 1;
	if (a != NULL && b != NULL) {
		return (a->data == b->data
				&& identicalTrees(a->left, b->left)
				&& identicalTrees(a->right, b->right));
	}
	return 0;
}
int main()
{
	struct node* root1 = newNode(1);
	struct node* root2 = newNode(1);
	root1->left = newNode(2);
	root1->right = newNode(3);
	root1->left->left = newNode(4);
	root1->left->right = newNode(5);
	root2->left = newNode(2);
	root2->right = newNode(3);
	root2->left->left = newNode(4);
	root2->left->right = newNode(5);
	if (identicalTrees(root1, root2))
		printf("trees are identical.");
	else
		printf("Trees are not identical.");

	getchar();
	return 0;
}
25.HEIGHT OF A BT:
#include <stdio.h>
#include <stdlib.h>
struct node {
	int data;
	struct node* left;
	struct node* right;
};
int height(struct node* node)
{
	if(node ==NULL)
	return 0;
	else{
		int leftHeight=height(node->left);
		int rightHeight= height(node->right);
		if (leftHeight>rightHeight)
			return ( leftHeight+ 1);
		else
			return (rightHeight + 1);
	}
}
struct node* newNode(int data)
{
	struct node* node= (struct node*)malloc(sizeof(struct node));
	node->data = data;
	node->left = NULL;
	node->right = NULL;
	return (node);
}
int main()
{
	struct node* root = newNode(1);
	root->left = newNode(2);
	root->right = newNode(3);
	root->left->left = newNode(4);
	root->left->right = newNode(5);
	printf("Height of tree is %d", height(root));
	getchar();
	return 0;
}
26.BT IS HEIGHT BALANED OR NOT:
#include <stdio.h>
#include <stdlib.h>
#define bool int
struct node {
    int data;
    struct node* left;
    struct node* right;
};
int height(struct node* node);
bool isBalanced(struct node* root)
{
    int lh;
    int rh;
    if (root == NULL)
        return 1;
    lh = height(root->left);
    rh = height(root->right);
    if (abs(lh - rh) <= 1 && isBalanced(root->left)&& isBalanced(root->right))
        return 1;
    return 0;
}
int max(int a, int b) { return (a >= b) ? a : b; }
int height(struct node* node)
{
    if (node == NULL)
        return 0;
    return 1 + max(height(node->left), height(node->right));
}
struct node* newNode(int data)
{
    struct node* node= (struct node*)malloc(sizeof(struct node));
    node->data = data;
    node->left = NULL;
    node->right = NULL;
    return (node);
}
int main()
{
    struct node* root = newNode(1);
    root->left = newNode(2);
    root->right = newNode(3);
    root->left->left = newNode(4);
    root->left->right = newNode(5);
    root->left->left->left = newNode(8);
    if (isBalanced(root))
        printf("Tree is balanced");
    else
        printf("Tree is not balanced");
    getchar();
    return 0;
}

27.DFS:
graph = {
    '5' : ['3','7'],
    '3' : ['2', '4','5'],
    '7' : ['8','5'],
    '2' : ['3'],
    '4' : ['3','8'],
    '8' : ['4','7']
}

visited = set() 
def dfs(visited, graph, node):
    if node not in visited:
        print (node)
        visited.add(node)
        for neighbour in graph[node]:
            dfs(visited, graph, neighbour)

print("dfs is:")
dfs(visited, graph, '5')

28.BFS:
graph = {
  '5' : ['3','7'],
  '3' : ['2', '4'],
  '7' : ['8'],
  '2' : [],
  '4' : ['8'],
  '8' : []
}
visited = []
queue = [] 

def bfs(visited, graph, node):
  visited.append(node)
  queue.append(node)
  while queue:      
    m = queue.pop(0) 
    print (m, end = " ") 

    for neighbour in graph[m]:
      if neighbour not in visited:
        visited.append(neighbour)
        queue.append(neighbour)
print("Following is the Breadth-First Search")
bfs(visited, graph, '5')

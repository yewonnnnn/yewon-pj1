# [DSA PROJ1]2020270408 김예원
### E. rotate_circularLinkedList

```
if (list->tail->next != list->head) 
{
	printf("Function rotote_circularLinkedList: The list type is not Circular Linked list.\n"); //메세지 출력
}
```
list의 tail의 next와 head가 일치하지 않는(circularlinkedlist가 아닌)경우
```
else 
{
	int i=0;
	while(i<rotate_num )
	{
		if(i==rotate_num-1)
		{
			printf("Function rotate_circularLinkedList: Complete the %d time rotation.\n", rotate_num); break;
		}
		list->head=list->head->next ;
		i++;

	}
}
```
circularlinkedlist의 경우 rotate_num보다 i가 작으면 head의 위치를 다음 위치로 이동 시키고 i를 1증가시키는 과정을 i=rotate_num-1가 될때까지 진행시킨다.

### F. check empty
```

if(stack->top <0)
{ 
	printf("The stack is empty.\n");
	return 1;
}
```
stack 이 비어있어 stack->top=-1 인 경우에 The stack is empty 메세지를 출력한 후 1을 return한다
```
else
{
	printf("The stack is not empty.\n");
	return 0;
	}
```
stack->top이 -1이 아닌경우 stack이 비워져있지 않다는 뜻이므로 The stack is not empty를 출력하고 0을 return 한다. 

### G. check full
```
int check_full(struct Stack* stack)
{
	if(stack->top == MAX_SIZE-1)
{ 
	return 1;
}
```
stack이 비워져 있는 경우 stack->top=-1 이므로 stack이 다 채워져 있다면 stack->top의 값이 Max size -1 이 될 것이다. 이때 1을 return한다.
```
else
{
	return 0;
	}
}
```
stack 이 다 채워져 있지 않다면 0 을 return 한다.

### H. push
```
int push(struct Stack* stack, int item) 
{

if (stack->top == MAX_SIZE-1)
{
printf("Stack overflow: Cannot push %d onto the stack.\n", item);
return -1;
}
````
stack 이 다 채워져 있다면 push할 공간이 없으므로 Stack overflow: Cannot push %c onto the stack. 를 출력하고 -1을 return 한다. 
```
else
{
stack->stk[stack->top++] = item;
return 1;
}
}
```
stack에 item을 push할 공간이 있다면 원래 stack의 top위치 다음에 item을 추가한다

### I. pop
```
int pop(struct Stack* stack) 
{
	int result;
	if (stack->top < 0) 
		{
			printf("Error: The stack is empty.\n");
		return -1;
		}
```
stack이 비어있어 stack->top=-1인 경우에 element가 없어 pop이 불가능 하므로 Error: The stack is empty. 메세지를 출력하고 -1을 return 한다.
```
	else
	    {
			result = stack->stk[stack->top--];
		return result;
		}
}
```
stack 이 비어있지 않는 경우 stack의 top에 있는 element를 result에 대입한 후 result를 return 하고 stack의 크기를 하나 줄인다.

### J. peek
```
int peek(struct Stack* stack) 
{
	int result;
if (stack->top <0) 
		{
			printf("Error: The stack is empty.\n");
		return -1;
		}
else
{
	result=stack->stk[stack->top];
}
}
```
pop과 비슷한 과정이다. 하지만 pop과는 다르게 result에 stack의 top값을 대입한 후 stack 의 크기는 유지한다. 

### K. perform operation
```
int perform_operation(int operand_1, int operand_2, char operator) 
{
int result;
switch(operator)
{
	case '+':  result = operand_1 + operand_2; break;
	case '-':  result = operand_1 - operand_2; break;
	case '*':  result = operand_1 * operand_2; break;
```
+,-,*, /  4개의 operation 중 해당하는 결과를 각각 실행시켜야 하므로 switch case 문을 사용한다.
```
	case '/':  if (operand_2 != 0) {result = operand_1/operand_2;}
	           else {printf("Division by zero is not allowed.\n"); return -1;}
			   break;
```
나눗셈의 경우 분모가 0이면 나눌 수 없으므로 if else문을 통해 operand_2가 0이 아니라면 result = operand_1/operand_2 계산값을 result에 대입하고 0이라면 Division by zero is not allowed.을 출력하고 -1을 return 하도록 한다.
```
    default: printf("Invalid operator:%c\n", operator);
             return -1; 
			 break;
}
```
+,-,*, /  4개의 operation이 아닌 다른 operation 이 입력되었을 경우 'Invalid operator: operator' 을 출력하고 -1을 return 한다.
```
return result;
}
```
switch case문을 빠져나오면 result를 return 한다.

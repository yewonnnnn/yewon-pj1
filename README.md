# [DSA PROJ1]2020270408 김예원
E. rotate_circularLinkedList

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

F. check empty
```


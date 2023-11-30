### 1. Heap common operations
A)  void buildHeap(HEAP h, int* array, int arraySize)
```
{
	if (h!=NULL)
```
heap이 존재한다면
 ```
	{
	for(int i=0; i<arraySize; ++i)
	{
		h->heapData[i]=array[i];
	}
```
array의 배열을 heap에 순서대로 대입
```
    for (int i=h->size/2-1; i>=0; --i)
	{
		int large = i;
		int left = 2*i+1;
		int right =2*i+2;
		if (left< h->size && h->heapData[left] > h->heapData[large])
		{
			large = left;
		}

 	if (right< h->size && h->heapData[right] > h->heapData[large])
		{
			large = right;
		}
	}
	printf("Heap built");
	}
```
heap order property를 맞춰준다
```
	else
	{
	printf("Error: No heap exists.\n");}
}
```
heap이 존재하지 않으면 에러메세지 출력

B)  void deleteHeap(HEAP h)
```
	if(h!=NULL)
	{
		h->heapData=NULL;
		h->size=0;
		printf("successfully deleted");
	}
```
heap이 존재하면 heapdata를 NULL로 만들어 heap을 삭제하고 size도 0으로 만든 뒤 successfully deleted를 출력
```
	else
	{
	printf("Error: No heap exists.\n");}
}
```
heap이 존재하지 않으면 에러메세지 출력

C) int dequeueHeap(HEAP h)
```
	if(h !=NULL)다

D)  void selectionSort(int *Array)
```
	int size =20;
	int i,j,min;
	for(i=0; i<size-1; i++)
	{
	min=i;
	for(j=i+1;j<size-1;j++)
	{
		if(Array[i]>Array[j])
		min=j;
	}
	}
	swap(&Array[i], &Array[min]);
```	
최소값min을 찾고 비교해 나가면서 swap을 해준다.


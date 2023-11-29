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
```

```
		if (right< h->size && h->heapData[right] > h->heapData[large])
		{
			large = right;
		}
	}
	printf("Heap built");
	}
```
```
	else
	{
	printf("Error: No heap exists.\n");}
}
```
hea[이 존재하지 않으면 에러메세지 출력

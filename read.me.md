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

```
	else
	{
	printf("Error: No heap exists.\n");}
}
```
C)  int findDepth(HEAP h)
```
	if(h!=NULL)
{
	int depth=0;
	int i;
	for(i=0; i<h->size; i++)
	{
		i=(i-1)/2;
		depth++;
	}
	return depth;
	printf("Depth is : %d", depth);
}
```
```
else
	{
	printf("Error: No heap exists.\n");}
}
```
heap이 존재하지 않으면 에러메세지 출력

### 2. Heap common operations
A)  void insertNode(HEAP h, int value)
```
	if(h!=NULL)
	{
	h->size++;
	int i;
	 i = h->size-1;
	h->heapData[i]=value;
```
```
	while ( i > 0 && h->heapData[( i - 1)/2] < h->heapData[i])
    {
		h->heapData[i] = h->heapData[(i-1)/2];
	}
	printf("Not Implemented!\n");
	}
```
```
	else
	{
	printf("Error: No heap exists.\n");}
}
```
heap이 존재하지 않으면 에러메세지 출력

B)  int dequeueHeap(HEAP h)
```
	if(h !=NULL)
	{
	h->heapData[0]=h->heapData[h->size-1];
	h->size--;
		int i;
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
	else
	{
	printf("Error: No heap exists.\n");}
}
```

### 3. Sorting
B)  void bubbleSort(int *Array)
```
	int i,j;
	int size = 20;
	for( i=0; i<size-1; i++)
		for(j=size; j>=i+1; j--)
			if (Array[j-1]>Array[j])
			{
				swap(&Array[j-1], &Array[j]);
			}
	printf("%d", Array[i]);
}
```

C)  void insertionSort(int *Array)
```
	int a,i,j;
	int size =20;
	for ( i=1; i<size; i++)
	{
		a=Array[i];
		j=i-1;
		while (j>=0 && Array[j]<a)
		{
			swap(&Array[j], &Array[i]);
			j=j-1;
		}
	}

	printf("Not Implemented!\n");
}
```

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



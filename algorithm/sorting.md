# 정렬
정렬이란 데이터를 어떤 기준에 따라 오름차순/내림차순으로 정리하는 것이다.  
(*해당 문서에서는 숫자를 오름차순으로 정렬하는 예시만을 다루었다.)  
대표적인 정렬 알고리즘으로 다음과 같은 것들이 있다.
- 선택(Selection): 가장 작은 값을 ***선택*** 하여 맨앞과 자리를 바꾼다.  
- 삽입(Insertion): 정렬된 값들을 밀어낸후 알맞은 자리에 ***삽입*** 한다.  
- 버블(Bubble): 자신vs인접한 것, 둘 중 더 가벼운 ***버블*** 이 위로 뜬다(=값이 작은 것이 앞으로)...-_-;
- 합병(Merge): 리스트를 잘게 분할하여 각각 정렬한 후 ***합병*** 한다.
- 퀵(Quick) 
- 힙(Heap)

## Big-O에 따른 정렬 알고리즘 분류
- **O(n<sup>2</sup>)**: 선택/삽입/버블. 비효율적이지만 구현이 쉽다.  
- **O(nlogn)**: 합병/퀵/힙. 효율적이지만 구현이 어렵다.  

***주의: 언제나 시간복잡도가 낮은 알고리즘만이 좋은 것은 아니다.***  
데이터의 수가 적어 수행시간에 큰 차이가 없는 경우 구현이 쉬운 알고리즘을 사용하기도 한다.

## 선택 정렬(Selection Sort)
i = 0부터 n-2까지 반복:  
  미정렬된 값 A[i]~A[n-1] 중 가장 작은 값을 찾는다.=***선택***  
  미정렬 리스트의 맨앞 값(=A[i])과 자리를 바꾼다.
### Pseudo code
```c
SelectionSort(A,n)

  for i = 0 to n-2 do
    find index of minimum value in (A[i]~A[n-1])
    swap A[i] and A[minIndex]

```
### Source code
```c++
void selectionSort(vector<int>& A){
  for(int i=0; i<A.size(); ++i){
    int minIndex = i;
    for(int j=i+1; j<A.size(); ++j){
      if(A[minIndex]>A[j]) minIndex = j;
    }
    swap(A[i], A[minIndex]);
  }
}
```

## 삽입 정렬(Insertion Sort)
i = 0부터 n-1까지 반복:  
  정렬된 값 A[i-1]~A[0] 중 첫번째로 A[i]보다 작은 값이 나올때까지 정렬된 값을 밀어낸다.  
  첫번째로 A[i]보다 작은 값 뒤에 A[i]를 넣는다.=***삽입***
    

### Pseudo code
```c
InsertionSort(A,n)

  for i = 0 to n-1 do
    (j = i to 1)
    while A[j]<A[j-1] do
      swap A[j-1] and A[j]
```
### Source code
```c++
void insertionSort(vector<int>& A){
  for(int i=0; i<A.size(); ++i){
    int j = i;
    while(j>0 && A[j]<A[j-1]){
      swap(A[j-1], A[j]);
      --j;
    }
  }
}
```

## 버블 정렬(Bubble Sort)

# 기타 정렬 알고리즘
- 기수(Radix)
- 셸(Shell)

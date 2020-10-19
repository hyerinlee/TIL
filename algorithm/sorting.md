# 정렬
정렬이란 데이터를 어떤 기준에 따라 오름차순/내림차순으로 정리하는 것이다.  
(*해당 문서에서는 숫자를 오름차순으로 정렬하는 예시만을 다루었다.)  
대표적인 정렬 알고리즘으로 다음과 같은 것들이 있다.
- 선택(Selection): 가장 작은 값을 ***선택*** 하여 맨앞과 자리를 바꾼다.  
- 삽입(Insertion): 정렬된 값들을 하나씩 밀어낸후 알맞은 자리에 ***삽입*** 한다.  
- 버블(Bubble): 가벼운 ***버블*** 이 인접한 버블을 하나씩 제치며 위로 뜬다(=값이 작은 것이 앞으로)...-_-;
- 합병(Merge): 리스트를 잘게 분할하여 각각 정렬한 후 ***합병*** 한다.
- 퀵(Quick) 
- 힙(Heap)

## Big-O에 따른 정렬 알고리즘 분류
- **O(n<sup>2</sup>)**: 선택/삽입/버블. 비효율적이지만 구현이 쉽다.  
- **O(nlogn)**: 합병/퀵/힙. 효율적이지만 구현이 어렵다.  

***주의: 언제나 시간복잡도가 낮은 알고리즘만이 좋은 것은 아니다.***  
데이터의 수가 적어 수행시간에 큰 차이가 없는 경우 구현이 쉬운 알고리즘을 사용하기도 한다.

<br/>

## 선택 정렬(Selection Sort)
i = 0부터 n-2까지 반복:  
&nbsp;&nbsp;A[i]~A[n-1] (미정렬된 값들) 중 가장 작은 값을 찾는다.=***선택***  
&nbsp;&nbsp;미정렬 리스트의 맨앞 값(=A[i])과 자리를 바꾼다.
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
<br/>

## 삽입 정렬(Insertion Sort)
i = 0부터 n-1까지 반복:  
&nbsp;&nbsp;A[i]와 정렬된 값 A[i-1]~A[0]을 비교하며, A[i]보다 작은 값이 나올때까지 정렬된 값을 밀어낸다.  
&nbsp;&nbsp;첫번째로 A[i]보다 작은 값 뒤에 A[i]를 넣는다.=***삽입***
    

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
<br/>

## 버블 정렬(Bubble Sort)
i = 1부터 n-1까지 반복:  
&nbsp;&nbsp;A[n-1]~A[i] (미정렬된 값들) 차례로 자신과 한칸 앞값을 비교하여, 앞값이 더 크면 자리를 바꾼다.  
&nbsp;&nbsp;A[n-1]~A[i]까지 비교를 마치면 가장 가벼운 ***버블*** 하나가 정렬되게 된다.
  
### Pseudo code
```c
BubbleSort(A,n)

  for i = 1 to n-1 do
    for j = n-1 to i do
      if A[j]<A[j-1] then swap A[j] and A[j-1]
```
### Source code
```c++
void bubbleSort(vector<int>& A){
  for(int i=1; i<A.size(); ++i){
    for(int j=A.size()-1; j>=i; --j){
      if(A[j]<A[j-1]) swap(A[j], A[j-1]);
    }
  }
```
<br/>
<br/>

## 합병 정렬(Merge Sort)
더이상 나눠지지 않을 때까지 **(1)잘게 나눈 후 (2)새 리스트에 정렬하여 ***합병*** 한다.**  
**(1) 잘게 나눈 후(Merge Sort)**  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;= 부분리스트 크기가 1이 될때까지 반으로 나눈다.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;('반으로 나눈다'는 것은 left,right를 지정하고 이들 간격을 좁히는 것으로 구현)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;= left 또는 right에 mid값을 대입  
**(2) 새 리스트에 정렬하여 합병한다(Merge)**  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;= 나누어진 두 부분리스트의 맨앞 값(left, mid+1)을 비교하여 작은 값을 새 리스트에 추가한다.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(두 부분리스트의 모든 값이 추가될 때까지)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;= 새 리스트에 모든 값이 추가되면 기존 배열에 복붙한다.

### Pseudo code
```c
MergeSort(list,left,right)

  if sublist not contains only single element then
    mid = (left+right)/2
    MergeSort(list,left,mid)
    MergeSort(list,mid+1,right)
    Merge(list,left,mid,right)
```    
```c    
Merge(list,left,mid,right)

  i = left, j = mid+1, k = left
  Until all elements are added to the new list
    if left < mid+1
      then
        sorted[k++] = list[i++]
      else
        sorted[k++] = list[j++]
  copy sorted and paste into list
```
### Source code
```c++
```


# 기타 정렬 알고리즘
- 기수(Radix)
- 셸(Shell)

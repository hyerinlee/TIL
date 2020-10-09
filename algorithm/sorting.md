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
A[0]부터 A[n-2]까지,  
미정렬된 값 A[i]~A[n-1] 중 가장 작은 값을 찾는다.=***선택***  
미정렬 리스트의 맨앞 값(=A[i])과 자리를 바꾼다.
### Pseudo code
```c
selection_sort(A,n){
  for i ← 0 to n-2 do
    min ← index of minimum value in (A[i]~A[n-1])
    swap A[i] and A[min]
}
```
### Source code
```c
#define SWAP(x, y, tmp) ((tmp)=(x), (x)=(y), (y)=(tmp))
void selection_sort(int list[], int n){
  int min,tmp;
  for(int i=0;i<n-1;i++){
    min=i;
    for(int j=i+1;j<n;j++){
      if(list[j]<list[min]) min=j;
    }
    SWAP(list[i], list[min], tmp);
  }
}
```

## 삽입 정렬(Insertion Sort)

## 버블 정렬(Bubble Sort)

# 기타 정렬 알고리즘
- 기수(Radix)
- 셸(Shell)

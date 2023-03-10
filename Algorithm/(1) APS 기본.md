# 알고리즘

- 좋은 알고리즘
    1. 정확성 : 얼마나 정확하게 동작하는가
    2. 작업량 : 얼마나 적은 연산으로 원하는 결과를 얻어내는가
    3. 메모리 사용량 : 얼마나 적은 메모리를 사용하는가
    4. 단순성 : 얼마나 단순한가
    5. 최적성 : 더 이상 개선할 여지없이 최적화 되었는가

## 버블 정렬

## 카운팅 정렬
- 항목들의 순서를 결정하기 위해 집합에 각 항목이 몇 개씩 있는지 세는 작업을 하여, 선형 시간에 정렬하는 효율적인 알고리즘

- 제한사항 
  - 정수나 정수로 표현할 수 있는 자료에 대해서만 적용 가능
  - 카운트들을 위한 충분한 공간을 할당하려면 집합 내의 가장 큰 정수를 알아야 한다.

```python
# 조건 : 0 ~ 5까지의 정수
arr = [0,1,2,3,4,5]
count = [0] * 6 # 조건에 부합하는 정수의 갯수 + 1만큼의 배열을 생성
count_accumulate = [0] * 6
for x in arr:
    count[x] += 1

for i in range(1,4):
    count_accumulate = count_accumulate[i -1] + count_accumulate[i] # 누적합
```

```python
def counting_Sort(A, B ,K)
# A [] 입력 배열 (0 to k)
# B [] 정렬된 배열
# C [] 카운트 배열

    C = [0] * (k + 1)
    
    for i in range(0,len(A)) :
        C[A[i]] += 1

    for i in range(1, len(C)):
        C[i] += C[i -1]
    for i in range(len(B) - 1 , -1, -1):
        c[A[i]] += 1
        B[C[A[i]]] = A[i]

```

## 완전 검색
- 모든 경우의 수를 나열해보고 확인하는 기법
- Brute-force 기법이라고도 불리 운다.
- 경우의 수가 상대적으로 작을 때 유용하다.

## 순열
- 서로 다른 것들 중 몇 개를 뽑아서 한 줄로 나열하는 것
- 서로 다른 n개 중 r개를 택하는 순열은 아래와 같이 표현한다.
  - nPr
  - nPr = n * (n -1) * (n-2) ... * (n -r + 1)
  - n!/(n -r)! # 순열의 갯수
  - nPn = n! -> Factorial

```python 

for i1 in range(1,4):
    for i2 in range(1,4):
        if i2 != i1:
            for i3 in range(1 , 4):
                if i3 != i1 and i3 != i2 :
                    print(i1,i2,i3)

```
## 탐욕(Greedy) 알고리즘
- 탐욕 알고리즘은 최적해를 구하는 데 사용되는 근시안적인 방법
-  여러 경우 중 하나를 결정해야 할 때마다 그 순간에 최적이라고 생각되는 것을 선택해 나가는 방식으로 진행하여 최종적인 해답에 도달
-  각 선택의 시점에서 이루어지는 결정은 지역적으로는 최적이지만, 그 선택들을 계속 수집하여 최종적인 해답을 만들었다고 하여, 그것이 최적이라는 보장은 없다.
-  일반적으로, 머릿속에 떠오르는 생각을 검증 없이 바로 구현하면 Greedy 접근이 된다

1. 해 선태 : 현재 상태에서 부분 문제의 최적 해를 구한 뒤, 이를 부분해집합에 추가한다.

2. 실행 가능성 검사 : 새로운 부분해 집합이 실행 가능한지 확인한다. 곧, 문제의 제약 조건을 위반하지 않는지를 검사한다.

3. 해 검사 : 새로운 부분해 집합이 문제의 해가 되는지를 확인한다.
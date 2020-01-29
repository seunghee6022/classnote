# Algorithm

> 어떤 문제를 해결하기 위한 절차,방법

20.01.28

***

#### Tip

__함수보다 내가 만든게 더 빠르다. 초반부터 함수쓰기보단 만들어써라.__

문제를 잘 읽어보고 -> 대충이라도 구현 시 설계를 해야 한다.

개발자가 되야지 코더가 되면 안된다!!!!(설계를 할 줄 알아야)

***

#### 설계 과정

1. 요구사항 분석
2. 설계(방법 찾기)
3. 구현(설계를 잘하면 코딩에 불과)
4. 테스트
5. 유지보수



***

__컴퓨터 상식__

프로세스 - 실행중인 프로그램

쓰래드(thread) - 프로그램 하나에 여러개 돌아가는거

cpu는 한번에 하나만 처리- 빨라서 동시에 실행한다고 느끼는 것

주소값은 byte로 되어 있다.

***

## 1.배열 1 (Array 1)

* 가지치기 -> 재귀(recurrsion) 필요

* 완전검색 -> 반복문 이용, 재귀
* 그리디 알고리즘 - 그냥 검증 없이 막 해버리는거. 최적해 찾을 수도/아닐수도 -> 그래서 완전검색 필요(확실한 답을 찾을 수 있으므로)
* 백트래킹 -> 완전검색 + 가지치기(재귀)
* 분할정복 
* Dynamic planning 동적 계획법



***

### 알고리즘의 성능 측정 기준

1. 정확성
2. 작업량 : 적은 연산
3. 메모리(Ram) 사용량 : 적게
4. 단순성 : 단순해야
5. 최적성 : 개선의 여지 없이



#### 알고리즘 성능 분석

작업량으로 비교

__시간복잡도(Time Complexity)__ 이용 

* 실행되는 명령문의 개수를 계산
* 실제 걸리는 시간 측정



#### 시간복잡도 - 빅-오(O) 표기법

계수는 생략하여 표시

O(3n^2+2n+4) = O(n^2) => ex) for문 2번이면 되네

<img src="C:\Users\multicampus\algorithm_class\필기\image-20200128104644512.png" alt="image-20200128104644512" style="zoom: 67%;" />

* O(1) :  

* O(logn) : 이진탐색
* O(n) : 순차이진탐색
* O(nlogn) : Heap, merge, quick sort...
* O(n^2) : 버블, 선택,삽입 정렬...
* O(n^3) : floyd플로이드 알고리즘, 인접행렬의 곱
* O(2^n) : 부분집합,조합
* O(n!): 순열



***

### 배열 (Array)

일정한 자료형의 변수들을 하나의 이름으로 열거하여 사용하는 자료구조

IM수준의 문제

![image-20200128113621825](C:\Users\multicampus\algorithm_class\필기\image-20200128113621825.png)

![image-20200128113631622](C:\Users\multicampus\algorithm_class\필기\image-20200128113631622.png)

***

### 완전 검색(Exhausted Search)

brute-force : 진짜 다 해보는 방법.

ex) greedy 알고리즘은 아님- 이건 탐욕적이라 다 안해보고 답을 찾으려는 방법

***

### Baby-gin Game -> 기억해야

#### !!!!!!!!!!!!! %이용한 카운팅 - 리스트 사용 등 매우 유용하다.!!!!!!!!!!!!!!

```python
1. %, // 방법 - 공부하자
for i in range(6):
    c[num%10] += 1
    num//=10 # 숫자에서 일의자리씩 빼냄
    
2. 문자로 하나씩 빼내서
for i in str(num) :
    c[int(i)%10] +=1
```

```python
#그리디 알고리즘

num = 456789
# idx 0부터 11까지( 9,10,11 확인 위해 리스트 인덱스 11까지 만듬)
c = [0] * 12

#숫자와 일치하는 리스트인덱스 이용한 카운팅 -> num을 한 숫자로 보고 일의자리씩 떼서 사용
for i in range(6):
    c[num%10] += 1
	num//=10
#숫자와 일치하는 리스트인덱스 이용한 카운팅 ->리스트의value를 통해 카운팅(원소가 0~9인 1의자리이므로)
for i in str(num) :
    c[int(i)] +=1


# while의 제어값. 최대 숫자 9의 인덱스인 10과도 일치
i = 0
#트리플과 런의 횟수
tri = run = 0
while i < 10 : #인덱스 0부터 차례대로 찾아본다.
    if c[i] >= 3 : #triplete 조사 후 데이터 삭제
        c[i] -=3 
        tri +=1
        continue # 이유 : 두번이나 트리플렛이 있을 것을 대비해서 555555
    if c[i] >= 1 and c[i+1]>=1 and c[i+2]>=1 : #연속된 3 자리에 숫자가 들어있을 때
        c[i]-=1
        c[i+1]-=1
        c[i+2]-=1 #각각 조사 후 데이터 삭제
        run += 1
        continue #이유 : 2번이나 같은 숫자로 run이 있을 경우를 대비해서. 123123 같은 경우
    i+=1
    
if run + tri == 2 : print("Baby Gin")
else : print("Lose")
```

***

### 정렬

2개 이상의 자료를 특정 기준애 의해 작은 값부터 큰 값(오름차순) 혹은 그 반대의 순서대로 (내림차순) 재배열하는 것

#### Bubble sort  - O(n^2)

오름차순

```python
num=[2,6,15,8,52,56,3,7,67,98,44,77,5,32,1,13]

def asc_bubblesort(num):
    for i in range(len(num)-1,0,-1):
        for j in range(0,i):
            if num[j] > num[j+1]:
                num[j],num[j+1] = num[j+1],num[j]
    return num

```

내림차순 (부등호 차이)

```python
def desc_bubblesort(num):
    for i in range(len(num)-1,0,-1):
        for j in range(0,i):
            if num[j] < num[j+1]:
                num[j],num[j+1] = num[j+1],num[j]
    return num
```



#### Counting Sort - O(n+k) n:리스트길이, k:정수의 최대값

항목들의 순서를 결정하기 위해 집합에 각 항목이 몇 개씩 있는지 세는 작업을 하여, 선형 시간에 정렬하는 효율적인 알고리즘

__정수나 정수로 표현할 수 있는 자료에 대해서만 적용 가능 ex)인덱스__

카운트들을 위한 충분한 공간을 할당하려면 집합 내의 가장 큰 정수를 알아야 한다.

```python
#counting sort
data = [0,4,1,3,1,2,4,1] #입력배열

def countingsort(data):
    counts = [0]*len(set(data)) #카운트 배열
    temp =[0]*len(data) #정렬된 배열

    #counts만들기
    for i in data:
        counts[i]+=1

    for i in range(1,5):
        counts[i] += counts[i-1]

    #temp 채우기
    for j in range(len(data)-1,0,-1): #뒤에서 부터 하나씩 올 때

        temp[counts[data[j]]-1]= data[j]
        counts[data[j]] -= 1

    print(temp)

countingsort(data)
```





***

***

20.01.29

***

***

## 2. 배열2(Array2)


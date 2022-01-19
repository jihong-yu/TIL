# 1. 계수정렬

```python
array = [7, 4, 9, 0, 3, 1, 6, 2, 9, 1, 4, 8, 0, 2, 2]

#출력할 배열 선언
result = []
#입력받은 배열의 최댓값을 기준으로 개수를 저장할 배열 선언
sort_list = [0] * (max(array)+1)

# 각 데이터에 해당하는 인덱스 값 증가(== 인덱스가 해당 숫자 이고 들어간 값이 해당숫자의 개수)
for i in array:
    sort_list[i] += 1

for j in range(len(sort_list)): #새로운 배열에 저장된 길이만큼
    for k in range(sort_list[j]): #그 인덱스에 저장되어 있는 개수만큼
        result.append(j) #그 값을 추가해준다.

print(*result) #언패킹을 이용하여 출력한다.
```

> 자세한 설명은 주석으로 달아놨다.

# 2. 삽입정렬

```python
array = [7, 5, 9, 0, 3, 1, 6, 2, 4, 8]

for i in range(1, len(array)):
    for j in range(i, 0, -1):  # 인덱스 i부터 1까지 1씩 감소하며 반복하는 문법
        if array[j] < array[j - 1]:  # 한 칸씩 왼쪽으로 이동
            array[j], array[j - 1] = array[j - 1], array[j]
        else:  # 앞쪽은 이미 정렬이 되어있기 때문에 자기보다 작은 데이터 만나면 그자리에서 멈춤
            break
print(array)
```

> 주석으로 표기 해놨다.  



# 3. 버블정렬

```python
array = [5, 7, 9, 0, 3, 1, 6, 2, 4, 8, 8, 3]

for i in range(0, len(array)): #하나의 인덱스를 기준으로
    for j in range(i + 1, len(array)): #그 다음 인덱스부터 비교하여 비교 대상보다 크다면 자리를 바꾼다.
        if array[i] > array[j]:
            array[i], array[j] = array[j], array[i]

print(array) 
```





# 4. 퀵정렬

```python
array = [5, 7, 9, 0, 3, 1, 6, 2, 4, 8, 8, 3]


def quick_sort(array, start, end):
    if start >= end:  # start가 end와 같다는 것은 원소가 1개 이기 때문에
        return

    pivot = start
    left = start + 1
    right = end

    while left <= right:  # left가 right를 넘어서는 순간 반복문 종료

        # pivot보다 큰 수를 왼쪽부터 찾아나간다.
        while left <= end and array[left] <= array[pivot]:
            left += 1

        # pivot보다 작은 수를 오른쪽부터 찾아나간다.
        while right > start and array[right] > array[pivot]:
            right -= 1

        if left <= right:  # left가 right보다 작을때는(엇갈리지 않았을때) 두 값을 교체해준다.
            array[left], array[right] = array[right], array[left]
        else:  # left가 right 보다 클때 (엇갈렸을 때) -> 피벗보다 작은 값을 pivot 자리에 보낸다. 피벗값을 right 값으로 이동
            array[pivot], array[right] = array[right], array[pivot]

    # 분할 이후에 다시 right(중간값)을 기준으로 다시 정렬을 수행한다.
    quick_sort(array, right + 1, end)
    quick_sort(array, start, right - 1)

#퀵 정렬 수행
quick_sort(array, 0, len(array) - 1)
print(array)
```



# 4. 퀵정렬2

```python
# 퀵정렬 구하는 식
array = [5, 7, 9, 0, 3, 1, 6, 2, 4, 8, 8, 3]


def quick_sort(array):
    # 만약 길이가 1개 이하라는 것은 정렬할 필요가 없으므로 그 값을 return
    if len(array) <= 1:
        return array

    pivot = array[0]  # pivot값을 가장 앞의 값으로 설정
    tail = array[1:]  # 나머지 값을 그 다음 인덱스 부터 구성

    # 오름차순
    # left_side = [x for x in tail if x <= pivot]  # 분할된 왼쪽 부분
    # right_side = [x for x in tail if x > pivot]  # 분할된 오른쪽 부분

    # 내림차순
    left_side = [x for x in tail if x <= pivot]
    right_side = [x for x in tail if x > pivot]

    # 분할 이후 왼쪽 부분과 오른쪽 부분에서 각각 정렬 수행하고 전체 리스트 반환
    return quick_sort(left_side) + [pivot] + quick_sort(right_side)


new_array = quick_sort(array)
print(new_array)
```


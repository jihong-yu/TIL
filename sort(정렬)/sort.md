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
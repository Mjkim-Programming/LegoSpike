<span style="color:red; font-weight:600">현재 실행이 안되는 문제가 있습니다. 이를 해결해야 합니다.</span>

# 자율주행 프로젝트
**Lego Spike**를 이용하여 자율주행을 제작합니다.<br>
## 목적
동아리 전시회 때 Lego Spike를 이용한 자율주행 자동차를 전시할 계획입니다.<br>
이 코드들은 그때를 위한 코드입니다.<br>

## 해설
**해설을 위해 약간 간단해진 전체 코드입니다.**
```python
def sense():
 for i in range(0,140):
  if(distance < 한계값):
   turn(right)

 for i in range(0,280):
  while(distance < 한계값):
   turn(left)

while(True):
 while(distance > 한계값):
  go(front)
 sense()
```

### 초기값
*distance*는 초음파 센서가 받아오는 값을 cm단위로 변환하여 실시간으로 이용하고 있습니다.<br>
*한계값*은 현재 ~~17cm~~ 7cm로 개발하고 있습니다. 시연을 위해 점차 한계값을 줄여나갈 계획입니다.<br>

### 부분 해설
#### 길찾기 함수
```python
def sense()
```
길찾기 함수를 정의합니다.<br>
```python
for i in rnage(0,140):
 if(distance < 한계값):
  turn(right)
```
만약 감지된 거리가 한계값보다 작으면 오른쪽으로 회전합니다.<br>
이를 140번 반복하여 최대 90도 정도까지 회전합니다.<br>
```python
for i in range(0,280):
 if(distance < 한계값):
  turn(left)
```
만약 감지된 거리가 한계값보다 작으면 왼쪽으로 회전합니다.<br>
이를 280번 반복하여 최대 180도 정도까지 회전합니다.<br><br>
**위의 코드를 통해 앞쪽 180도를 둘러보고 길을 감지합니다.** <br>
#### 실행부
```python
while(True):
 while(distance > 한계값):
  go(front)
 sense()
```
감지된 거리가 한계값 이하가 될 때까지 앞으로 이동합니다.<br>
감지된 거리가 한계값 이하가 되면 길찾기 함수를 실행합니다.

## 타임라인
**2024 / 10 / 14**<br>
기초적인 자율주행 알고리즘 작성 / 코드로 변환<br>
#### Issue
> 길에 적응하기 위해 한계값을 줄여나가야 함

**2024 / 10 / 21**<br>
한계값을 17cm에서 7cm까지 줄임.
#### Issue
> 실제 환경에서도 작동되는가 확인 필요

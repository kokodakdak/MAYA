# MAYA 007 - Wheel 만들기


### create Polygon Tool
* Panel에 Vertex를 찍어서 Polygon Face를 만들어 주는 Tool
* delete: 역순으로 지워짐
* 4번 버튼을 눌러서 와이어모드에서 작업하는 것이 좋다.

### Boolean
* Cube에 cylynder 형태로 구멍을 내는 Tool
* 2개의 obj를 이용해서 구멍을 내는 Tool
* 뚫고 싶은 object를 먼저 선택하고 Source object를 나중에 선택해서 실행.
  * Tool을 실행시키기 전 수행해야 할 작업
    1. Freeze Transformation
    1. History Delete
  * Tool 실행하고 나서 수행할 작업
    1. Delete History
    1. Multi Cut을 이용해서 다각형을 없애준다.
   
### 휠 copy할 때
 Axis|Axis Position|Direction|Merge Threshold
 ---|---|---|---
 X|Bounding box|+|0.001
  
### Wheel 만들기
* 60도 먼저 만들기

### Wheel 회전시키기
* shift + D로 복사(행동복사) 후 rotate X값을 120으로
* 행동복사 한 번 더

### Slide Edge Tool
* edge 선택 후 shift + 마우스 우클릭
* slide edge tool선택
* 마우스 휠 버튼으로 

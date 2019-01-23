# Walking animation
## step 1. 제자리 걷기
1. reference 이미지를 image plane으로 불러오기
    * 카메라 hide
1. side view에서 작업
    * show>NURBS Curves 선택해서 컨트롤러 보이게
1. 첫번째 이미지에 동작 맞추기
    * 골반부터 작업하는 게 좋다
1. perspective view에서 전체 드레그 한 후 S를 눌러서 키찍기(0 frame)
1. 걷는 동작은 Contact 1 &rarr; Down &rarr; Passing Pose &rarr; Up &rarr; Contact 2 &rarr; Down &rarr; Passing Pose &rarr; Up 의 반복이다.

frame|0|3|6|9|12|15|18|21|24
---|---|---|---|---|---|---|---|---|---
**action**|Contact 1|Down|Passing Pose|Up|Contact 2|Down|Passing Pose|Up|Contanct 1

    따라서 0, 3, 6, 9 프레임만 동작을 맞춘 후 나머지는 복사 붙여넣기로 하면 더 빠르게 할 수 있다.(왼발 오른발의 위치만 바꾸기)


   

# 타이어 만들기


#### bend가 속해있는 툴
* deform > nonlinear
  * deform: outline에서 Node로 생성되는 Tool
  * History를 삭제 시 Tool이 지워짐
  * 오브젝트를 왜곡 시키는 Tool
#### bend  
* bend탭의 curvature를 선택하고 마우스 휠버튼을 누른 채 좌우로 이동하면 오브젝트가 구부러진다
* curvature의 기준 축은 회전툴을 이용해서 돌릴 수 있다.
#### bend 실습
1. Cube를 만들어 y푹으로 길게 늘린다.
1. polycube의 subdivision height값을 40으로 준다
1. bend탭의 curvature를 선택하고 휠버튼을 눌러 좌우로 이동해본다.

#### 타이어 패턴조각 만들기
1. plane 하나 만들기
1. z축 잡고 늘려서 직사각형을 만듬
1. subdivision width, height 모두 1로 설정
1. top뷰에서 multicut을 이용해서 세로로 반을 나눈다.
1. 중앙의 edge를 선택해서 bevel을 걸면 양쪽에 edge가 두 개 생긴다.(segment 1)
1. 새로 생긴 edge 두 개를 클릭한 후 스케일툴을 이용해 양쪽으로 벌린다
    * 스케일툴을 이용하면 동일한 간격으로 벌릴 수 있다.
1. 멀티컷을 이용해서 가로로 5개의 edge를 만든다
1. 각 edge를 적당한 위치에 두고 선택하여 bevel를 건다.
    * fraction 0.05 segment 1
    * 이렇게하면 작은 홈이 생긴다.
1. 네모난 면 5개를 선택해서 extrude
1. 면 4개를 선택하고 crtl+마우스 우클릭>to edge>to edge
    * 면을 엣지로 만들어줌
1. bevel
    *fraction 0.1 segment 3
1. 전체 히스토리 삭제, freeze transformation

#### 타이어 패턴 복사하기
1. 자연스럽게 밴드하기 위해 복사 전에 multi cut을 이용해 세로로 정가운데에 엣지를 만들어 주고 베벨을 걸어 2개로 만든다.
1. d+v를 누르고 피봇을 좌하단으로 옮긴다.(복사하기 위한 준비)
1. shift+D로 복사 후, v를 누른 상태로 x축을 잡고 옆으로 이동시킨다.
1. shift + D를 많이(!) 반복해서 패턴을 반복시킨다
1. 모두 선택한 후 shift + 오른쪽 버튼 > combine
1. vertex모드로 선택 후 shift+오른쪽 버튼>merge vertices>merge vertices
    * display>Heads up display> Poly count를 켜서 vertices 수가 줄어드는 걸 꼭 확인할 것!
    * distance threshold 0.001
1. 오브젝트 모드로 선택 후 히스토리 삭제, 빈 폴더 삭제

#### 타이어 패턴 구부려서 원통형으로 만들기
1. bend 적용.
1. 축을 z축으로 90도 돌려서 object와 평행하게 만든다.
1. curvature를 선택한 후 휘어서 원통형으로 만든다.


#### 타이어 구부린 후
1. combine
1. merge vertices>merge vertices
   * distance threshold 0.001
1. multi cut으로 부족한 엣지 추가

#### 타이어 형태 잡기


#### 타이어 두께 만들기
1. 양쪽 가장자리 엣지 선택 후 extrude
1. 바로 R버튼을 눌러서 scale tool로 바꿔서 전체사이즈를 살짝 줄인다.
1. z축을 잡고 밖으로 살짝 빼낸다

#### 타이어 형태 잡기
1. vertex가 너무 많으면 가장자리가 울기 때문에 전체를 vertex로 선택 후 merge vertices> merge vertices해서 가장자리 vertex 수를 줄인다.
1. 다시 양쪽 가장자리 edge를 선택 후 extrude>R 스케일툴을 이용해 나머지 형태를 잡는다

# 사람 얼굴 모델링 - 02
#### 콧구멍 만들기
1. cylinder(subdivisions Axis = 8)
1. 뚜껑만 남기고 없애기
    * modify>center pivot
1. 사이즈 맞추고, 각도에 맞춰서 y축, z축으로 회전
    * front에서 모델링할 땐 z축만 이용한다
1. 엣지를 더블클릭해서 둘레를 선택한 후 extrude
    * y축을 잡고 밖으로 살짝 땡긴다.
1. 가운데 면을 지워서 구멍을 만든다.

#### 코와 콧구멍 연결
1. 지난 시간에 모델링한 부분과 콧구멍을 선택한 후 combine
   * history 삭제(alt+shift+D)
    
#### 콧구멍 주변 모델링
1. 콧구멍부분 엣지 중 아래쪽 2개를 잡고 extrude
    * world pivot을 잡고 아래로 내린다
1. 코끝의 가장 높은 지점에 있는 엣지를 잡고 extrude
    * 콧볼까지 내린다.
    * 제일 가장자리에 있는 엣지를 잡고 살짝 안으로 넣는다.(콧볼 가장자리의 들어간 곳)
    * 하나 안쪽에 있는 엣지를 잡고 콧볼의 가장 넓은 곳에 위치한다
1. 콧구멍을 중심으로 동심원을 그리듯 모델링한다.
1. 콧구멍 주변 엣지와 눈 아래 엣지를 bridge를 이용해서 잇는다
    * division값을 이용해 중간에 엣지를 추가한다
    
#### 입술 모델링
1. front에서 create polygon tool로 입술 모양을 딴다.
1. side에서 형태 맞추기(눈 하듯이)
1. combine
1. 입술 가운데와 코끝 가운데를 append polygon으로 연결
      * 연결해서 생긴 면은 multicut을 이용해 가로 선을 3개 추가한다.
1. side에서 추가한 선을 이용해서 인중의 곡선을 만든다.
1. 윗입술,이랫입술 가운데에 ctrl+multicut을 이용해서 선을 가로로 추가 한다
1. 입술 가운데 선을 side에서 안쪽으로 살짝 넣는다
1. 입술 가장 끝 엣지를 선택 후 extrude
      * z축 방향으로 과감하게
      * 다 뺀 후엔 스케일툴로 바꿔서 y축 방향으로 크기 키워서 지느러미 모양으로 만들기

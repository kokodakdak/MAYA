## Merge Node

### 레이저불빛 보였다가 안보이게 하기

1. Merge 노드 더블클릭
1. 레이저가 보이면 안되는 프레임으로 가서 Mix값을 0으로
1. mix 우클릭> set key
1. 레이저가 보여야 하는 프레임으로 가서 Mix 값을 1으로(이 때는 key 안찍어도 됨)


### 오브젝트가 움직이는 배경 따라가게 하기
- Backdrop
  - 그룹지을 수 있음
  - Backdrop 노드 더블클릭하면 이름 바꿀 수 있음
  - 그룹해제할 땐 노드 선택 후 드래그하여 상자밖으로 꺼내면 됨.
- Tracker
  : 영상 또는 시퀀스가 가지고 있는 픽셀의 좌표값을 추적하는 Tool
  
  
 1. tracker생성
 1. tracker 노드 더블클릭
 1. add track 누르고 이름설정
 1. 화면에 생긴 tracker로 트랙할 픽셀 지정
 1. 화면 상단의 재생버튼을 눌러서 트래킹 시작.
 1. tracker의 translateX와 centerX를 ctrl 누르고 Transform1로 드래그
  - 이렇게하면 자동으로 tracker와 Transform1이 연결된다.

### Keying
- 블루,그린 스크린(크로마키)을 벗겨내고, 다른 시퀀스나 영상에 합치는 작업

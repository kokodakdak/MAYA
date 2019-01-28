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

## Keying
블루,그린 스크린(크로마키)을 벗겨내고, 다른 시퀀스나 영상에 합치는 작업

### 방법1 : Hue Keyer
1. 왼쪽 아이콘 중 keyer > Hue Keyer
1. 시퀀스와 연결, viewer와 연결

&rarr; 단점: 노이즈가 낀다.

### 방법2 : IBKColour, IBKGizmo
- IBKcolour: 크로마키를 벗겨내는 계산기
- IBKgizmo: 그 계산 결과를 받아들이는 애

1. IBKcolour를 시퀀스노드, viewer노드와 연결
1. IBKcolour 더블클릭 > screentype > green
    - 블루스크린을 이용했을 경우 blue선택
1. dark의 두번째 값을 내리면 검정 영역이 넓어진다(-0.01)
1. light의 두번째 값을 올리면 하얀 영역이 넓어진다(+0.01)
1. erode 값을 올리면 검정색 영역이 하얀 영역을 침식해나간다.
1. patch black 50
1. IBKgizmo 노드 생성

    C|fg|bg
    :---:|:---:|:---:
    Colour|fore ground|back ground

    - screentype : C-green(블루스크린이면 C-blue)
1. merge노드 생성

    a|b
    :---:|:---:
    IBKGizmo|background

    - viewer랑 연결

&rarr; 단점: 배경의 잔상이 남는다</br>
해결방법 1. gizmo의 red weight과 blue/green weight을 조절한다(+ use background luminance/use bkg chroma)</br>
해결방법 2. Color correction을 이용한다</br>
해결방법 3. Hue Correction을 이용한다.</br>


해결방법 1.
gizmo의 redweight을 올리거나, blue/green weight을 낮춘다.

해결방법 2.
- Color correct노드를 더블클릭
- master의 saturation 오른쪽 동그란 컬러판 선택
- 초록색값을 내린다.

해결방법 3.
- Hue Correct노드를 더블클릭
- g_sup 그래프에서 녹색부근 그래프를 아래로 내린다




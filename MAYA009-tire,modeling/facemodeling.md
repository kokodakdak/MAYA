# 사람 얼굴 모델링 -01

* 유의사항
  - 처음 모델링 연습할 때는 서양인으로 하는 게 좋다.
  - depth차이로 인한 음영감이 있어야 모델링하기 쉽기 때문.
  
  - 사람 모델링은 front와 side가 딱 맞을 수 없기 때문에, 한 면을 포기해야 한다.
  
### create polygon tool로 모델링
  #### 눈
  1. 정면에서 눈모양 따기
    * 왠만하면 위 아래 vertex 개수가 같도록 한다
  1. side에서 봤을 때, 위치 맞추기
  1. front에서 가장자리 edge 선택, extrude
    * x축 잡고 바깥 쪽으로
  1. 가운데 면 삭제
  1. modify>center pivot
  1. front에서 점 선택 -> side에서 위치시키기 (반복)
  
  
  #### 코
  1. plane 가늘고 길게 만들어 못등에 댄다, 반으로 쪼개기
    * subdivision height 1, width 2
  1. multicut으로 edge 10개
  1. 측면에서 보면서 코 라인에 맞춘다.
  
  #### 눈코 합치기
  1. combine, delete history
  1. append polygon으로 눈앞머리와 코 연결.
  1. 눈둘레 extrude
  1. 2,3 반복
    * merge vertices, multi cut 등으로 정리
    * 눈을 중심으로 

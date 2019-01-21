# 자동차 rigging
1. 자동차 전체 컨트롤러 생성
1. 바퀴 컨트롤러 생성
    * 휠의 중앙에 오도록 v잡고 옮기기
    * rotate Z: 90
1. 휠선택, 타이어선택  P
1. 바퀴 컨트롤러 선택, 타이어 선택, CP
1. 바퀴 컨트롤러/자동차 모델링 전체 선택, 메인 컨트롤러 선택, P

## Expression
수식을 이용한 parent 관계를 만들어 주는 Tool(editor)</br>

**위치:** Windows>Animation Editors>Expression Editor</br>
**장점:** 무한으로 parent 가능, 복수로 제작이 가능, 수식으로 제어하기 때문에 범용적이다.</br>
**주의:** 부모가 항상 수식의 마지막에 들어가야 한다.</br>
**방법:** **1단계** 오브젝트 선택 &rarr; **2단계** attribute 선택 &rarr; **3단계** expression작성

### 자동차의 이동과 바퀴의 회전
##### 1,2 단계
1. 메인 컨트롤러 선택, translate Z 선택(...a)
    * selected object and attribute의 값을 기억해놔야 수식을 쓸 때 활용할 수 있으므로 메모장에 적어놓는 게 좋다.
1. 바퀴 컨트롤러 선택, rotate X 선택(...b)
    * 마찬가지로 메모장에 적어둔다.
##### 3단계
1. "타이어의 회전(b) = 자동차 바디의 이동값(a)  * 2의 배수"이라고 프로그래밍 하면 됨(expression 작성)
    * 이미 만든 expression을 수정하고 싶으면 Expression Editor>Select Filter> By Expression Name


### 핸들의 회전과 바퀴의 회전
1. 핸들 컨트롤러 만들기
1. v를 눌러서 핸들의 중간에 컨트롤러의 피봇 맞추기, rotate X: 90
   * freeze
1. 핸들 컨트롤러 누르고 ctrl + G(그룹짓기)
   * 핸들 컨트롤러를 핸들의 각도에 맞춰서 rotate 시키면 핸들의 움직임이 이상해지기 때문에 그룹에 rotate값을 주는 것.
1. 핸들 컨트롤러 그룹을 선택해서 핸들 각도에 맞춰서 rotate값을 준다.

# Cycle Animation
사람이던 동물이던 반복적으로 행동하는 것들을 Loop를 이용해서 무한 반복 시키는 Animation

* 첫 프레임의 키값이 끝 프레임의 키값과 동일
   * 1fps = 24fps일 때 1~23fps만 play
* 원하는 attribute만 key를 찍으려면 channel박스에서 원하는 attribute 드래그 후 오른쪽 버튼> key selected

## 바닥에 튀기는 공
1. plane 깔고, sphere를 만든다.
      * sphere의 피봇을 가장 아래로 옮기고(D + V) 원점에 갖다 놓는다. (X)
1. frame은 24로 설정

   frame|1|7|24
   ---|---|---|---
   sphere transY|50|0|50

1. frame 1 복사 frame 24 붙여넣기
1. 23fps로 바꾸고 재생


### 움직임 조정
Windows>Animation Editors>Graph Editor
   * 그래프 축소 확대 alt + shift + 마우스우클릭
* translate Y 선택
* break tangent를 이용해 양쪽 접선을 따로 움직이도록 한다.
* 그래프를 V모양으로 만든다

      
      
## Reference
[애니메이션의 12가지 법칙](https://cafe.naver.com/mayaedu)

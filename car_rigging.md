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

# Walking animation
## 제자리 걷기
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

## Rendering

* 깔끔하게 정리하는 거 잊지말기!
   * freeze
   * delete history
   * 이름 짓기
   * 등등
   
1. tents_con.hdr을 source image폴더에 넣는다
1. Arnorld>light>Skydome Light
1. Skydome Light 노드 선택 > Attribute Editor > color 옆 체크박스 클릭 > file클릭
   * filter type : off
   * Image Name 옆 폴더아이콘 클릭 : tents_con.hdr 불러오기
   * IBL(Image Based Light)

### Shade 입히는 법(Hyper shade)
   Arnold>Shader>aiStandartSurface
 
   1. 오브젝트 선택
   1. aiStandardSurface 우클릭> Assign material to selection(12시방향)
      * lambert가 기본값이기 때문에, 되돌리고 싶으면 위와 같은 방향으로 lambert를 적용시키면 된다
   1. attribute editor에서 세부값을 조절한다.
   
   **Base**
   color : 재질을 입히는 곳(질감이 아님)
   Diffuse Roughness : 뽀얀 느낌
   Metal ness
   
   **Specular**
   Color : 하이라이트 컬러
   Roughness : 반사값을 뭉겐다(블러처리하듯)

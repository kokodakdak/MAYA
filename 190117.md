# Rigging 02

#### 지난 시간 간략 복습
1. 오브젝트 만들고 이름짓고, parent관계 만들고, 레이어화
    * freeze, delete History
1. Joint 만들고 이름짓고, 레이어화
    * freeze, delete History
1. Controller 만들고, 위치 옮기고, 이름짓고, 레이어화
    * freeze, delete History
1. object와 Joint를 연결
    * Joint와 연결이 안되서 따라오지 않는 오브젝트는 오브젝트끼리 P로 연결한다
1. Joint와 Controller를 연결한다.
    * 이 때 까지는 컨트롤러를 움직인다고 해서 전체 오브젝트가 움직이지 않는다.
1. Controller끼리 P구조를 만든다.
    * 이제 가능
    
    
#### 집게 움직임 만들기
1. 집게 컨트롤러의 피봇을 관절위에 놓는다
    * D + V 눌러서 스냅을 이용해서 움직인다.
1. 집게 컨트롤러 선택, 집게 오브젝트 선택, Constrain Parent
1. 집게 컨트롤러를 연결된 관절 컨트롤러 밑으로 Constrain Parent

#### 마무리
1. 오브젝트, 관절, 컨트롤러 모두 메인 컨트롤러 밑으로 넣는다.


## IK
  * skeleton>create IK Handle(option)
  * reset tool을 눌러준다
  * single chain solver 선택
  * 관절의 시작 -> 끝을 각각 클릭
    * 자동적으로 연결되었기 때문에 시작 관절과 끝 관절 사이의 컨트롤러들은 필요없다.
  * IK는 회전은 불가능, 이동만 가능하다
  
 
   1. 컨트롤러 선택, IK 선택, constraint>Point &rarr; translate값만 연결된다.
   1. 컨트롤러 선택, IK 선택, constraint>Orient &rarr; rotate값만 연결된다.
      * Orient로 연결했을 때, option의 maintain offset을 선택하면 오브젝트를 기준으로 회전하게 된다.
      * 체크하지 않으면 컨트롤러나 조인트 기준으로 회전하게 된다.
    
# Animation
## Set Driven
  1. animation>key>set driven> set
      * Driver : 부모
      * Driven : 자식
  1. 부모 object 선택 Load Driver
  1. 자식 object 선택 Load Driven
  1. 부모의 노드(속성) 중 원하는 것 선택(Rotate Z)
  1. 자식의 노드(속성) 중 원하는 것 선택(Rotate Z)
  1. key 클릭 (자식 object를 선택해보면 연결된 속성에 표시가 되어있다.)
  1. 최대값 설정
      * 부모의 속성 중 Rotate Z = 40
      * 자식값의 속성 중 Rotate Z = -40
    * 연결을 끊으려면: 자식 선택> 연결된 속성 선택 > 오른쪽 버튼> Break Condition
    * 부모에게 limit 주기: 부모의 Controller 선택 > Channel Box
    
  
#### 설정
   TimeSlider>
     * playback speed: Play every frame
     * Max Playback Speed: 24fps x 1
      
  컨트롤러 선택, 프레임레이트 바를 1로 가져다놓고
  S를 누르면 키 선택, 프레임레이트 바에 빨갛게 표시된다
  
  ## 큐브 집는 집게 만들기
  1. 큐브를 만든다
      * 위치잡고, freeze
  1. create>locator 큐브위에 가져다 놓는다.
  1. locator 선택, hand 컨트롤러 선택, P
  1. locator 선택, cube 선택, CP
  ---다음주에 to be continue...---

# Rendering
## Camera

* 카메라 생성</br>
create>Cameras>Camera

* 카메라 관점에서 보기</br>
(Perspective View에서)
Panels>perspective>[Camera이름]
되돌리려면
&rarr; Panels>perspective>Persp

* 카메라 설정 시 주의사항</br>
Camera 설정할 땐 Resolution gate를 키고 작업해야 한다.

* 카메라 설정 완료 후 고정시키기</br>
Channel Box>TranslateX~Visibility 드래그>오른쪽 버튼>lock selected
풀 땐 *unlock selected

## display Render Setting
  * Render Using</br>
    Render engine을 고르는 탭.
  * Common
    결과물 파일로 뽑아낼 때 설정하는 곳
      * File Output
        * File name prefix : 파일 이름대로 이미지 파일로 아웃풋됨
        * image format : exr로 쓰는 게 좋다. 속성(채널)을 하나의 파일로 저장.
        * compression : 필요x
      * Meta data
        * Color Space : 디지털로 송출되는 컬러는 sRGB.
        * Frame/Animation ext : name.ext(Single Frame) 한장의 이미지만 뽑겠다고 설정하는 것.
            * name_#.ext를 추천
            * **name** file name prefix에서 설정한 것.
            * **#** frame 넘버
            * **ext** 확장자 자리
        * Frame padding : frame 넘버 자릿수
      * Frame Range
        * By frame : frame을 n장씩 렌더링하겠다. ex)0.5 -> 한프레임을 두 장으로 렌더링
      * Renderable Cameras
        * Renderable Camera : 내가 만든 camera로 설정
      * Image Size
        * Presets : 사이즈(영화만들 땐 꼭 HD_1080) 
      
  * Arnold renderer
  * System
  * AOVs
  * Diagnostics
Windows>setting/preference>Plug-in Manager>mtoa.mll


Render Using: Render engine
2018년 부터는 Arnold Renderer가 탑재. 기본 Render engine으로 사용되고 있다.
ex) V-ray, mental-ray, Render man
Arnold의 장점: real time으로 결과를 확인할 수 있다.
단점: 무겁다
                      


Frame Range
 

Renderable Cameras(**중요**)


Image size
Presets: 사이즈
영화만들 땐 꼭 HD_1080
애니메이션 등은 720으로 해도 상관없음

Resolution
많아야 100-150 너무 많아지면 렌더링이 오래걸린다.
많이해야 하는 게 아니면 72에 두고 쓴다


Arnold Renderer

Camera ~ Volume Indirect &raar;각 속성의 퀄리티 제어부(보통 회사에서 세팅값을 알려준다)
Camera(AA = )
Specular 반사
Transmission투명도
SSS내부산란
renderer에서 shader나 light를 건드리고도 노이즈가 안없어질 때 이 부분을 건드린다

Filter
type catrom


Raydepth
빛의 추적 계산량 조절
GI 조절

Raytrace
빛의 추적
빛이 반사되어 어디에 부딪히는지 추적
GI를 켜놓고 작업해야 한다(Global Illumination, 전역 조명)
요즘 나오는 건 자동으로 켜진다.

Environment
  Atmosphere: 씬 자체에 이미지를 얻는것.
  
 Motion Blur
  Enable을 체크하면 모션블러간 일어나게 만들 수 있다.
  
System

AOVs
한장의 이미지에서 속성을 따로 분리하는 탭

Dianosti

Create>Lights>
Arnold>Lights>

Mesh Light
area light:네모 판떼기 라이트

ctrl+A
intensity
exposure intensity의 n제곱

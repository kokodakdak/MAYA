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

#### Arnold 안보일 때
Windows>setting/preference>Plug-in Manager>mtoa.mll

## display Render Setting
  * Render Using</br>
    Render engine을 고르는 탭.
    2018년 부터는 Arnold Renderer가 탑재. 기본 Render engine으로 사용되고 있다.
    ex) V-ray, mental-ray, Render man
    Arnold의 장점: real time으로 결과를 확인할 수 있다.
    단점: 무겁다
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
        * Presets : 사이즈(영화만들 땐 꼭 HD_1080, 애니메이션은 720)
        * Resolution : 많아야 100-150 너무 많아지면 렌더링이 오래걸린다. 보통 72에 두고 쓴다
      
  * Arnold renderer
    * Sampling
    각 속성의 퀄리티 제어부(보통 회사에서 세팅값을 알려준다)
    할 만큼 다하고도 노이즈가 해결되지 않을때 이 부분을 건드린다.
      * Camera(AA = Anti Aliasing)
      * Specular : 반사
      * Transmission : 투명도
      * SSS 내부산란    
    * Filter
      * type : catrom
    * Ray Depth
    빛의 추적(Ray trace) 계산량 조절
    GI 조절
      * Raytrace
        빛의 추적
        빛이 반사되어 어디에 부딪히는지 추적
        GI를 켜놓고 작업해야 한다(Global Illumination, 전역 조명)
        요즘 나오는 건 자동으로 켜진다.
     * Environment
        * Atmosphere : 씬 자체에 이미지를 얻는 것
     * Motion Blur
        * Enable을 체크하면 모션블러가 일어나게 만들 수 있다
  * System
  * AOVs
    한장의 이미지에서 속성을 따로 분리하는 탭
  * Diagnostics

Create>Lights>
Arnold>Lights>

Mesh Light
area light:네모 판떼기 라이트

ctrl+A
intensity
exposure intensity의 n제곱
Temperature: 조명의 온도
Light space: 조명의 모양
Light를 피사체에 가까이 두지 않는 게 거리 사관

7번 버튼: 빛을 확인
원래대로 5번
거리 상간없이 똑같이 적용. 씬 전체의 밝기를 조절하는 조명
빛이 은은하지 않아서 그림자가 선명하다
Attribute Editor의 Arnold탭으로 조절


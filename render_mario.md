# Mario Rendering

1. 0frame에 키찍고, 120frame에서 rotateY 20 키찍고
1. 옷선택>우클릭>Assign New material>Arnold>shader>aiStandardSurface
1. 받침 선택>우클릭>Assign New material>Arnold>shader>aiStandardSurface
## 플라스틱 재질 느낌 내기(마리오 옷)
  - Base>color
  - specular(반사)>Roughness 값을 올린다(0.35)
  - Geometry>Bump mapping에 약간 오돌도돌한 느낌을 내는 map을 넣는다.
  - specular>IOR(Index Of Reflaction, 굴절률)
  
    |0| |1|
    |:--------:|:--:|:--------:|
    |불투명| ...|완벽한 투명|
    
  - Anisotropy(이방성)
같은 재질이라도 다른 각도로 빛을 받게 되면 다른 재질처럼 보인다.

## 유리재질 느낌 내기(마리오 받침)
  - 유리재질 느낌내기
    - Transmission>weight
  
    |0|---|1|
    |:--------:|:--:|:--------:|
    |불투명|...|투명|
    
  - 스테인레스 느낌내기
    - Base>Metalness
    - Coat>weight
   
## 렌더링 제대로 되는지 확인하는 법
> 1. script editor 확인
> 2. set project해서 생긴 images폴더안에 파일이 생성되는지 보기

1. Rendering모드로 바꾸기
1. Render>Batch Render클릭 &raar; Script Editor에 렌더링과정이 뜬다

**취소하고 싶으면**
- esc 눌러도 소용없음
- Render>Cancel Batch Render
    - 만약 21프레임 지 render하고 끊겼다면 다음에 render할 때 render setting에서 22프레임부터 rendering


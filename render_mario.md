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
  - 

Anisotropy(이방성)
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
   

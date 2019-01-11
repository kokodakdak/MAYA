# MAYA 008 - 타이어 만들기

#### 타이어 형태만들기

1. 실린더 타이어 모양으로
1. 양쪽 엣지 잡고 bevel(segment 6)
1. 양쪽 면 FACE로 선택 후 soft selection 적용(단축키 'B')
   1. B버튼 누른채로 마우스를 좌우로 드래그해서 soft selection의 범위를 조절한다.(타이어 크기 정도로)
   1. 스케일 툴로 전체적인 크기를 줄인다(선택된 면이 안으로 약간 들어온다)
1. 선택했던 양쪽 면을 삭제
1. top view에서 multi cut으로 가운데에 edge 추가
1. 추가한 edge 선택 후 bevel(segment 2) -> 정확히 3등분 할 수 있다.
1. 가운데 vertex선택 후 soft selection -> scale tool로 약간 키워서 가운데가 살짝 올라오게 만든다.


#### soft selection
|노란색<----------->보라색|
|----------------|
|영향력 강<----------->영향력 약|



#### Modeling으로 타이어 무늬(마크) 만들기

* 패턴을 찾아서 반복시키는 게 핵심 -> duplicate special 사용




#### Bump Map으로 타이어 무늬 만들기
* Image(Texture): 3D 이미지에 입히는 이미지
* Image(Texture)를 이용해서 모델링 효과를 볼 수 있는 맵
* Grayscale(W-B)로 되어있으며, W일 수록 위로, B일 수로 아래로. 그림자가 떨어진다.
* 모델링을 왜곡 시키지 않고, 빛이 들어갔을 때 음영을 이용해서 모델링 효과를 만들어준다.




##### Texture
* 3D Modeling 또는 3D툴에 사용되는 Image
* 정사각형 이미지로 되어 있다.
* size(Pixel)
   * 256*256
   * 512*512
   * 1024(1K)
   * 2048(2K)
   * 4896(3K)
   * 8K, 16K, 32K
   
   영화업계: 1K~3K
   게임업계 245*256 ~ 1K or 2K
   
##### 재질
* 질감 표현은 없지만 눈에 보이는 무늬



##### UV(3D 오브젝트의 도면)
* 패키지디자인과 같은 느낌
* 마야 안의 포토샵같은 역할로 도면을 수정한다.
* plane 선택 후 UV>UV editor를 선택
* 두 창을 모두 띄워놓고 작업하는 것이 좋다(듀얼모니터를 추천)
* 좌표가 U축과 V축으로 이루어져 있음(world 도면에서 이미 x,y축을 사용했기 때문)
* 도면을 한꺼번에 올려놓고 작업하는 것 => multi UV
* 


##### Texture 입히기
1. 구글링을 통해 이미지 찾아서 저장(검색 키워드:ground bump texture)
   * 정사각형 이미지로 찾기(만들어둔 plane이 정사각형이니까)
1. 만들어둔 플레인 오른쪽 버튼으로 길게 눌러서>Assign Favorite Material>Blinn
1. _ 옆 체커박스 > file 선택 > bump노드로 넘어감
1. bump value 옆 버튼을 눌러서 file 노드로 넘어감
1. filter type: off, ImageName옆 폴더버튼을 눌러서 미리 저장해둔 사진을 불러옴
   * 적용된 모습이 안보이면 6번버튼(texture mode)
1. 제목 옆 버튼을 누르면 다시 bump 노드로 넘어갈 수 있음
1. bump노드에서 bump depth를 조절
   * file노드가 바로 object에 연결되는 게 아니라, bump노드가 object노드에 연결되고, file노드가 bump노드에 연결됨.

##### Texture mapping 하는 법
1. 포토샵으로 bump map만들기(아래 bump map만들기 참고)
1. 오브젝트를 선택해서 Assign Favorite Material>Blinn
1. color mapping
   1. color 옆 체커박스 클릭
   1. Filter type: off
      Image Name 옆 폴더아이콘 클릭>file>color mapping할 파일 선택
1. bump mapping
   1. bump mapping 옆 체커박스 클릭
   1. Filter Type: off
      Image Name 옆 폴더아이콘 클릭>file>포토샵으로 만들어둔 bump map 파일 선택


##### bump map만들기
* 구글링을 통해 이미지 찾아서 저장(검색 키워드: asphalt tile texture)
* 포토샵에서 불러옴
* ctrl+shift+U 흑백으로 바뀜
* ctrl + L Level값을 조절하는 창이 나옴
* 다른 이름으로 저장(ctrl + shift + S), Quality는 Maximum으로



##### Texture 확장자
* 절대 압축된 확장자(ex. jpg)를 사용하면 안된다!
* 사용가능한 확장자: TGA(Targa), BMP, PNG, EXR, Tiff, iff, sgi(얘는 old함)

* 참고 툴:
   * substance painter
      3D object 위에 리얼타임으로 texture를 입히는 것
   * substance designner
      노드를 이용해서 작업
   

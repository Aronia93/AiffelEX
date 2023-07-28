# AIFFEL GoingDeeper
----  
## **Code Peer Review**
------------------
- 코더 : 정연준
- 리뷰어 : 이성주

## **PRT(PeerReviewTemplate)**  
------------------  
- [x] **1. 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?**

|평가문항|상세기준|완료평가|
|-------|--------|---------|
|1. 잠재적 표현의 변화가 모델 출력에 미치는 영향을 관찰하였는가?|텍스트 프롬프트 2 개를 설정하고 LDM 에 넣어 이미지를 생성한 후, 생성 이미지 안에서 점차 변화되는 특성들에 대한 분석 결과를 기록하였다.|![image](https://github.com/Aronia93/AiffelEX/blob/master/GD27/doggo-and-fruit-5.gif) 분석결과를 이미지로 보여줬습니다. |
|2. Stable diffusion 모델의 dreambooth 미세조정을 실습하였는가?|미세조정에 사용할 대상의 모습이 담긴 Instance 와 class 이미지를 각각 마련하여 알맞은 경로에 저장하고, 데이터를 모델을 학습시켜 대상이 담긴 이미지를 생성하였다.|![image](https://github.com/Aronia93/AiffelEX/assets/29011595/fa012abb-984d-46a3-ab14-1e2c304dfe25) 아직 학습 진행중 입니다.|
|3. 나만의 취향이 담긴 생성 이미지를 만들어보았는가?|웹사이트에서 원하는 Checkpoint 와 Lora 파일을 다운로드하고, 생성 모델 파이프라인을 구축하여 이미지를 생성하였다.|학습이 진행중이라 진행을 못한것 같습니다..|

- [x] **2. 주석을 보고 작성자의 코드가 이해되었나요?**
      
 ```python
# Enable mixed precision
# (only do this if you have a recent NVIDIA GPU)
keras.mixed_precision.set_global_policy("mixed_float16")

# Instantiate the Stable Diffusion model
model = keras_cv.models.StableDiffusion(jit_compile=True)
 ```
 > 주석을 보고 코드이해가 잘되었습니다.

- [x] **3. 코드가 에러를 유발할 가능성이 있나요?**
      
 > 없습니다.

- [x] **4. 코드 작성자가 코드를 제대로 이해하고 작성했나요?**  

 > 이번 노드는 시간이 부족한것 같았습니다.

- [x] **5. 코드가 간결한가요?**
      
 ```python
def export_as_gif(filename, images, frames_per_second=10, rubber_band=False):
    if rubber_band:
        images += images[2:-1][::-1]
    images[0].save(
        filename,
        save_all=True,
        append_images=images[1:],
        duration=1000 // frames_per_second,
        loop=0,
    )


export_as_gif(
    "doggo-and-fruit-5.gif",
    [Image.fromarray(img) for img in images],
    frames_per_second=2,
    rubber_band=True,
)
 ```
 > 함수화로 코드를 간결하게 작성하였습니다.

## **참고링크 및 코드 개선 여부**  
------------------  
- 
    


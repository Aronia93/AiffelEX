## Code Peer Review Template
---
* 코더 : 정연준
* 리뷰어 : 김창완


PRT(PeerReviewTemplate)
---
- [x] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?  
    - 잘 동작했고 과정 전체도 전부 이해 가능했습니다
    ![5d7c13f3-336c-40a0-bffe-4f5c96fdd58e](https://github.com/Aronia93/AiffelEX/assets/36715224/e6da030e-da4b-4f5d-823a-622eefe60853)
- [x] 주석을 보고 작성자의 코드가 이해되었나요?  
    - 주석도 전부 달려 있어서 이해하기 편했습니다
```python
sticker_area = img_show[refined_y:refined_y+img_sticker.shape[0], 
                        # 기준좌표 + 스티커 너비
                        refined_x:refined_x+img_sticker.shape[1]]
                         # 기준좌표 + 스티커 높이
    
                        
# np.where는 조건에 해당하는 인덱스만 찾아서 값을 적용하는 방법이다.

img_show[refined_y:refined_y +img_sticker.shape[0], 
         refined_x:refined_x+img_sticker.shape[1]]  =\
    np.where(img_sticker!=0,sticker_area,img_sticker).astype(np.uint8)
# img_sticker!=0 : 이미지에서 색 없는 부분만 사용(검정부분)
# np.where(조건,조건충족시 출력내용, 충족하지 않을때 출력내용)
plt.imshow(img_show)
plt.show()
```
- [x] 코드가 에러를 유발할 가능성이 있나요?  
    - 코드에서 에러를 유발할 가능성은 보지 못했습니다
- [x] 코드 작성자가 코드를 제대로 이해하고 작성했나요? (직접 인터뷰해보기)  
    - 직접 얘기해봤는데 전부 이해하고 짜셨습니다. 둘다 문제 해결은 했으나 다른 방법으로 코드를 풀어서 더 흥미로웠습니다
```python
sticker_area = img_show[refined_y:refined_y+img_sticker.shape[0], 
                        # 기준좌표 + 스티커 너비
                        refined_x:refined_x+img_sticker.shape[1]]
                         # 기준좌표 + 스티커 높이
    
                        
# np.where는 조건에 해당하는 인덱스만 찾아서 값을 적용하는 방법이다.

img_show[refined_y:refined_y +img_sticker.shape[0], 
         refined_x:refined_x+img_sticker.shape[1]]  =\
    np.where(img_sticker!=0,sticker_area,img_sticker).astype(np.uint8)
```
여기 보면 img_sticker!=0으로 조건 설정 하셨는데 저는 이부분을 img_sticker > 127 이렇게 처리했습니다
- [x] 코드가 간결한가요?  
    - 딱히 제 실력으로 나열된 코드를 더 줄일 수 있을만한건 보지 못했습니다  
    - 다만 작성자와 리뷰어 둘다 마찬가지로 긴 코드를 함수화해 더욱 간략화한 코드를 작성할 수 있지 않을까 기대해봅니다.

아쉬웠던점은 addweight method가 쓰이지 않았다는것과 함수를 이용해 간략화를 했다면 더욱 이쁜 코드가 되지 않을까 정도 입니다. 이점은 저도 고쳐야 합니다...

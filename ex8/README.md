## Code Peer Review Template
---
* 코더 : 정연준
* 리뷰어 : 이동익 


## PRT(PeerReviewTemplate)
---
[0] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
  - 세가지 모델 lstm, cnn, maxpooling을 이용하여 성능을 테스트하고, 한글 word2vec을 이용하여 성능개선이 이루어졌습니다.

[0] 주석을 보고 작성자의 코드가 이해되었나요?
  - 세부 기능별로 잘 이해되었습니다.
  
[0] 코드가 에러를 유발할 가능성이 있나요?
  - 에러는 아니지만, epoch이 늘어남에 따라 과적합가능성이 있어, test accuracy가 낮아질 수 있습니다.

<pre>
<code>

model2.compile(optimizer='adam',
              loss='binary_crossentropy',
              metrics=['accuracy'])


history2 = model2.fit(x_train,
                    y_train,
                    epochs=epochs,
                    batch_size=512,
                    validation_data=(x_val, y_val),
                    verbose=1)

</code>
</pre>
 
 
[0] 코드 작성자가 코드를 제대로 이해하고 작성했나요? (직접 인터뷰해보기)
  - 네, 임베딩 벡터의 구조 및 모델링에 대해 인터뷰 진행하였습니다.
  
[0] 코드가 간결한가요?
  - 대체적으로 간결한 것 같습니다.


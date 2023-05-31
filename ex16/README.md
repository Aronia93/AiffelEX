## Code Peer Review Template
---
* 코더 : 정연준    
* 리뷰어 : 임지혜


## PRT(PeerReviewTemplate)
---
- [O] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
```python
"""
-> 정상 작동 & test data를 따로 만들어 결과를 확인

10 에포크일떄는 만들어진 답변과 실제 답변간에 차이가 있다
30 에포크 이상부터는 만들어진 답변과 실제 답변간에 차이가 거의 없음을 알 수 있다
50 에포크에서는 두번째 질문의 온점도 일치하는 결과를 보였다
""
```
- [O] 주석을 보고 작성자의 코드가 이해되었나요?
```python
# 하이퍼파라미터의 주석을 제공해 이해가 쉬움 !!!!
NUM_LAYERS = 2 # 인코더와 디코더의 층의 개수
D_MODEL = 256 # 인코더와 디코더 내부의 입, 출력의 고정 차원
NUM_HEADS = 8 # 멀티 헤드 어텐션에서의 헤드 수 
UNITS = 512 # 피드 포워드 신경망의 은닉층의 크기
DROPOUT = 0.1 # 드롭아웃의 비율
```

- [X] 코드가 에러를 유발할 가능성이 있나요?
```python
# 없는 것 같습니다, 테스트 결과가 무난하게 나오는것 같음 
```
- [O] 코드 작성자가 코드를 제대로 이해하고 작성했나요? (직접 인터뷰해보기)
```python
# 하이퍼파라미터 셋팅, 레이어 수, loss에 대해 토론
```
- [O] 코드가 간결한가요?
```python
#data를 로드하고 전처리 하는 과정을 간결하게 정리
def load_conversations(data):
    Q, A = [],[]
    for text_q in data["Q"]:
        Q.append(preprocess_sentence(text_q))
    for text_a in data["A"]:
        A.append(preprocess_sentence(text_a))
    Label = data["label"]
    return Q, A, Label

"""
모델 테스트 결과를 확인해보기 위해 테스트 데이터를 분리하고, 
질문, 예측답변, 실제답변을 직관적으로 비교할 수 있는 코드 작성
"""
for i in range(10000,10005):
    sentence_generation(data.loc[i,"Q"])
    print("실제 답변 :",data.loc[i,"A"],"\n")
```


<div align="center">
  <h1> 문서 유사도 계산 (STS) project </h1>
  한국어 문장의 유사도 분석 모델 훈련 및 서비스화
 
  
</div> 

  ### 프로젝트 목표 
  - 의미적 텍스트 유사도(Semantic Textual Similarity)는 두 문장 사이의 의미적 동등성의 정도를 측정하는 것입니다. 
    학습 데이터 셋을 사용하여, 의미적 텍스트 유사도 모델을 훈련하는 것을 목표로 합니다.
  - 두 개의 한국어 문장을 입력받아 두 문장의 의미적 유사도를 출력하는 모델 생성
  <br>
  
  
  
  
  ###
  1. 전처리 - roberta-base tokenizer를 사용하여 모델 입력으로 만들어 주는 전처리 함수를 만들어 길이를 맞춰서 토큰화하였다.
  2. 파인튜닝 - 허깅페이스에 있는 klue roberta 로드하였고, f1과 pearson metric를 불러와 매트릭 함수를 정의하여 전처리된 데이터를 훈련시켰다.
  3. 하이퍼 파라미터 튜닝 - grid search , optuna 사용
  4. API 구현 - flask 사용
  <img width="600" src="https://lh4.googleusercontent.com/dLTipoDGwhOpP7slPCb1qEbTOeq40j6qFqYX5k7lYmur3HXQr3iNIYWC_Hqt6yWSVXIv1-zTH4vHjHmPat9ErIW2FMgGAoKB9iSmbo8CWQoVaek5gwpmL-HjzPTHGTAX6Zw8IA7P">   
  <br>


  

  ## 최종 결과 분석 및 회고

  - 학습 결과를 보고 초기에는 배치 사이즈를 크게 설정하는게 좋을 거라 예상 했지만 오히려 작게 설정했을때 일반화가 잘되었다. 
  - epoch이 크지않고 adamw을 사용하여 scheduler의 역할이 별로 크지않을 거라 예상 했지만 scheduler를 사용한 결과가 더 좋았다. 
  - 추후에 디커플드 웨이트 디케이 정규화 논문 확인 결과 아담과 아담 더블유의 경우에도 스케쥴러 사용이 유의미하다는 것을 확인하여 이런 결과가 나왔다고 생각합니다.

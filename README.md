
<div align="center">
  <h1> 문서 유사도 계산 (STS) project </h1>
  한국어 문장의 유사도 분석 모델 훈련 및 서비스화
 
  
</div> 

  ### 프로젝트 배경
  - 기업에서는 두개의 문장을 입력받아 의미적 유사도를 측정 할 수 있는 서비스를 개발해야한다
  - 주어진 data로만 학습을 해야하며 실제 사용할 수 있는 api가 구현 되어야한다
  <br>
  
  
  
  
  ###
  1. 전처리 - roberta-base tokenizer를 사용하여 모델 입력으로 만들어 주는 전처리 함수를 만들어 길이를 맞춰서 토큰화하였다.
  2. 파인튜닝 - 허깅페이스에 있는 klue roberta 로드하였고, f1과 pearson metric를 불러와 매트릭 함수를 정의하여 전처리된 데이터를 훈련시켰다.
  3. 하이퍼 파라미터 튜닝 - grid search , optuna 사용
  4. API 구현 - flask 사용
  <img width="600" src="https://lh4.googleusercontent.com/dLTipoDGwhOpP7slPCb1qEbTOeq40j6qFqYX5k7lYmur3HXQr3iNIYWC_Hqt6yWSVXIv1-zTH4vHjHmPat9ErIW2FMgGAoKB9iSmbo8CWQoVaek5gwpmL-HjzPTHGTAX6Zw8IA7P">   
  <br>


  

  ## 프로젝트 결과
  - 문장 유사도를 측정 할 수 있는 모델 구현(Klue/roberta base)
  - STS task를 직접 사용 할 수 있는 api( flask) 구현
  - f1: 0.87 , pearsonr: 0.88 의 결과를 갖는 모델
  <br>
  
  ## 프로젝트 내 나의 기여
  - 모델의 input에 맞게 데이터를 전처리 및 토큰화
  - 하이퍼 파라미터 튜닝



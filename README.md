# 2021 Bigcontest 퓨처스리그 홍수 Zero 부문
## 1. 개요
주제: 댐 유입 수량 예측을 통한 최적의 수량 예측 모형 도출 </br>
기간: 2021.07 ~ 2021.09 </br>
팀원: 김권호, 김시현, 조형래, 황재원 </br>
사용 skill: Python </br>
<img width="1219" alt="image" src="https://user-images.githubusercontent.com/79994991/166149676-568f47b2-bae8-482f-913d-37fe83ad03cf.png">

## 2. 사용 데이터 및 전처리 
- 6개의 집단으로 나뉜 홍수사상 데이터 (time series) 
- 데이터 특징에 따라 데이터 집단을 date 별로 그룹화한 후, log transformation 진행
- MA, EWMA, Lag, 기술 통계량 등 시계열 특성을 반영해줄 수 있는 변수 추가 
- 통계적 지식을 활용한 EDA를 통해 다양한 파생 변수 추가 
<img width="1121" alt="image" src="https://user-images.githubusercontent.com/79994991/166149967-ab5ec4f2-bcc6-40b5-bf0a-9f1f8cb6c07c.png">

## 3. Modeling
- 블랙박스 모델과 화이트박스 모델 stacking
<img width="1008" alt="image" src="https://user-images.githubusercontent.com/79994991/166149954-8613f4e3-3b76-410e-9f94-84571e751adf.png">
- stacking : simple average

## 4. Result
### 4-1) 모델별 예측 결과
<img width="1212" alt="image" src="https://user-images.githubusercontent.com/79994991/166150038-620cbc4b-fea2-49cf-afbc-d09fcae37315.png">

### 4-2) stacking 전 최종 예측 결과 
<img width="1199" alt="image" src="https://user-images.githubusercontent.com/79994991/166150067-c39896bf-8475-4582-92ee-198812bbfc73.png">

### 4-3) stacking 적용 최종 예측 결과 
<img width="1206" alt="image" src="https://user-images.githubusercontent.com/79994991/166150109-c2aacf00-e3bf-4081-ba1c-ca77a7c78a2c.png">

## 5. 분석 의의
1. 통계적 지식을 활용하여 주어진 변수들을 충분히 활용하고자 함. 수위 D변수의 AV plot을 확인한 점,  MA와 EWMA  변수의 window size를 PACF plot을 통해 결정한 점 등 통계적 근거를 활용하고자 하였음. 
2. 충분한 EDA를 통해 다양한 파생 변수를 생성. EDA를 통해 index 변수와 다양한 통계량들을 추가하여 분석에 설득력을 높이고자 함. 
3. 다양한 모델을 활용하여 오버피팅을 방지하고 안정적인 결과를 얻을 수 있는 예측 모델 생성. 다양한 모델을 사용했지만 모델의 해석까지 고려할 수 있도록 하였음 (feature importance 확인 등)
4. 시계열 모델을 적용하지 않았지만 lag, ma 등 이전 시점을 고려한 변수를 충분히 활용하여 실제 이용이 가능하도록 하였음. 


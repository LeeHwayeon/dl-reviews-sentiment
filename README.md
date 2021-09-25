# 에어비앤비 텍스트 리뷰 감성 분석 🏠
## 💡 Abstract 
본 프로젝트는 런던에 위치한 에어비앤비 숙소의 텍스트 리뷰를 사용해 긍정, 부정 감정을 분석하는 모델을 생성한다.
텍스트 리뷰는 자연어 처리 과정을 거치고 RNN, LSTM, CNN 및 다양한 Hyper parameter를 적절히 사용해 비교하며 예측 정확도가 가장 높은 모델을 생성하고자 한다.
## 💡 데이터 선정
[kaggel “London Airbnb Data”](https://www.kaggle.com/labdmitriy/airbnb?select=reviews.csv)
> statista의 통계에 따라 에어비앤비 도시 중 숙소가 가장 많은 도시는 London
## 💡 데이터 전처리
1. 다양한 언어의 리뷰 존재 => 영어 이외의 문자를 제거, 소문자 변환
2. Vader 어휘사전을 이용해 긍정, 부정 매핑
3. Nltk 라이브러리 => 어간 추출, 표제어 추출, 불용어 제거
4. 단어 집합 생성 후 정수 인코딩 및 리뷰 데이터 길이 동일
## 💡 모델 구성 및 test 데이터 정확도 평가
1. 첫 번째 모델
<img width="60%" alt="스크린샷 2021-09-25 오후 6 11 21" src="https://user-images.githubusercontent.com/33210124/134766209-067ca188-8ebd-48fb-b027-d182d60d8aba.png">
2. 두 번째 모델 : : LSTM
<img width="60%" alt="스크린샷 2021-09-25 오후 6 12 57" src="https://user-images.githubusercontent.com/33210124/134766252-1a1dbbf2-0446-4d42-a725-e192111bee3f.png">
3. 세 번째 모델 : : CNN
<img width="60%" alt="스크린샷 2021-09-25 오후 6 13 34" src="https://user-images.githubusercontent.com/33210124/134766273-bc32ee82-1fea-4280-a2c7-d767559ae032.png">
4. 네 번째 모델 : : LSTM+CNN
<img width="60%" alt="스크린샷 2021-09-25 오후 6 14 02" src="https://user-images.githubusercontent.com/33210124/134766294-33d900dd-f056-48ac-b180-10fa9c7b2f8b.png">    

## 💡 결론 및 한계
1. 생성한 4개의 모델로 평가한 test 데이터 정확도는 큰 차이 없다.
2. 정확도가 가장 높고, Loss가 가장 낮은 모델 : LSTM 단일 모델.
3. 사용자가 느낀 감정을 텍스트로 전부 표현하기에는 어려움이 있음.

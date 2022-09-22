weather_UV_Prediction_Model
- 2022-1 project (2022_weather_contest)
- 2022년 기상청 날씨 빅데이터 콘테스트 공모적
 
 
# 1차 과제 - 기상위성 자료를 활용한 여름철 자외선 산출기술 개발
- 제공 데이터: 기상 데이터(자외선지수, band1~16(각 변수에 대한 설명은 생략), 지면타입, solarza, sateza, esr, 지역 번호, 위치 정보(위도와 경도) 등)
- 추가 수집 데이터: 추가 기상 데이터(습도, 강수량, 기온, 풍속, 풍향)
- 추가 수집 데이터의 경우, 제공 데이터 내 위도 및 경도 정보에 부합하는 지역 내 행정구역에 대한 기상 데이터로 수집 (해당 행정구역 정보가 없는 경우, 근접한 행정구역의 정보로 대체)

- 데이터 제공 형태: .csv

- 데이터 형태: 제공 데이터의 경우, 일별/시간대별 정보 제공 & 추가 수집 데이터의 경우, 특정 지역 내 일별/시간대별 기상 수치 제공

- 데이터 활용: 여름철 자외선 산출기술 개발이라는 공모전의 목적에 맞추어, 여름철에 최적화된 모델을 개발하기 위해 학습 데이터로 06 ~ 08월 데이터를 선정 
              & 자외선과 높은 연관성이 있는 오존전량이 한 계절 간 차이가 존재한다는 기존 연구 결과를 참고하여 3~5월 데이터를 학습 데이터로 추가 선정

- 학습기간: 2020년/2021년 03 ~ 08월, 검증기간: 2022년 6월
- 종속변수(예측값): uv (자외선지수)
- 독립변수: 그 외 27개 변수
- 활용 모델: XGBoost, LightGBM, Random Forest Regression)

- 검증 방법: RMSE (모델 정확도, 실제 검증값 대비 정확도)
- 분석 프로세스
 
 
# 결과
[사용 파라미터]


- 마감 결과 (기준 오후 6시): RMSE 기준 최종 8위 (총 19팀 참여)
 
 
# 문제점 및 아쉬운 점
- 제공 데이터의 경우, 각 변수별로 나타내는 수치의 의미 및 범위에 대한 정보가 부재하였음, 이는 모델 개발까지만 진행하는 공모전의 특성상 큰 문제가 되지 않았으나, 변수에 대한 명확한 설명 및 정보가 있다면 추가 변수 수집에 도움이 되었을 것
- 추가 수집 데이터의 경우, 데이터를 제공받는 형식이 지역별, 월별로 따로 제공되며 각 파일별로 데이터 타입이 달라, 결합 시 예상 외로 많은 시간이 소요됨


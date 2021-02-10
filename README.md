# 서울시 구별 '공원면적' 및 '범죄율' 데이터를 통한 공원면적과 범죄율의 상관관계 탐색
##### ※ 가제이며, 추후 소스 데이터 변동에 따라 제목 수정 가능

## Member / Role
* 임현수 / 범죄데이터 전처리 및 탐색
* 정다은 / 공원면적 등 기타요소 데이터 전처리 및 상관성 탐색

## 조사 동기
* 지난 강의의 '강남 3구 (강남구, 서초구, 송파구)가 범죄에 대해 안전하지 않다'는 분석 결과에 의문을 가지고, 분석 과정 중 구별 인구 수에 따른 조정이 필요할 것이라고 판단하였음
* 범죄발생과 유의한 상관성을 보이는 요소가 있다면, 현재 혹은 미래에 그와 성격이 유사할 것으로 예상되는 지역의 치안 발전에 기여할 수 있을 것이라고 기대함

## 소개
* 5대 범죄 발생률이 높은 구를 파악하고, 범죄(전체 혹은 종류별) 발생과 유의한 상관성을 보이는 요소를 찾고자 함
* 서울시 구별 범죄율 데이터 및 서울시 구별 공원면적 데이터 간 상관관계를 도출할 예정임
* 현재는 독립변수 데이터로 '공원면적'만을 선정하였으나, 다양한 데이터셋으로 분석범위를 확대하며 유의한 독립변수를 지속 발굴 예정
* 유의한 상관관계를 보이는 요소 발견 시, 계절별/월별/요일별/시간대별 범죄 데이터에까지 확장 적용하여 치안 관련 리소스가 더/덜 필요한 때를 분류, 효율적인 자원 운영에 기여할 수 있을 것으로 기대됨
* 서울시 구별 범죄율을 다각도에서 분석하여 안전한 치안의 지표와 효과적인 도시계획의 근거를 탐색 예정

## 목적 (Objectives)
* 5대 범죄 각각에 대해 특이점(상위, 하위)을 보이는 구 파악
* 범죄 발생률과 유의한 상관관계를 보이는 요소 및 정도 파악

## 목표 (Goal)
* 과거 데이터를 분석하여 이를 바탕으로 미래 예측을 통해 서울시 각 자치구의 한정된 리소스를 5대 범죄 죄종마다 어느 수준으로 분배할지 판단하는 데 기여하고, 효율적인 리소스 분배 및 합리적인 인력 충원의 근거로써 활용


## 결과 (Result)
### 1. 범죄데이터 탐색
* 강남 3구가 비록 절대건수는 상~중위권에 속하나, 인구 대비 범죄발생건수의 비율을 보았을 때에는 주민등록/유동 인구 무관하게 중하위권에 위치함
   → 강남 3구의 높은 절대건수는 범죄발생률보다는 높은 인구수가 주요한 원인으로, 타 지역구 대비 위험하다고 보기 어렵다고 판단됨

* 살인의 경우, 절대건수 및 발생률 모두에서 영등포가 1~2위 권으로 매우 높은 수준을 보임
* 강도 및 강간강제추행의 경우, '강북구, 관악구, 금천구'가 범죄 발생률이 높게 나타남 (유동인구 수 대비 기준)
* 절도 및 폭력의 경우, 위 3구(강북구, 관악구, 금천구) 및 중랑구에서 범죄 발생률이 높게 나타남 (유동인구 수 대비 기준)

![image](https://user-images.githubusercontent.com/78459305/107248906-20912380-6a76-11eb-86d4-4c0d32b5f123.png)

### 2. 범죄발생과 유의한 상관성을 보이는 요소 탐색

* [주민등록인구와 유동인구의 5대 범죄 총발생건수와의 상관관계 비교]
   * 각각 0.51과 0.79의 양의 상관관계가 나타남. 더 높은 상관관계를 가지는 유동인구를 기준으로, 범죄 데이터와 다양한 데이터셋을 통해 상관관계 탐색 예정

![image](https://user-images.githubusercontent.com/75604413/107478433-cea6e580-6bbc-11eb-9560-2baa7a413ed1.png)

* [총유동인구 1000명 대비 총범죄율과 생활권공원면적 상관관계 비교]
   * -0.49의 음의 상관관계 도출. 생활권공원면적이 늘어날수록 총범죄율이 줄어드는 것을 확인.
   
   ![image](https://user-images.githubusercontent.com/75604413/107478218-72dc5c80-6bbc-11eb-82ad-8039f31cddc2.png)

* [유동인구와 지구대/파출소 수의 상관관계 비교]

## 진행 과정
### 1. 범죄데이터 탐색
* 데이터 대상기간은 2018년이며, 데이터는 아래 3가지를 활용하였음
  * 구별 범죄발생 및 검거수: 서울시 구별 5개 범죄에 대한 범죄발생건수 및 검거수
  * 구별 주민등록인구수: 서울시 구별 세대수 및 성별, 내/외국인별 주민등록인구수
  * 구별 유동인구수: 서울시 구별 총 유동인구수


### 2. 범죄발생률과 유의한 상관성을 보이는 요소 탐색
* 대상 데이터는 2018년 서울특별시 기준
   * 구별 5대 범죄 :  구별 5대 범죄 총 발생건수
   * 구별 주민등록인구수 : 구별 총 인구수
   * 구별 유동인구수 : 구별 총 유동인구수
   * 구별 공원면적 : 생활권공원 총 면적


## 현재 느끼고 있는 문제
* 인구수 기준을 유동인구 기준으로 삼는 것이 타당한가? 주민등록인구 기준이 나은가, 혹은 둘을 혼합한 지수를 만들어야 하나?
* 후에 가로등/cctv/지구대와 범죄의 상관관계 분석 시, 범죄율로 상관도를 분석하려면 면적 당 '해당 시설물' 수로 하는게 적합해 보이지만 분석에 복잡함이 있어 범죄율 대신 범죄발생수로 분석?
* 높은 범죄 발생률을 나타내는 상위 3~5개 구의 죄종별 분석시 임의로 가중치를 줄 수 있을까. 예를들어 살인과 폭행에 더 가중치를 두어 살인과 폭행이 많이 일어나는 구가 더 위험하다? 어떤 죄종이 더 위험하나 나누기 모호하지만 고려

## To-Do List
### 1. 범죄데이터 탐색




### 2. 범죄발생률과 유의한 상관성을 보이는 요소 탐색
* [유동인구와 지구대/파출소 수/ 범죄율 분석]
* [그래프 추가]
* [분석한 내용을 바탕으로 1번 항목의 범죄데이터 탐색과 연관지어 인사이트 도출 시도]




## 데이터 출처
* [서울시 5대 범죄 발생 현황](http://data.seoul.go.kr/dataList/316/S/2/datasetView.do)
* [서울시 공원 (1인당 공원면적) 현황](http://data.seoul.go.kr/dataList/360/S/2/datasetView.do)
* [서울시 구별 가로등 현황](http://data.seoul.go.kr/dataList/261/S/2/datasetView.do)
* [서울시 구별 주민등록인구 현황](http://data.seoul.go.kr/dataList/419/S/2/datasetView.do)
* [서울시 구별 유동인구 현황](http://datakorea.datastore.or.kr/profile/geo/04000KR11/#flow_top_bottom_private_data)
* [서울시 주민등록인구 (연령별/구별) 통계](http://data.seoul.go.kr/dataList/10718/S/2/datasetView.do)
* [서울시 지구대/파출소/치안센터 수](http://data.seoul.go.kr/dataList/224/S/2/datasetView.do)

## 참조
* [범죄 발생의 도시계획적 함의](http://kostat.go.kr/file_total/paper2005-1.pdf)
* [도시 내 공원녹지공간이 범죄에 미치는 영향](https://www.dbpia.co.kr/journal/articleDetail?nodeId=NODE01227581)

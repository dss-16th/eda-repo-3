# 서울시 구별 '공원면적' 및 '범죄율' 데이터를 통한 공원면적과 범죄율의 상관관계 탐색
##### ※ 가제이며, 추후 소스 데이터 변동에 따라 제목 수정 가능
## 소개
* 범죄자들이 모종의 공통된 경향성을 보일 것이라고 전제했을 때, 범죄(전체 혹은 종류별) 발생과 유의한 상관성을 보이는 요소를 찾고자 함
* 유의한 상관관계를 보이는 요소가 발견된다면, 계절별/월별/요일별/시간대별 범죄 데이터에까지 확장 적용하여 치안 관련 리소스가 더/덜 필요한 때를 분류, 효율적인 자원 운영에 기여할 수 있을 것으로 기대됨
* 우선 독립요인 데이터로 '공원면적'만을 선정하였으나, 다양한 데이터셋으로 분석 범위를 확대하며 유의한 독립요인을 지속적으로 찾아갈 예정임

## 조사 동기
* 지난 강의 결과, 범죄율이 높은 구로 영등포구 등 평소 위험하다고 인식되던 지역 외에 안전하다고 인식되던 강남3구도 포함되는 분석 결과가 나옴
* 언뜻 상반되어 보이는 두 개의 구에 대해 공통적으로 유의한 상관성을 보이는 요소가 있다면, 현재 혹은 미래에 그와 유사할 것으로 예상되는 지역의 치안 발전에 기여할 수 있을 것이라고 예상함

## 목표 (Goal)
* 구별 범죄율과 유의한 상관관계를 보이는 요소 파악

## Member / Role
* 임현수 / 
* 정다은 / 

## 데이터 출처
* [서울시 5대 범죄 발생 현황](http://data.seoul.go.kr/dataList/316/S/2/datasetView.do)
* [서울시 공원 (1인당 공원면적) 현황](http://data.seoul.go.kr/dataList/360/S/2/datasetView.do)
* [서울시 구별 가로등 현황](https://www.data.go.kr/tcs/dss/selectDataSetList.do?dType=TOTAL&keyword=%EC%84%9C%EC%9A%B8+%EA%B0%80%EB%A1%9C%EB%93%B1&detailKeyword=&publicDataPk=&recmSe=N&detailText=&relatedKeyword=&commaNotInData=&commaAndData=&commaOrData=&must_not=&tabId=&dataSetCoreTf=&coreDataNm=&sort=&relRadio=&orgFullName=&orgFilter=&org=&orgSearch=&currentPage=1&perPage=10&brm=%EA%B5%90%ED%86%B5%EB%AC%BC%EB%A5%98&instt=&svcType=&kwrdArray=&extsn=&coreDataNmArray=)
* [서울시 구별 주민등록인구 현황](http://data.seoul.go.kr/dataList/419/S/2/datasetView.do)
* [서울시 주민등록인구 (연령별/구별) 통계](http://data.seoul.go.kr/dataList/10718/S/2/datasetView.do)
* [서울시 지구대 1개소당 시민수](https://www.data.go.kr/data/15046341/fileData.do)

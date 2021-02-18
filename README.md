# [EDA 프로젝트] 서울시 자치구별 5대 범죄 발생 현황과 상관요인 


## 프로젝트 소개
   * 강남 3구(강남구, 서초구, 송파구)는 5대 범죄 건수로는 상위권을 차지했고 범죄에 안전하지 않다는 분석을 보게 되었습니다. 하지만 강남 3구의 체감안전도는 높다는 설문조사에 따라 정말 강남 3구가 안전하지 않은걸까하는 의문이 들어 EDA 프로젝트를 시작하게 되었습니다. 더 확장하여 주민등록기준 인구와 유동인구와의 관계를 살펴보고 다양한 요소와의 상관관계를 탐색하고자 합니다. 

## 프로젝트 주제
   * 서울시 자치구별 5대 범죄 발생과 현황과 상관요인을 주제로하여 서울시 범죄 발생과 유의한 상관 요소를 파악하고 시각화하고자 합니다. 
   
## 프로젝트 목적

   1. 강남 3구 범죄 발생 건수와 범죄율을 비교하여 안전도 확인
      * 강남 3구의 범죄 발생 건수와 범죄율에 따른 범죄 발생 순위를 탐색하고, 두 결과 사이에 어떤 차이가 있는지 확인하고, 특히 강남 3구의 순위에는 어떠한 변화가 있는지 알아보고자 합니다.
           
   2. 서울시 구별 범죄 발생과 유의한 상관관계를 보이는 요소 파악
      * 범죄 발생 장소별와 범죄 유형 사이에서 어떤 특성을 나타내는지 분석할 예정입니다. 유흥업소가 1%         증가할수록 5대 범죄 발생 건수는 0.003% 높아진다는 결과가 있었고 다양한 장소마다 5대 범                  죄 사이에 어떤 관계를 보이나 분석하려 합니다. 
      * 주민등록기준 인구와 유동인구의 상관관계 분석하여 거주인구와 유동인구 사이에 범죄 발생과 관련한         차이가 있는지 탐색하는 목적이 있습니다. 
      * 서울시 구별 생활권공원 면적과 지구대 수가 각각 범죄발생률과 범죄 발생건수 사이의 상관관계 확인         하려 합니다. 
      *
   3. 분석을 바탕으로 서울시의 효율적인 자원 운영에 기여하고 효과적인 도시계획의 근거로 사용가능한지         확인
      * 위의 분석 결과를 기반으로 서울시 각 자치구의 한정된 리소스로 효과적인 도시계획에 기여하고자 합         니다. 


## 데이터셋
  1. 서울시 열린데이터 광장
  
      * [서울시 5대 범죄 발생 현황](http://data.seoul.go.kr/dataList/316/S/2/datasetView.do)
      * [서울시 공원 (1인당 공원면적) 현황](http://data.seoul.go.kr/dataList/360/S/2/datasetView.do)
      * [서울시 구별 가로등 현황](http://data.seoul.go.kr/dataList/261/S/2/datasetView.do)
      * [서울시 구별 주민등록인구 현황](http://data.seoul.go.kr/dataList/419/S/2/datasetView.do)
      * [서울시 주민등록인구 (연령별/구별) 통계](http://data.seoul.go.kr/dataList/10718/S/2/datasetView.do)
      * [서울시 지구대/파출소/치안센터 수](http://data.seoul.go.kr/dataList/224/S/2/datasetView.do)
  
  2. 한국 데이터 산업진흥원
     * [서울시 구별 유동인구 현황](http://datakorea.datastore.or.kr/profile/geo/04000KR11/#flow_top_bottom_private_data)

## 데이터 전처리
  1. 정규화
  2. 상관관계 분석 : Pearson

## 탐색적 분석 EDA
  
  1. 주민등록인구/유동인구와 서울시 구별 5대 범죄발생 건수의 상관관계
  
     1-1. 주민등록인구 기준 전체 범죄 발생건수와 상관관계
        <img width="727" src="https://user-images.githubusercontent.com/75604413/108394239-d9661800-7257-11eb-92fa-8c1437a7a5aa.png">
   
       * 각각 0.51과 0.79의 강한 양의 상관관계가 있었고 주민등록인구와 유동인구 모두 높은 범죄발생 건수와 높은 상관관계를 보였습니다. 그러나 유동인구가 비교적 매우 높고 강한 상관도를 나타내었습니다. 범죄발생 건수와 강한 상관도를 가지는 유동인구 기준으로, 다양한 데이터셋과의 상관관계를 도출하려 합니다. 
   
   
  2. 서울시 구별 5대 범죄 발생 건수 및 범죄발생률
  
     2-1. 서울시 구별 5대 범죄발생 건수
      <img src="https://user-images.githubusercontent.com/75604413/108393191-c43cb980-7256-11eb-8fef-212e80e3620d.png" width="50%" height="50%"/>
      2-2. 서울시 구별 5대 범죄발생률
      <img src="https://user-images.githubusercontent.com/75604413/108393481-0e259f80-7257-11eb-9ed5-744c1ba29aee.png" width="50%" height="50%"/>
  
  3. 범죄 발생 장소와 범죄 유형별 범죄발생률
    
  <img src="https://user-images.githubusercontent.com/75604413/108393927-7e342580-7257-11eb-9259-58aa4a403a3a.png" width="50%" height="50%"/>
    
  4. 5대 범죄 발생 건수와 지구대의 상관관계
  <img src="https://user-images.githubusercontent.com/75604413/108397344-32837b00-725b-11eb-8733-09a7058b55c6.png" width="50%" height="50%"/>



  5. 범죄 발생률과 생활권공원 면적의 상관관계
  <img width="727" src="https://user-images.githubusercontent.com/75604413/108397309-27304f80-725b-11eb-9312-f4631632c7eb.png">





## 결과 (Result)
* 강남 3구가 비록 절대건수는 상~중위권에 속하나, 인구 대비 범죄발생건수의 비율을 보았을 때에는 주민등록/유동 인구 무관하게 중하위권에 위치함
   → 강남 3구의 높은 절대건수는 범죄발생률보다는 높은 인구수가 주요한 원인으로, 타 지역구 대비 위험하다고 보기 어렵다고 판단됨

* 살인의 경우, 절대건수 및 발생률 모두에서 영등포가 1~2위 권으로 매우 높은 수준을 보임
* 강도 및 강간강제추행의 경우, '강북구, 관악구, 금천구'가 범죄 발생률이 높게 나타남 (유동인구 수 대비 기준)
* 절도 및 폭력의 경우, 위 3구(강북구, 관악구, 금천구) 및 중랑구에서 범죄 발생률이 높게 나타남 (유동인구 수 대비 기준)

![image](https://user-images.githubusercontent.com/78459305/107248906-20912380-6a76-11eb-86d4-4c0d32b5f123.png)

 





## 참조
* 조중구 (2003). 범죄발생의 도시계획적 함의. 서울대학교 박사학위 논문
* 강준모, 김현정 (2007). 도시 내 공원녹지공간이 범죄에 미치는 영향.<대한토목학회논문집>, 27권 제1 D호, 117-129.
* 윤창완 (2014, 10, 20). [국감브리핑]'부자동네'...서울 강남 3구 체감안전도 높아. <NEWS 1>. URL: https://news.mt.co.kr/mtview.php?no=2014102009548225853
* 박대로 (2019, 02, 03). 서울 1인가구·유흥업소·女 많을수록 살인 등 5대범죄 다발. <NEWSIS>. URL: https://mobile.newsis.com/view.html?ar_id=NISX20190124_0000540393#_enliple



## Member / Role
* 임현수 / 범죄데이터 전처리 및 탐색
* 정다은 / 데이터 수집,데이터 전처리, 데이터 탐색, PPT 작성






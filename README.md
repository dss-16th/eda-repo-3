# [EDA 프로젝트] 서울시 자치구별 5대 범죄 발생 현황과 상관요인 


## 프로젝트 소개
   * '설문조사 결과 강남 3구(강남구, 서초구, 송파구)가 체감 안전도는 높게 나타났으나, 강남 3구의 실제 5대 범죄건수는 상위권이며 범죄로부터 안전하지 않다'는 분석을 접함
   * 하지만 '위험하다'의 기준으로써 '범죄발생건수'가 타당한지, '동일 인구수 대비 범죄발생률'이 더 타당하지는 않은지, 후자의 기준으로도 강남 3구는 위험하다는 결론이 나올지 의문이 들어 EDA 진행
   * 서울시 구별 범죄발생률에 따른 위험 여부를 판단하고, 나아가 범죄 발생과 인구(주민등록인구, 유동인구), 그리고 기타 요소들과의 상관관계를 탐색하고자 함


## 프로젝트 주제
   * '서울시 자치구별 5대 범죄 발생 현황 및 유의미한 상관 요소'를 주제로, 이들에 대한 파악 및 시각화 진행


## 프로젝트 목표

   1. 강남 3구를 포함한 서울 자치구들의 안전 여부 확인
      * 서울 자치구들의 범죄 발생건수와 범죄율 간의 순위 차이를 확인하며, 특히 강남 3구의 순위 변화, 즉 안전함에 대한 판단의 변화 여부 확인
           
   2. 서울시 구별 범죄 발생과 유의한 상관관계를 보이는 요소 파악
      * 주민등록인구보다 유동인구 중 범죄 발생과 더 상관성이 높은 요소 파악, 범죄발생률 산출 시 활용
      * 범죄 발생장소, 생활권공원 면적, 지구대 수 등 범죄발생률/건수와 상관관계가 유의미한 요소 탐색   (유흥업소의 수와 범죄발생 건수가 상관관계가 있는 것처럼 (하단 참고문헌 참조), 범죄 발생과 상관관계를 보이는 타 요소 추가 탐색 목적)


## 데이터 전처리
  1. 정규화
      - 범죄 종류별 발생건수 규모의 차이가 커, 그에 따른 왜곡을 방지하기 위함
      - 각 열에 대해 각각의 값을 최대값으로 나누어 0 ~ 1 사이의 값으로 변환
       - 예시
        ```
          crime[column] = crime[column] / crime[column].max()
        ```
          
  2. 상관관계 분석
      - Pearson 상관계수 이용
       - 예시
         ```
          assault_rate_corr = assault_rate.corr(method='pearson')
         ```
                

## 탐색적 분석 및 결과
  
  1. 주민등록인구/유동인구와 서울시 구별 5대 범죄발생 건수의 상관관계
  
     1-1. 주민등록인구 기준 전체 범죄 발생건수와 상관관계
        <img width="727" src="https://user-images.githubusercontent.com/75604413/108394239-d9661800-7257-11eb-92fa-8c1437a7a5aa.png">
   
       * 범죄발생건수와의 관계에서 유동인구가 주민등록인구 대비 더 높은 상관관계를 보임    
         (r(주민등록인구)=0.51, r(유동인구)=0.79)    
         → 유동인구를 기준으로 다른 데이터셋들과의 상관관계 도출
   
   
  2. 서울시 구별 5대 범죄 발생 건수 및 범죄발생률
  
     2-1. 서울시 구별 5대 범죄발생 건수
     
      <img src="https://user-images.githubusercontent.com/75604413/108393191-c43cb980-7256-11eb-8fef-212e80e3620d.png" width="50%" height="50%"/>
      
      * 절대적인 발생건수 기준, 강남3구는 상위권에 위치하여 위험한 구로 간주될 수 있음


      2-2. 서울시 구별 5대 범죄발생률
      
      <img src="https://user-images.githubusercontent.com/75604413/108393481-0e259f80-7257-11eb-9ed5-744c1ba29aee.png" width="50%" height="50%"/>
      
      * 그러나 유동인구 반영한 발생률 기준, 강남3구는 하위권에 위치하며, 따라서 범죄발생률 측면에서 타 자치구 대비 위험하지 않음
  
  3. 범죄 발생 장소와 범죄 유형별 범죄발생률
    
  <img src="https://user-images.githubusercontent.com/75604413/108393927-7e342580-7257-11eb-9259-58aa4a403a3a.png" width="50%" height="50%"/>
    
      * 범죄 발생은 대체로 노상에서 발생했으며, 특히 폭력에서 더욱 두드러지게 나타남
      * 반면, 살인은 노상 비율은 적었으며, 주로 주거지역에서 발생함
    
    
  4. 5대 범죄 발생 건수와 지구대의 상관관계
  <img src="https://user-images.githubusercontent.com/75604413/108397344-32837b00-725b-11eb-8733-09a7058b55c6.png" width="50%" height="50%"/>



  5. 범죄 발생률과 생활권공원 면적의 상관관계
  <img width="727" src="https://user-images.githubusercontent.com/75604413/108397309-27304f80-725b-11eb-9312-f4631632c7eb.png">


## 결과 요약
* 범죄 발생 건수는 대체로 주민등록인구보다는 유동인구와 더 높은 상관관계를 보임
* 강남 3구가 비록 절대건수는 상위권이나, 이는 많은 유동인구 때문으로 범죄발생률은 중~하위권에 위치하여 안전한 편임
* 대부분 범죄는 노상에서 다수 발생하는 반면, 살인은 예외적으로 주거지에서 높은 발생률을 보임
* 지구대 수와 범죄발생 건수 간에는  약한 양의 상관관계가 나타남
* 생활권 공원 면적을 늘리는 것은 절도/폭력발생률 감소에 유의미한 것으로 판단

## 기대 효과
* 분석을 바탕으로 서울시의 효율적인 자원 운영에 기여하고 효과적인 도시계획의 근거로 사용가능한지         확인
      * 위의 분석 결과를 기반으로 서울시 각 자치구의 한정된 리소스로 효과적인 도시계획에 기여하고자 합니다.


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


## 참고문헌
* 조중구 (2003). 범죄발생의 도시계획적 함의. 서울대학교 박사학위 논문
* 강준모, 김현정 (2007). 도시 내 공원녹지공간이 범죄에 미치는 영향.<대한토목학회논문집>, 27권 제1 D호, 117-129.
* 윤창완 (2014, 10, 20). [국감브리핑]'부자동네'...서울 강남 3구 체감안전도 높아. <NEWS 1>. URL: https://news.mt.co.kr/mtview.php?no=2014102009548225853
* 박대로 (2019, 02, 03). 서울 1인가구·유흥업소·女 많을수록 살인 등 5대범죄 다발. <NEWSIS>. URL: https://mobile.newsis.com/view.html?ar_id=NISX20190124_0000540393#_enliple


## Member / Role
* 임현수 / 범죄 데이터 및 인구 데이터 전처리, 분석, 시각화, 발표 내용 기획, 발표 자료 최종 검토, 발표.
* 정다은 / 기타 요소 데이터 전처리, 범죄 발생과 기타요소 간 상관관계 분석, 시각화, 발표자료 작성.






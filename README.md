# Analysis of Earthquake-prone Buildings🏚️

- 프로젝트 주제 : __지진 피해 고위험 건축물 현황 분석 및 시각화__

지진에 대한 큰 피해가 예상되는 건축물의 현황에 대해 분석하고 이를 시각화해 제공

## 프로젝트 개요

* 선정 배경
  1. 2023년 2월 6일 튀르키예 가지안테프토에서 발생한 규모 7.7의 강진으로 인해 국내 지진 위험성에 대한 경각심 제고
  2. 국내에서도 2016년의 경주지진(5.8 규모), 2017년의 포항지진(5.4 규모) 등의 강진 발생 경험
  3. 특히 포항지진을 통해 필로티형 건물의 위험성 부각
  - 대한건축학회에서 발표된 보고서에 따르면 기둥을 세우고 그 위에 건물을 올려 지탱하는 방식의 필로티형 건물 지진에 취약
    - [포항지진으로 드러난 필로티건물의 지진취약성] https://www.aik.or.kr/board/board_view.jsp?ncode=a001&num=1745
  - 2017년 국토교통부의 조사에 따르면 2015년 기준 전국 도시형 생활주택 총 13,933단지 중 88%인 12,321 단지가 지진에 취약한 필로티형 건축물로 확인

__따라서 필로티형 건물이 밀집된 지역을 파악하여 내진보강 정책의 시범지역 선정을 위한 근거자료로서 제공하고자 한다__

* 기대효과
  1.	지진정보와 건축물정보를 통해 지진 취약 거주지역 도출
  2.	지역별 주택유형별 인허가 추이, 지진 빈도, 옥외대피소 위치 등 현황 분석 정보 제공
  3.	지진 관련 정책(건축물 내진보강, 내진 설계 점검, 자치구별 지진 예산 편성) 시범 적용 지역 선정의 근거로서 활용



## 프로젝트 수행

* 데이터 선정 기준
  1. 지역 선정
      - 선행 연구에 따르면 활성 단층 중 강진을 동반할 수 있는 활성단층 후보 (추가령 단층, 옥천 습곡대 단층, 양산 단층)
          + [공간 분석 기반 지진 위험도 정보를 활용한 우리나라 지진 취약 지역 평가] https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART002544690
      - 추가령 단층은 활성 밀도가 높지만 범위가 좁아 위험도가 상대적으로 낮음, 옥천 습곡대 단층은 범위는 넓지만 활성 밀도가 낮아 위험도가 상대적으로 낮음
      - 따라서 두 습곡대보다 범위가 넓으면서 활성 밀도도 높은 양산 단층 위에 형성된 __영남권 지역을 분석 지역으로 선정__
     

   2. 주택 유형 선정
       - 2017년 발표된 국토교통부의 통계에 따르면 2015년 기준 전국 도시형 생활주택 총 13,933단지 중 88%인 12,321 단지가 지진에 취약한 필로티형 건축물로 확인
       - 2016년 경주 지진 이후 내진설계의 기준이 서로 상이한 점을 개선하여 2017년 2월 일관성 유지를 위하여 내진설계법이 개정
       - 따라서 최종적으로 `영남권 지역의 2017년 2월 이전에 지어진 도시형생활주택 밀집 지역` 으로 데이터 분석 범위를 선정

* 데이터 전처리

  1. 건축인허가 데이터를 주택 유형별, 지역별, 건축 인허가 날짜별로 분류
      -	전체 주택 유형 대비 도시형 생활주택(약 90%가 필로티 구조, 최우선 취약지역 도출 기준)비율 도출
      -	주택 유형별, 연도별 건축 인허가 추이 도출
      -	지진 발생 위험도가 높은 영남권 지역의 도시형 생활주택 밀집 지역(동단위) 도출후 위도와 경도 등 위치 정보 추가(지도 시각화) = 	내진설계 점검 우선 지역 선정 자료로서 활용 
      -	지진 발생 위험도가 높은 영남권 지역의 2005년 7월 이전에 건설된 5층 이하의 필로티형 건축물(국내건축물 내진설계 규정에 포함되지 않은 건축물 기준) 밀집 지역 도출 = 지진 위험 노출 고위험 지역(최종 목적) 

  2. 국내 지진 발생 데이터를 연도별, 지역별로 분류
      - 연도별, 지역별 지진 발생 추이 도출

  3. 지진옥외대피소 데이터를 지역별로 분류한 후 위도와 경도 등 지도 시각화를 위한 위치 정보 추가
      -	지도 시각화를 위한 위치 정보 추가
      -	지역별 지진옥외대피소 개수 확인

* 데이터 탐색 및 시각화

  -	주택인허가 데이터를 통해 도시형 생활주택 밀집 지역 분석(전체)
  -	전체 주택 유형 대비 도시형 생활주택 비율 파이 차트
  -	연도별, 지역별 지진 발생 추이 그래프(1977년 부터 최근까지)
  -	주택 유형별, 연도별 건축 인허가 추이 그래프
  -	지진 피해 고위험 노출 지역 지도 시각화(지진 발생 위험도가 높은 영남권 지역의 필로티형 주택 밀집 지역-2017년 2월 이전 건설
  

## 데이터 및 타겟 명세

1) 건축인허가 데이터(기본, 주택용도)
(국토교통부 건축데이터 민간개방 시스템,~2023-01, 630070행)
지역별 필로티 구조의 건축물 수 확인 및 필로티 구조의 건축물 수 동향 파악에 이용
2) 국내지진조회 데이터
(기상청 날씨누리,1977-01~2023-01, 2118행)
지역별 지진 횟수 정리하여 시각화 및 지진 위험도 산출에 반영
3. 지진 옥외대피장소 데이터
(행정안전부,2022-09-20, 2118행)
지진 옥외대피 장소 지도 시각화에 사용
 
## 첨부 파일 설명

[analysis] 폴더는 데이터 수집(오픈API)과 전처리, 시각화를 한 코드파일.
  - '지진옥외대피소 오픈 API 데이터' 파일은 오픈 API를 사용해 데이터를 크롤링하고 저장한 코드.
  - '지진옥외대소 전처리 + 시각화' 파일은 위에서 저장한 데이터를 이용해 전처리하고 시각화한 코드.
  - '건축 데이터 전처리 + 시각화' 파일은 국내 건축 인허가 데이터를 전처리하고 시각화한 코드.
  - '국내 지진 데이터 전처리 + 시각화' 파일은 국내 지진 통계 데이터를 전처리하고 시각화한 코드. 
  - 'json파일 변경' 파일은 geojson을 원하는 범위로 맞추어 만들기 위해 사용한 코드.


[데이터] 폴더는 코드 파일에서 사용한 데이터 모음.

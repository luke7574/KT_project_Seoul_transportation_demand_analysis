# 서울시 생활 정보 기반 대중교통 수요 분석 
---
## 프로젝트 개요 
- 주제 : 버스 노선 추가가 필요한 서울 시 내 자치구 선정
- 데이터 : 생활이동 정보, 버스 정보, 구별 거주 인구 정보
- 데이터 출처 : <https://data.seoul.go.kr/dataVisual/seoul/seoulLivingMigration.do>
- 목표 : 가설 수립, 단변량/이변량 분석, 검증, 인사이트 도출
---
## 데이터 소개
![image](https://github.com/user-attachments/assets/35af67dc-7174-44b2-b91b-ab0660d8f2f1)
---
## 문제 해결 프로세스 
![image](https://github.com/user-attachments/assets/9abdf435-2b47-45f9-a70c-42641c6fff1a)
---
### 가설 수립 
- 가설 1 : 총 이동인구가 많으면, 노선 추가가 필요할 것이다.
- 가설 2 : 평균 이동 시간이 긴 자치구와 인접하게 있으면 버스이용이 많아 노선이 필요할 것이다.
- 가설 3 : 상가가 많이 발달하여 승하차 평균 승객이 많으면서, 정류장이 없는 지역에 정류장 추가가 필요할 것이다.

--- 
## 단변량 분석
- **노선수**
![image](https://github.com/user-attachments/assets/6ca219c7-d3a7-490c-9766-68f675f6718a)
---
- **정류장 수**
![image](https://github.com/user-attachments/assets/cfcde39d-85ca-422e-8682-0ca769af23ea)
---
- **총 이동 인구 수**
![image](https://github.com/user-attachments/assets/a09fee3b-7288-4e32-b906-a5246c0b7ddc)
---

## 가설 1 : 총 이동인구가 많으면, 노선 추가가 필요할 것이다.
![image](https://github.com/user-attachments/assets/4e599273-bbe0-4c0f-95f9-890fa6b851b3)
- 현재 강남구,서초구를 비롯해 총 승객수 비율이 높게 측정 됨.
- 하지만 노선같은경우에는 현재 서대문,종로구가 높은 비율을 갖고 있음.
- 또한 정류장 수를 보면 현재 서초,강북 지역이 높은 비율을 갖고 있음.
- 현재 강남, 서초, 관악 지역이 하차 비율이 높게 평가 됨.
- **PearsonRResult(statistic=0.2842787773745359, pvalue=0.1684396143339288)**
- **상관계수가 0.28, p-value < 0.05 보다 크므로, 관계가 없다고 판단.**

## 가설 2 : 평균 이동 시간이 긴 자치구와 인접하게 있으면 버스이용이 많아 노선이 필요할 것이다.
![image](https://github.com/user-attachments/assets/e33c557c-f5db-4f26-be06-92ba50d2ea19)
![image](https://github.com/user-attachments/assets/6982c5df-e634-4534-bd97-f6530ca8dab8)

- 평균 이동 시간과 정류장수의 상관계수 0.29, p 검정값 0.16 (0.05 이상)
- 평균 이동 시간과 노선수의 상관계수 -0.55, p 검정값0.004 (0.05 이하)
- 평균 이동 시간과 승차평균승객수의 상관계수 -0.34, p 검정값0.101 (0.05 이상)
- **데이터 분석 결과, 평균 이동 시간과 인근 자치구의 승차 승객 수는 관련 없음을 확인하였다.**

## 가설 3 : 상가가 많이 발달하여 승하차 평균 승객이 많으면서, 정류장이 없는 지역에 정류장 추가가 필요할 것이다.
### 가설 3-1 : 상가와 승하차 승객 수는 총 유동인구와 높은 상관관계가 있을 것이다.
- 총 이동인구, 상가총합, 승하차총합, 승하차평균총합 의 상관관계
![image](https://github.com/user-attachments/assets/398fb89c-bfbe-468d-9ce7-699cedcdd334)
- 상가 총합과 유동인구의 상관계수 0.94, p-value 2.387695248905012e-12로 0.05 이하
- 승하차총합과 유동인구의 상관계수 0.63, p-value 0.0007167474589489073로 0.05 이하
- 승하차평균총합과 유동인구의 상관계수 0.04, p-value 0.8569474258867641로 0.05 이상
- **상가 개수, 승하차 승객수 총합, 승하차 평균 승객수 총합 순으로 유동인구와 높은 상관관계가 있다.**
- **상가 개수와 승하차 승객은 관계가 있으나, 평균 승객은 유의미한 관계를 보이고 있지 않다.**

### 가설 3-2 : 총 유동인구와 버스 수요(즉, 정류장 수)는 높은 상관관계가 있을 것이다.
![image](https://github.com/user-attachments/assets/ba78ce6f-c852-4757-8391-6979160b98b0)
![image](https://github.com/user-attachments/assets/b2c1527c-5737-4a25-8190-59b0c33ab2ed)
- 총 유동인구와 정류장수는 비슷한 경향이 있다.
- 총 유동인구와 정류장 수의 상관계수는 0.40, p-value는 0.05와 근사한 값으로 서로 관계가 있다고 볼 수 있다.
- **상가와 승하차 승객 수는 정류장 수요에 유의미하므로, 상가와 승하차 승객 수 대비 정류장 비율이 가장 낮은 곳에 정류장을 더 설치하면 될 것이다.**

## 결론
![image](https://github.com/user-attachments/assets/323dd59f-81c4-42d8-8a03-0850e8f049ef)
> ****위 그래프와 같이 왼쪽으로 갈수록 상가&승하차 승객의 수는 많지만, 정류장의 수는 적은 것을 의미하므로 두 그래프에서 모두 하위에 랭크된 **중구, 강남구, 종로구** 3개의 자치구에 가장 필요할 것으로 보인다.****



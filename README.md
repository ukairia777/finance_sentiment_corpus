# 금융 감성 분석 데이터셋 (finance sentiment corpus)
금융 감성 분석에 사용할 수 있는 긍정(positive), 중립(neutral), 부정(negative)이 라벨링이 된 텍스트 데이터입니다.  

한국어 금융 분석 모델 개발을 위해 기존 금융 감성 분석 영어 데이터셋을 번역하여 한국어 버전을 만들었습니다.  
번역 후 육안 검수하였으며 동일 크기의 DL 모델에서 기존의 영어 데이터와 일치하는 테스트 정확도를 얻었습니다.  
실험 내용은 아래의 유효성 검증에 기재하였습니다.  

finance_data.csv
---
- 언어 : 영어, 한국어  
- 출처 : Finance Phrase Bank (Malo et al., 2014)  
- 데이터 건수 : 4,846건

영어 데이터
---
- Finance Phrase Bank (Malo et al., 2014)  
- 금융 뉴스 데이터에서 4,840여개의 문장 추출
- 16명의 전문지식을 갖춘 연구자들에 의해 수동 라벨링하여 만들었음.
- 감정 라벨 : positive, neutral, negative

한국어 데이터
---
- 위 데이터를 한국어로 번역 및 검수한 데이터.

데이터 미리보기
---
```
lables   sentence   kor_sentence
neutral   "According to Gran, the company has no plans to move all production to Russia, although that is where the company is growing."   "Gran에 따르면, 그 회사는 회사가 성장하고 있는 곳이지만, 모든 생산을 러시아로 옮길 계획이 없다고 한다."
neutral   "Technopolis plans to develop in stages an area of no less than 100,000 square meters in order to host companies working in computer technologies and telecommunications, the statement said."   테크노폴리스는 컴퓨터 기술과 통신 분야에서 일하는 회사들을 유치하기 위해 10만 평방미터 이상의 면적을 단계적으로 개발할 계획이라고 성명은 밝혔다.
negative   "The international electronic industry company Elcoteq has laid off tens of employees from its Tallinn facility ; contrary to earlier layoffs the company contracted the ranks of its office workers, the daily Postimees reported."   "국제 전자산업 회사인 엘코텍은 탈린 공장에서 수십 명의 직원을 해고했으며, 이전의 해고와는 달리 회사는 사무직 직원 수를 줄였다고 일간 포스티메스가 보도했다."
positive   With the new production plant the company would increase its capacity to meet the expected increase in demand and would improve the use of raw materials and therefore increase the production profitability.   새로운 생산공장으로 인해 회사는 예상되는 수요 증가를 충족시킬 수 있는 능력을 증가시키고 원자재 사용을 개선하여 생산 수익성을 높일 것이다.
positive   "According to the company's updated strategy for the years 2009-2012, Basware targets a long-term net sales growth in the range of 20 % -40 % with an operating profit margin of 10 % -20 % of net sales."   "2009-2012년 회사의 업데이트된 전략에 따르면, Basware는 20% - 40% 범위의 장기적인 순매출 성장을 목표로 하고 있으며, 영업이익률은 순매출액의 10% - 20%를 목표로 하고 있습니다."
```

기존 영어 데이터 성능으로 비교한 한국어 데이터의 유효성 검증
---
훈련 데이터와 테스트 데이터를 8:2 비율로 분할 후 훈련 데이터의 20%를 다시 검증 데이터로 사용.

- LSTM으로 텍스트 분류를 수행하였을 때 영어 테스트 데이터에서 정확도 77.38% 확인.  
- LSTM으로 텍스트 분류를 수행하였을 때 한국어 테스트 데이터에서 정확도 77.95% 확인.  
- 구글 BERT로 텍스트 분류를 수행하였을 때 영어 테스트 데이터에서 정확도 85.85% 확인.  
- 한국어 BERT로 텍스트 분류를 수행하였을 때 한국어 테스트 데이터에서 정확도 85.82% 확인.  

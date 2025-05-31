# Null속성의이해
## Null특성
- 비정의값, 
  - ❌0
  - ❌‘ ‘
- NOT NULL 또는 PRIMARY KEY 외 모든 데이터 유형에 포함 가능 
- NVL, ISNULL로 다른 결과값을 얻음 
- 집계 함수에서는 제외됨 


## Null연산 
- NULL값과의연산은 Null을 리턴 
- 모든비교는 Unknown 리턴 
  - NULL=NULL ▶️UnKnown
  - NULL!=NULL▶️UnKnown
- 집계함수는 Null제외하고 계산 



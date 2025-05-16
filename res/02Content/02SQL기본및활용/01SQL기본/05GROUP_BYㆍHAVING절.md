# GROUP_BYㆍHAVING절
- [집계 함수(Aggregate Function)](#집계-함수aggregate-function)
- [HAVING절](#having절)
- [CASE표현을 활용한 월별데이터집계](#case표현을-활용한-월별데이터집계)
- [집계함수와 NULL](#집계함수와-null)

## 집계 함수(Aggregate Function)
- 여러 행들의 그룹이 모여서 그룹당 단 하나의 결과를 돌려주는 함수
- GROUP BY절은 행들을 소그룹화 한다
- SELECT절 , HAVING절 , ORDER BY절에 사용할 수 있다


Syntax
- ```sql
  집계함수명( [DISTINCT|ALL] 컬럼이나 표현식)
  ```
- ALL
  - Default
- DISTINCT


집계함수
- COUNT(*)
- COUNT(표현식)
- SUM([DISTINCT|ALL] 표현식)
- AVG([DISTINCT|ALL] 표현식)
- MAX([DISTINCT|ALL] 표현식)
- MIN([DISTINCT|ALL] 표현식)
- STDDEV([DISTINCT|ALL] 표현식)
- VARIAN([DISTINCT|ALL] 표현식)
- 기타통계함수

## GROUP BY절
Syntax
- ```sql
  SELECT [DISTINCT] 칼럼명 [ALIAS명]
  FROM 테이블명
  [WHERE 조건식]
  [GROUP BY 칼럼(Column)이나 표현식]
  [HAVING 그룹조건식];
  ```

특성
- GROUP BY절을통해 소그룹별기준을정한후 SELECT절에 집계함수를 사용한다
- 집계함수의 통계정보는 NULL값을 가진행을 제외하고 수행한다
- GROUP BY절에서는 SELECT절과는달리 ALIAS명 사용불능
- 집계함수는 WHERE절에 올수없다
- WHERE절은 전체데이터를 GROUP BY절보다 WHERE절이 먼저수행된다
- HAVING절은 GROUP BY절의 기준항목이나 소그룹의 집계함수를 이용한조건을 표시할수있다
- GROUP BY절에의한 소그룹별로 만들어진 집계데이터중, HAVING절에서 제한조건을두어 조건을만족하는 내용만출력
- HAVING절은 일반적으로 GROUP BY절 뒤에 위치한다

## HAVING절
Ex.
- HAVING AVG()
- HAVING MAX()
## CASE표현을 활용한 월별데이터집계
- 개별데이터확인
- 월별데이터구분
- 부서별데이터집계

## 집계함수와 NULL
- 전체NULL▶️⭕NULL
- 일부NULL▶️❌NULL

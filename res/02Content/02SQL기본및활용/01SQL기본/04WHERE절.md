# WHERE절
- [WHERE조건절개요](#where조건절개요)
- [연산자의 종류](#연산자의-종류)
- [비교연산자](#비교연산자)
- [SQL연산자](#sql연산자)
- [논리연산자](#논리연산자)
- [부정연산자](#부정연산자)
- [ROWNUM, TOP사용](#rownum-top사용)



## WHERE조건절개요
```sql
SELECT [DISTINCT/ALL] 칼럼명 [ALIAS명]
FROM 테이블명
WHERE 조건식;
```
## 연산자의 종류
- 비교연산자 (부정비교연산자 포함)
- SQL연산자  (부정SQL연산자 포함)
- 논리연산자

연산자우선순위
- 괄호()
- NOT연산자
- 비교연산자/SQL연산자
- AND
- OR

## 비교연산자
- =
- \>
- \>=
- <
- <=
## SQL연산자
- BETWEEN
  - BETWEEN a AND b
- IN
  - IN (list)
- LIKE
  - LIKE '비교문자열'
  - 와일드카드
    - %
    - _
- IS NULL
  - NULL값과의 수치연산은 NULL값을 리턴한다
  - NULL값과의 비교연산은 거짓(FALSE)값을 리턴한다
  - 어떤값과 비교할수도없으며, 특정값보다 크다적다라고 표현할수없다
## 논리연산자
- AND
- OR
- NOT
## 부정연산자

부정논리연산자
- !=
- ^=
- <>
- NOT 컬럼명 =
- NOT 컬럼명 >

부정SQL연산자
- NOT BETWEEN a AND b
- NOT IN (list)
- IS NOT NULL

## ROWNUM, TOP사용
ROWNUM
- 행의개수
- WHERE절
- WHERE ROWNUM

TOP
- 행의개수
- SELECT절
- SELECT TOP
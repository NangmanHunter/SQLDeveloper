# ORDER_BY절
- [ORDER BY정렬](#order-by정렬)
- [SELECT문장실행순서](#select문장실행순서)
- [TopN쿼리](#topn쿼리)
## ORDER BY정렬
```sql
SELECT 칼럼명 [ALIAS명]
FROM 테이블명
[WHERE 조건식]
[GROUP BY 칼럼(Column)이나 표현식]
[HAVING 그룹조건식]
[ORDER BY 칼럼(Column)이나 표현식 [ASC 또는 DESC]] ;
```

- 기본▶️ASC 

Null
- Oracle
  - 가장큰값
  - 맨뒤(ASC)
- SQLServer
  - 가장작은값
  - 맨앞(ASC)

## SELECT문장실행순서
```sql
5. SELECT 칼럼명 [ALIAS명]
1. FROM 테이블명
2. WHERE 조건식
3. GROUP BY 칼럼(Column)이나 표현식
4. HAVING 그룹조건식
6. ORDER BY 칼럼(Column)이나 표현식;
```
## TopN쿼리
ROWNUM
- Oracle
- ```sql
  SELECT ENAME, SAL
  FROM (SELECT ENAME, SAL
        FROM EMP
        ORDER BY SAL DESC)
  WHERE ROWNUM <4 ;
  ```

TOP()
- SQLServer
- ```sql
  SELECT TOP(2) ENAME, SAL
  FROM EMP
  ORDER BY SAL DESC;
  ```

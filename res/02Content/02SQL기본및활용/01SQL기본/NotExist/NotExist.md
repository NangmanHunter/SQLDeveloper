# NOT EXISTS
## WHERE NOT EXISTS
```sql
SELECT ...
FROM 테이블A
WHERE NOT EXISTS (
    SELECT 1
    FROM 테이블B
    WHERE 테이블B.조건 = 테이블A.조건
);
```

주문한적없는 고객찾기
```sql
SELECT *
FROM 고객 c
WHERE NOT EXISTS (
    SELECT 1
    FROM 주문 o
    WHERE o.고객ID = c.고객ID
);
```
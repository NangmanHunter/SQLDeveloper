# DDL
- [데이터유형](#데이터유형)
- [CREATE TABLE](#create-table)
  - [테이블과 칼럼 정의](#테이블과-칼럼-정의)
  - [제약조건(CONSTRAINT)](#제약조건constraint)
  - [생성된 테이블구조확인](#생성된-테이블구조확인)
  - [SELECT문장을통한 테이블생성사례](#select문장을통한-테이블생성사례)
- [ALTER TABLE](#alter-table)
  - [ADD COLUMN](#add-column)
  - [DROP COLUMN](#drop-column)
  - [MODIFY COLUMN](#modify-column)
  - [RENAME COLUMN](#rename-column)
  - [DROP CONSTRAINT](#drop-constraint)
  - [ADD CONSTRAINT](#add-constraint)
- [RENAME TABLE](#rename-table)
- [DROP TABLE](#drop-table)
- [TRUNCATE TABLE](#truncate-table)

## 데이터유형

주요데이터유형
- CHARACTER
  - CHARACTER(s)
- VARCHAR
  - VARCHAR(s)
- NUMERIC
- DATETIME

## CREATE TABLE
### 테이블과 칼럼 정의
CREATE TABLE
- 테이블명

- Syntax
  - ```sql
    CREATE TABLE 테이블명(
      칼럼명1 DATATYPE [DEFAULT 형식],
      칼럼명2 DATATYPE [DEFAULT 형식],
      칼럼명3 DATATYPE [DEFAULT 형식]
    );
    ```
  - ```sql
    CREATE TABLE 테이블명(
      칼럼명1 DATATYPE [DEFAULT 형식]
      ,칼럼명2 DATATYPE [DEFAULT 형식]
      ,칼럼명3 DATATYPE [DEFAULT 형식]
    );
    ```
  - ```sql
    CREATE TABLE 테이블명(
      칼럼명1 DATATYPE [DEFAULT 형식]
      ,칼럼명2 DATATYPE [DEFAULT 형식]
      ,칼럼명3 DATATYPE [DEFAULT 형식]
      ,칼럼명3 DATATYPE [DEFAULT 형식]
      ,CONSTRAINT 제약조건명 제약조건 (칼럼명)
    );
    ```



### 제약조건(CONSTRAINT)
- 제약조건의 종류
  - PRIMARY KEY
  - UNIQUE KEY
  - NOT NULL
  - CHECK
  - FOREIGN KEY
- NULL의미
  - ✅NULL ASCII00번
  - ❌BLANK ASCII32번
  - ❌ZERO ASCII48번
  - ❌공집합
- DEFAULT의미
  - NULL값
  - 정의값


### 생성된 테이블구조확인
- ```sql
  DESCRIBE 테이블명;
  ```
- ```sql
  DESC 테이블명;
  ```

### SELECT문장을통한 테이블생성사례
- CTAS방법
- CTAS: Create Table ~ As Select ~

Oracle
- ```sql 
  CREATE TABLE TEAM_TEMP
  AS SELECT * FROM TEAM;
  ```

SQLServer
- ```sql 
  SELECT* INTO TEAM_TEMP FROM TEAM;
  ```

## ALTER TABLE
### ADD COLUMN
```sql
ALTER TABLE 테이블명
ADD 칼럼명 데이터유형;
```
- 추가칼럼
- ✅마지막칼럼
- ❌위치지정칼럼

### DROP COLUMN
```sql
ALTER TABLE 테이블명
DROP COLUMN 칼럼명;
```

### MODIFY COLUMN
- Oracle
  - MODIFY
  - ```sql
    ALTER TABLE 테이블명
    MODIFY (칼럼명1 데이터유형 [DEFAULT 식] [NOT NULL],
            칼럼명2 데이터유형 [DEFAULT 식] [NOT NULL]
    )
    ```
- SQLServer
  - ALTER COLUMN
  - ```sql
    ALTER TABLE 테이블명
    ALTER COLUMN 칼럼명 데이터유형 [DEFAULT 식] [NOT NULL]
    ```

특징
- ✅늘림크기
- ❌줄임크기
- NULL값ㆍ아무행도없는경우
  - ✅줄임크기
- DEFAULT변경
  - ❌이전데이터영향
  - ✅이후데이터영향
- NOT NULL조건
  - NULL없을경우만



### RENAME COLUMN
Oracle
```sql
ALTER TABLE 테이블명
RENAME COLUMN 칼럼명 TO 칼럼명;
```

SQLServer
```sql
sp_rename 칼럼명, 칼럼명, 'COLUMN';
```


### DROP CONSTRAINT
```sql
ALTER TABLE 테이블명 
DROP CONSTRAINT 제약조건명;
```

### ADD CONSTRAINT
```sql
ALTER TABLE 테이블명
ADD CONSTRAINT 제약조건명 제약조건 (칼럼명)
```
## RENAME TABLE
Oracle
```sql
RENAME 테이블명 변경후 테이블명;
```

SQLServer
```sql
sp_rename 테이블명, 테이블명;
```

## DROP TABLE
```sql
DROP TABLE 테이블명 [CASCADE CONSTRAINT];
```
- CASCADE옵션
- CASCADE CONSTRAINT

## TRUNCATE TABLE
```sql
TRUNCATE TABLE 테이블명;
```
- 모든행제거

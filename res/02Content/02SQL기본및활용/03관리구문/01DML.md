# DML
- [INSERT](#insert)
- [UPDATE](#update)
- [DELETE](#delete)
- [SELECT](#select)
- [산술연산자ㆍ합성연산자](#산술연산자ㆍ합성연산자)
  - [산술연산자](#산술연산자)
  - [합성연산자](#합성연산자)

## INSERT
- ```sql
  INSERT INTO 테이블명
  VALUES (VALUE_LIST)
  ```
- ```sql
  INSERT INTO 테이블명 (COLUMN_LIST)
  VALUES (VALUE_LIST)
  ```


## UPDATE
- ```sql
  UPDATE 테이블명
  SET 컬럼명=컬럼값
  ```
## DELETE
- ```sql
  DELETE [FROM] 테이블명
  ```
## SELECT
- ```sql
  SELECT [ALL/DISTINCT] 칼럼명, 칼럼명, ...
  FROM
  ```
  - ALL 
    - ⭕중복데이터출력
    - Default
  - DISTINCT
    - ❌중복데이터출력


WildCard사용
- ```sql
  SELECT *
  FROM
  ```

ALIAS부여
- ```sql
  SELECT PLAYER_NAME AS 선수명
  FROM PLAYER
  ```
- ```sql
  SELECT PLAYER_NAME 선수명
  FROM PLAYER
  ```


## 산술연산자ㆍ합성연산자
### 산술연산자
- NUMBER
- DATE

산술연산자
- ()
- \*
- /
- \+
- \-

### 합성연산자
- 문자+문자

특징
- ||
  - Oracle
- \+
  - SQLServer
- CONCAT
  - CONCAT (string1, string2)
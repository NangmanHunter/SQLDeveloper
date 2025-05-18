# DCL
- [DCL개요](#dcl개요)
- [유저와 권한](#유저와-권한)
  - [유저생성과 시스템권한부여](#유저생성과-시스템권한부여)
  - [OBJECT에 대한 권한 부여](#object에-대한-권한-부여)
- [Role을 이용한 권한부여](#role을-이용한-권한부여)

## DCL개요
## 유저와 권한
Oracle유저
- SCOTT
- SYS
- SYSTEM

### 유저생성과 시스템권한부여
```sql
GRANT CREATE USER TO SCOTT;
CONN SCOTT/TIGER
CREATE USER PJS IDENTIFIED BY KOREA7;
```


### OBJECT에 대한 권한 부여
Oracle
```
ALTER     ▶️✅테이블ㆍ❌VIEWSㆍ✅SEQUENCEㆍ❌PROCEDURE
DELETE    ▶️✅테이블ㆍ✅VIEWSㆍ❌SEQUENCEㆍ❌PROCEDURE
EXECUTE   ▶️❌테이블ㆍ❌VIEWSㆍ❌SEQUENCEㆍ✅PROCEDURE
INDEX     ▶️✅테이블ㆍ❌VIEWSㆍ❌SEQUENCEㆍ❌PROCEDURE
INSERT    ▶️✅테이블ㆍ✅VIEWSㆍ❌SEQUENCEㆍ❌PROCEDURE
REFERENCES▶️✅테이블ㆍ❌VIEWSㆍ❌SEQUENCEㆍ❌PROCEDURE
SELECT    ▶️✅테이블ㆍ✅VIEWSㆍ✅SEQUENCEㆍ❌PROCEDURE
UPDATE    ▶️✅테이블ㆍ✅VIEWSㆍ❌SEQUENCEㆍ❌PROCEDURE
```

SQLServer
```
ALTER     ▶️✅테이블ㆍ❌VIEWSㆍ✅FUNCTIONㆍ❌PROCEDURE
DELETE    ▶️✅테이블ㆍ✅VIEWSㆍ✅FUNCTIONㆍ❌PROCEDURE
EXECUTE   ▶️❌테이블ㆍ❌VIEWSㆍ❌FUNCTIONㆍ✅PROCEDURE
INDEX     ▶️✅테이블ㆍ❌VIEWSㆍ❌FUNCTIONㆍ❌PROCEDURE
INSERT    ▶️✅테이블ㆍ✅VIEWSㆍ❌FUNCTIONㆍ❌PROCEDURE
REFERENCES▶️✅테이블ㆍ❌VIEWSㆍ❌FUNCTIONㆍ❌PROCEDURE
SELECT    ▶️✅테이블ㆍ✅VIEWSㆍ✅FUNCTIONㆍ❌PROCEDURE
UPDATE    ▶️✅테이블ㆍ✅VIEWSㆍ❌FUNCTIONㆍ❌PROCEDURE
```

## Role을 이용한 권한부여
- 유저들과 권한들 사이에서 중개역할
```sql
CONN SYSTEM/MANAGER
CREATE ROLE LOGIN_TABLE;
GRANT CREATE SESSION, CREATE TABLE TO LOGIN_TABLE;
GRANT LOGIN_TABLE TO JISUNG;

CONN JISUNG/KOREA7
CREATE TABLE MENU2(
  MENU_SEQ NUMBER NOT NULL,
  TITLE VARCHAR2(10)
);
```

Oracle
- 주요ROLE
  - CONNECT
    - ALTER SESSION
    - CREATE CLUSTER
    - CREATE DATABASE LINK
    - CREATE MENU_SEQUENCE
    - CREATE SESSION
    - CREATE SYNONYM
    - CREATE TABLE
    - CREATE VIEW
  - RESOURCE
    - CREATE CLUSTER
    - CREATE INDXTYPE
    - CREATE OPERATOR
    - CREATE PROCEDURE
    - CREATE MENU_SEQUENCE
    - CREATE TABLE
    - CREATE TRIGGER
    - CREATE

SQLServer
- 서버수준역할명
  - public
  - bulkadmin
  - dbcreator
  - diskadmin
  - processadmin
  - securityadmin
  - serveradmin
  - setupadmin
  - sysadmin
- 데이터베이스수준역할명
  - db_accessadmin
  - db_backupoperator
  - db_datareader
  - db_datawriter
  - db_ddladmin
  - db_denydatareader
  - db_denydatawriter
  - db_owner
  - db_securityadmin
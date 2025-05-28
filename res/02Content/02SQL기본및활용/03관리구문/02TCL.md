# TCL
- [트랜잭션개요](#트랜잭션개요)
- [COMMIT](#commit)
- [ROLLBACK](#rollback)
- [SAVEPOINT](#savepoint)

## 트랜잭션개요
- 데이터베이스의 논리적연산단위
- ALL OR NOTHING

TCL
- Commit
- RollBack
- SavePoint

특성
- 원자성
- 일관성
- 고립성
- 지속성


## COMMIT
- 트랜잭션을 완료
- Locking

SQLServer의 COMMIT
- Oracle
  - 수동커밋
- SQLServer
  - 자동커밋




3가지방식
- AUTO COMMIT
- 암시적 트랜잭션
- 명시적 트랜잭션
  - 시작ㆍ끝 지정
  - BEGIN TRANSACTION▶️COMMIT TRANSACTION
  - BEGIN TRANSACTION▶️ROLLBACK TRANSACTION
    - BEGIN TRANSACTION
      - BEGIN TRAN
    - COMMIT TRANSACTION
      - COMMIT
    - ROLLBACK TRANSACTION
      - ROLLBACK


## ROLLBACK
- 변경사항 취소

SQLServer의 ROLLBACK 
- AUTO COMMIT
- 명시적트랜잭션
  - 임의적ROLLBACK

COMMITㆍROLLBACK효과
- 데이터무결성보장
- 영구적변경전 데이터변경사항 확인가능
- 논리적 연관작업을 그룹핑하여 처리가능


## SAVEPOINT
- ```sql
  SAVEPOINT SVPT1;
  ```
- ```sql
  ROLLBACK TO SVPT1;
  ```

SQLServer
- ```sql
  SAVE TRANSACTION SVTR1;
  ```
- ```sql
  ROLLBACK TRANSACTION SVTR1;
  ```


정리
- TCL대상
  - INSERT
  - UDPATE
  - DELETE
- DML▶️수동커밋
- DDL▶️자동커밋
- 정상종료▶️자동커밋
  - SQLServer트랜잭션▶️자동커밋
- 이상종료▶️자동롤백
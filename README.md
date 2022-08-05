# AP-PreservationPrediction

### 22.08.05
- 티움넷 실제값 매칭 API 개발
  - 기존에 있는 처방 입력하기 프로세스를 이용하여 하되 쿼리문을 수정중
  - 쿼리문 수정 완료되면 실제값을 가져오기 위한 update 쿼리문 작성
    - h_prd_test_rq_mstr테이블에 매칭 시켜주면 됨.
    - 매칭 되는 컬럼은 3가지(PRD_UNQ_CD, ver, TEST_RSLT_NO)

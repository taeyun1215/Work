# AP-PreservationPrediction

### 22.08.05
#### DW 실제값 매칭(티움넷) API 개발
(진행)
  - 기존에 있는 처방 입력하기 프로세스를 이용하여 하되 쿼리문을 수정중.
  - 쿼리문 수정 완료되면 실제값을 가져오기 위한 update 쿼리문 작성.
    - h_prd_test_rq_mstr테이블에 매칭 시켜주면 됨.
    - 매칭 되는 컬럼은 3가지(PRD_UNQ_CD, ver, TEST_RSLT_NO)
---

### 22.08.07
#### DW 실제값 매칭 API(티움넷) 개발
(진행)
- dbeaver로 update 쿼리문 확인해야함. (실제값이 업데이트 되는지)
- 나머지 테이블(h_psvn_test_psve_pres_mstr, psvn_tium_prd_key)도 확인해야함.

(완료)
- 쿼리문 수정 완료.
- 쿼리문 update 작성 완료.
---

### 22.08.08
#### DW 실제값 매칭 API(처방 입력하기) 개발
(진행)
- 의뢰번호, 방부코드를 입력할 수 있음. -> 연구원분들이 이미 알고 있다는 가정하에
- 이미 존재하는 의뢰번호와 방부코드로 실제값을 매칭 시켜줘야함.

(완료)
- dbeaver로 update 쿼리문 확인해야함. (실제값이 업데이트 되는지)
- 나머지 테이블(h_psvn_test_psve_pres_mstr, psvn_tium_prd_key)도 확인해야함.
---

### 22.08.09
#### DW 실제값 매칭 API(처방 입력하기) 개발
(진행)
- 업데이트 쿼리문 코드에 작성시 나오는 오류 해결하기.
- 오류 해결하면 history/modify-history에서 "수정" 클릭후 데이터가 제대로 들어오는지 확인하기.
(완료)
- 업데이트 쿼리문 작성 완료.
- dbeaver에 업데이트 쿼리문 제대로 실행되는지 확인 완료.
---


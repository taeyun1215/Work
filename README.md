# AP-PreservationPrediction

### 22.08.05
#### (진행) @DW 실제값 매칭(티움넷) API 개발
  - 기존에 있는 처방 입력하기 프로세스를 이용하여 하되 쿼리문을 수정중.
  - 쿼리문 수정 완료되면 실제값을 가져오기 위한 update 쿼리문 작성.
    - h_prd_test_rq_mstr테이블에 매칭 시켜주면 됨.
    - 매칭 되는 컬럼은 3가지(PRD_UNQ_CD, ver, TEST_RSLT_NO)
    
---

### 22.08.07
#### (진행) @DW 실제값 매칭 API(티움넷) 개발
- dbeaver로 update 쿼리문 확인해야함. (실제값이 업데이트 되는지)
- 나머지 테이블(h_psvn_test_psve_pres_mstr, psvn_tium_prd_key)도 확인해야함.

#### (완료) @DW 실제값 매칭 API(티움넷) 개발
- 쿼리문 수정 완료.
- 쿼리문 update 작성 완료.

---

### 22.08.08
#### (진행) @DW 실제값 매칭 API(처방 입력하기) 개발
- 의뢰번호, 방부코드를 입력할 수 있음. -> 연구원분들이 이미 알고 있다는 가정하에
- 이미 존재하는 의뢰번호와 방부코드로 실제값을 매칭 시켜줘야함.

#### (완료) @DW 실제값 매칭 API(처방 입력하기) 개발
- dbeaver로 update 쿼리문 확인해야함. (실제값이 업데이트 되는지)
- 나머지 테이블(h_psvn_test_psve_pres_mstr, psvn_tium_prd_key)도 확인해야함.

---

### 22.08.09
#### (진행) @DW 실제값 매칭 API(처방 입력하기) 개발
- 업데이트 쿼리문 코드에 작성시 나오는 오류 해결하기.
- 오류 해결하면 history/modify-history에서 "수정" 클릭후 데이터가 제대로 들어오는지 확인하기.

#### (완료) @DW 실제값 매칭 API(처방 입력하기) 개발
- 업데이트 쿼리문 작성 완료.
- dbeaver에 업데이트 쿼리문 제대로 실행되는지 확인 완료.

---

### 22.08.10

#### (진행) @DW 실제값 매칭 API(처방 입력하기) 개발
- 따라서 실제값 매칭이 불가하여 다른 데이터를 가져와야하므로 아모레퍼시픽측에 이메일(이수진 매니저님)을 보내야함.
  - 이메일 보내기 전 수정사항이 잘 맞는지 확인하기.
- history/modify-history에서 "수정" 클릭후 데이터가 제대로 들어오는지 확인하기.

#### (완료) @DW 실제값 매칭 API(처방 입력하기) 개발
- 업데이트 쿼리문 코드에 작성시 나오는 오류 해결하기.
- "수정" 클릭시 입력할 수 있는 데이터(의뢰번호, 방부코드)로는 실제값 매칭이 불가함.
  - 방부코드는 실제값 테이블에 있기에 매칭이 가능하지만 의뢰번호는 없기에 불가함. 
  - 따라서 "의뢰번호"가 아닌 "시험접수번호"를 사용하여 실제값 테이블에 매칭함.
 
---

### 22.08.11
#### (진행) @DW 실제값 매칭 API(처방 입력하기) 개발
- 따라서 실제값 매칭이 불가하여 다른 데이터를 가져와야하므로 아모레퍼시픽측에 이메일(이수진 매니저님)을 보내야함.
  - 이메일 보내기 전 수정사항이 잘 맞는지 확인하기.
- history/modify-history에서 "수정" 클릭후 데이터가 제대로 들어오는지 확인하기.

#### (진행) @로그인시 비밀번호를 2번 이상 틀리게 되면 더이상 로그인이 불가능한 버그 수정하기.
- 웹 페이지에서는 제대로 되는데 postman에서는 false이 뜨는 버그 수정하기.

#### (완료) @로그인시 비밀번호를 2번 이상 틀리게 되면 더이상 로그인이 불가능한 버그 수정하기.
- 로그인시 어떤 동작을 하는지 확인하기, 코드 로직 이해하기.
- 해당 코드에 문제로 판단
  - password가 where조건문에 통과되지 않아 생기는 문제로 확인.
  - 코드 수정 완료.

---

### 22.08.12

#### (진행) @GCP 서버에 배포하기.
- GCP서버 폴더 remote git url 변경하기.
- pm2로 배포하기.

#### (완료) @로그인시 비밀번호를 2번 이상 틀리게 되면 더이상 로그인이 불가능한 버그 수정하기
- 웹 페이지에서는 제대로 되는데 postman에서는 false이 뜨는 버그 수정하기.

#### (완료) @DW 실제값 매칭 API(처방 입력하기) 개발
- 실제값 매칭이 불가하여 다른 데이터를 가져와야하므로 아모레퍼시픽측에 이메일 보냄.

---

### 22.08.16

#### (진행) @GCP 서버에 배포하기.
- pm2로 배포하기
  - package.json 파일에서 오류가 나서 고치는중.

#### (진행) @DW 데이터를 확인하기 위한 Python Code Checking
- 코드상 DB url 바꾸기.
- 실행이 된 후 DB에서 확인하기.

#### (완료) @DW 데이터를 확인하기 위한 DB Setting
- DB query를 이용하여 DB Setting 완료.
  - [x] table
  - [x] function
  - [x] sequences

---

### 22.08.17

#### (진행) @아모레 화상회의 후 안건 test
- 안건들로는 진행이 불가능하여 다른 매칭법을 찾는중.

#### (완료) @아모레 화상회의 후 안건 test
- 티움넷에서 불러오기 했을 경우 방부성분으로도 매칭이 가능한지.
  - 가능하지만 절반이 실제값 매칭이 불가능함.
- 티움넷에서 불러오기 했을 경우 시험 접수 번호로도 매칭이 가능한지.
  - 티움넷 테이블에는 시험 접수번호가 없어서 불가능
  
#### (대기) @GCP 서버에 배포하기.
- pm2로 배포하기.
  - package.json 파일에서 오류가 나서 고치는중.

#### (대기) @DW 데이터를 확인하기 위한 Python Code Checking
- 코드상 DB url 바꾸기.
- 실행이 된 후 DB에서 확인하기.

---

### 22.08.18

#### (진행) @처방 입력하기 프로세스
- 협의된 시험 접수 번호로 매칭

#### (진행) @티움넷 처방 불러오기 프로세스
- 안건 2가지가 안 되므로 새로운 방법을 찾는중.
  - SRNO로 매칭하기
    - d_psvn_test_psve_pres_mstr -> SRNO
    - d_psvn_test_sn_rslt_mstr -> SN
  - PSVE_NM로 매칭하기
    - d_psvn_test_psve_pres_mstr -> PSVE_NM

#### (완료) @티움넷 처방 불러오기 프로세스
- 처방 성분으로 매칭하기 (불가능)
- 시험 접수 번호로 매칭하기 (불가능)

#### (대기) @GCP 서버에 배포하기.
- pm2로 배포하기.
  - package.json 파일에서 오류가 나서 고치는중.

#### (대기) @DW 데이터를 확인하기 위한 Python Code Checking
- 코드상 DB url 바꾸기.
- 실행이 된 후 DB에서 확인하기.

---

### 22.08.19

#### (진행) @티움넷 처방 불러오기 프로세스
- 코드에서 구현중.
- 로컬에서도 확인이 가능하게 테스트 환경 구축중.

#### (진행) @처방 입력하기 프로세스
- 협의된 시험 접수 번호로 매칭.

#### (완료) @티움넷 처방 불러오기 프로세스
- 안건 2가지가 안 되므로 새로운 방법을 찾는중.
  - SRNO로 매칭하기
    - d_psvn_test_psve_pres_mstr -> SRNO
    - d_psvn_test_sn_rslt_mstr -> SN
  - PSVE_NM로 매칭하기
    - d_psvn_test_psve_pres_mstr -> PSVE_NM
- 중복되는 방부코드가 나오지만 distinct, limit 1를 사용하여 중복제거함.
- 업데이트 쿼리문 작성완료.
  - DB에서 업데이트 쿼리문이 제대로 작성하는지 확인 완료.

#### (대기) @GCP 서버에 배포하기.
- pm2로 배포하기.
  - package.json 파일에서 오류가 나서 고치는중.

#### (대기) @DW 데이터를 확인하기 위한 Python Code Checking
- 코드상 DB url 바꾸기.
- 실행이 된 후 DB에서 확인하기.

---

### 22.08.22

#### (진행) @티움넷 처방 불러오기 프로세스
- 코드에서 구현중
  - 업데이트 쿼리문 작동함.
- 이상한 점들이 몇가지 있음.
  - srno는 데이터를 입력했을 때 그 순서인데, 이 순서가 실제값이 맞는건지?
  - 로컬환경에서는 왜 확인이 불가한지.

#### (진행) @처방 입력하기 프로세스
- 협의된 시험 접수 번호로 매칭.
  - 업데이트 쿼리문 작성중.

#### (대기) @GCP 서버에 배포하기
- pm2로 배포하기.
  - package.json 파일에서 오류가 나서 고치는중.

#### (대기) @DW 데이터를 확인하기 위한 Python Code Checking
- 코드상 DB url 바꾸기.
- 실행이 된 후 DB에서 확인하기.

---

### 22.08.23

#### (진행) @티움넷 처방 불러오기 프로세스
- 업데이트 쿼리문 오류발생.
  - DB에서는 업데이트가 되지만 프론트도 돌리면 될 때가 있고 안 될 때가 있음.
  - 오류 확인중.

#### (진행) @처방 입력하기 프로세스
- 협의된 시험 접수 번호로 매칭.
  - 업데이트 쿼리문 작성중.
  
#### (완료) @티움넷 처방 불러오기 프로세스
- DB에서 업데이트 확인 완료
- 코드 구현 완료.

#### (대기) @GCP 서버에 배포하기
- pm2로 배포하기.
  - package.json 파일에서 오류가 나서 고치는중.

#### (대기) @DW 데이터를 확인하기 위한 Python Code Checking
- 코드상 DB url 바꾸기.
- 실행이 된 후 DB에서 확인하기.

---

### 22.08.24

#### (진행) @처방 입력하기 프로세스
- 코드상 구현중.
  - 티움넷 프로세스 삭제후 진행중.

#### (완료) @처방 입력하기 프로세스
- 업데이트 쿼리문 작성 완료.
- DB 테스트 완료.
  
#### (완료) @티움넷 처방 불러오기 프로세스
- 업데이트 쿼리문 오류 수정 완료.
  - 비동기 처리 오류였음. 따로 공부할 예정.
- 로컬에서 업데이트 확인 완료.
  
#### (대기) @GCP 서버에 배포하기
- pm2로 배포하기.
  - package.json 파일에서 오류가 나서 고치는중.

#### (대기) @DW 데이터를 확인하기 위한 Python Code Checking
- 코드상 DB url 바꾸기.
- 실행이 된 후 DB에서 확인하기.

---

### 22.08.25

#### (진행) @처방 입력하기 프로세스
- 에러 수정중.
  - 웹 테이블(h_psvn_test_sn_rslt_mstr)에 실제값이 제대로 매칭이 되는데 history에서는 실제값이 안 나옴.
  - 처방 입력하기 프로세스에서 데이터를 저장하면 서버 연결이 끊기는 오류
    - dataSimulatingstep4에서 의뢰번호를 입력하면 끊김.

#### (완료) @처방 입력하기 프로세스
- 코드 구현 완료.
  
#### (대기) @GCP 서버에 배포하기
- pm2로 배포하기.
  - package.json 파일에서 오류가 나서 고치는중.

#### (대기) @DW 데이터를 확인하기 위한 Python Code Checking
- 코드상 DB url 바꾸기.
- 실행이 된 후 DB에서 확인하기.

---

### 22.08.26

#### (진행) @stg서버에 있는 데이터 로컬로 옮기기
- dbeaver에서 insert문 추출 완료.
- 로컬환경에 insert문 입력
  - 그전에 처방 입력하기 프로세스 dataSimulatingstep4에서 의뢰번호를 입력하면 끊김 현상 해결하기.
  
#### (진행) @처방 입력하기 프로세스
- 에러 수정중.
  - 처방 입력하기 프로세스에서 데이터를 저장하면 서버 연결이 끊기는 오류.
    - dataSimulatingstep4에서 의뢰번호를 입력하면 끊김.
  - 실제값은 매칭이 되지만 판정값이 나오지 않는 오류.

#### (완료) @처방 입력하기 프로세스
- 에러 수정 완료.
  - 웹 테이블(h_psvn_test_sn_rslt_mstr)에 실제값이 제대로 매칭이 되는데 history에서는 실제값이 안 나옴.
  
#### (대기) @GCP 서버에 배포하기
- pm2로 배포하기.
  - package.json 파일에서 오류가 나서 고치는중.

#### (대기) @DW 데이터를 확인하기 위한 Python Code Checking
- 코드상 DB url 바꾸기.
- 실행이 된 후 DB에서 확인하기.

---

### 22.08.29

#### (진행) @처방 입력하기 프로세스
- 에러 수정중.
  - 처방 입력하기 프로세스에서 데이터를 저장하면 서버 연결이 끊기는 오류.
    - dataSimulatingstep4에서 의뢰번호를 입력하면 끊김.

#### (완료) @처방 입력하기 프로세스
- 에러 수정 완료.
  - 실제값은 매칭이 되지만 판정값이 나오지 않는 오류.
  - 일치여부가 맞지 않는 오류.
  
#### (대기) @GCP 서버에 배포하기
- pm2로 배포하기.
  - package.json 파일에서 오류가 나서 고치는중.

#### (대기) @DW 데이터를 확인하기 위한 Python Code Checking
- 코드상 DB url 바꾸기.
- 실행이 된 후 DB에서 확인하기.

#### (대기) @stg서버에 있는 데이터 로컬로 옮기기
  
---

### 22.08.30

#### (진행) @처방 불러오기 프로세스
- 에러 수정중.
  - 처방 불러오기 프로세스에서 데이터를 저장하면 실제값이 업데이트가 안 되는 오류.
    - 원인 파악 완료.
    - 해당 쿼리문 수정중.

#### (진행) @처방 입력하기 프로세스
- 에러 수정중.
  - 처방 입력하기 프로세스에서 데이터를 저장하면 서버 연결이 끊기는 오류.
    - dataSimulatingstep4에서 의뢰번호를 입력하면 끊김.

#### (완료) @스마트 팜 차출

#### (대기) @GCP 서버에 배포하기.
- pm2로 배포하기.
  - package.json 파일에서 오류가 나서 고치는중.

#### (대기) @DW 데이터를 확인하기 위한 Python Code Checking
- 코드상 DB url 바꾸기.
- 실행이 된 후 DB에서 확인하기.

#### (대기) @stg서버에 있는 데이터 로컬로 옮기기

---

### 22.08.31

#### (진행) @티움넷 프로세스
- 티움넷에서 실험 후 DW 테이블에 데이터가 들어오는데 시간이 걸리므로, 티움넷 실험후 바로 데이터를 넣어 예측을 하게 된다면 실제값이 없어서 업데이트가 불가능함.
  - DataSimulatingStep4에서 저장할 때 실제값이 존재하는 DW 테이블에 아직 데이터가 저장되지 않아서 문제가 발생함.
  - 해결방안은 데이터를 저장(history/reg)하는 api에서 update를 하는것이 아니라 리스트(history/list) 만들어주는 api에서 update를 해줘야 할 것 같음.

#### (완료) @처방 불러오기 프로세스
- 오류 인줄 알았지만 오류가 아닌걸로 판정.  
  - res.json 형태를 중첩해서 받아 그렇게 된 거였음, 기존 있던 코드는 연구원분들이 방부성분과 값을 실제 있는 값으로 매칭 해줬음.  
  - 방부성분과 치수가 0.0001이라도 다르면 불가능함.  
- 기존 프로세스를 유지하는 방식으로 해결함.  
  
#### (완료) @처방 입력하기 프로세스
- 오류 인줄 알았지만 오류가 아닌걸로 판정.  
  - res.json 형태를 중첩해서 받아 그렇게 된 거였음.  
- 처방 입력하기와 처방 불러오기가 동일한 api를 사용하므로 구분을 지어줘서 해결하였음. 구분값 PSVN_I  

#### (대기) @GCP 서버에 배포하기
- pm2로 배포하기.
  - package.json 파일에서 오류가 나서 고치는중.

#### (대기) @DW 데이터를 확인하기 위한 Python Code Checking
- 코드상 DB url 바꾸기.
- 실행이 된 후 DB에서 확인하기.

#### (대기) @stg서버에 있는 데이터 로컬로 옮기기
  
---

### 22.09.01

#### (진행) @티움넷 프로세스
- 오류 수정중.
  - history/list 웹에 중복된 데이터가 나오는 오류.
  - history/list 두번 클릭해야 업데이트가 되는 오류.

#### (완료) @티움넷 프로세스
- 기존 업데이트 방식 : 티움넷 불러오기로 데이터 저장후 바로 방부코드, 실제값을 업데이트 함.
- 수정된 업데이트 방식 : 티움넷 불러오기로 데이터 저장후 history/list api 호출시 실제값만 업데이트를 함.
  - 실제값만 업데이트 하는 이유 : 임시로 받은 방부코드를 유지하고 데이터 저장시 insert되는 테이블에 실제 방부코드를 받을 수 있는 컬럼을 추가함.
- h_psvn_test_sn_rslt_mstr, h_psvn_test_psve_pres_mstr 테이블에 real_rslt_no(실제 방부코드)컬럼을 추가함.
- history/list api 호출시 티움넷 프로세스는 real_rslt_no로 다른 테이블에 매핑되게 수정 완료.
- 판정값, 일치여부도 나오게 수정 완료.

#### (대기) @GCP 서버에 배포하기
- pm2로 배포하기.
  - package.json 파일에서 오류가 나서 고치는중.

#### (대기) @DW 데이터를 확인하기 위한 Python Code Checking
- 코드상 DB url 바꾸기.
- 실행이 된 후 DB에서 확인하기.

#### (대기) @stg서버에 있는 데이터 로컬로 옮기기
  
---

### 22.09.02

#### (진행) @처방 불러오기
- 테스트 진행하기
  - 정확한 처방성분과 그 값을 입력해서 매칭이 되는지 확인하기.

#### (완료) @처방 입력하기
- 기능 수정 완료.
  - test_rslt_no에서 real_rslt_no로 수정함.

#### (완료) @티움넷 프로세스
- 오류 수정 완료.
  - history/list 웹에 중복된 데이터가 나오는 오류.
    - groupBy를 추가하여 오류를 수정함.
  - history/list 두번 클릭해야 업데이트가 되는 오류.
    - global.pool.query 中 update쿼리가 먼저 실행이 되게 수정함.

#### (대기) @GCP 서버에 배포하기
- pm2로 배포하기.
  - package.json 파일에서 오류가 나서 고치는중.

#### (대기) @DW 데이터를 확인하기 위한 Python Code Checking
- 코드상 DB url 바꾸기.
- 실행이 된 후 DB에서 확인하기.

#### (대기) @stg서버에 있는 데이터 로컬로 옮기기
  
---

### 22.09.05

#### (진행) @티움넷 프로세스
- history/list 두번 클릭해야 업데이트가 되는 오류.
  - 해당 오류는 일단 억지로 update쿼리가 먼저 실행되도록 하였음.
  - async, await를 이해후 코드 리팩토링 진행.

#### (완료) @처방 불러오기
- 테스트 진행 확인 완료.
  - 정확한 처방성분과 그 값을 입력해서 매칭이 되는지 확인하기.

#### (대기) @GCP 서버에 배포하기
- pm2로 배포하기.
  - package.json 파일에서 오류가 나서 고치는중.

#### (대기) @DW 데이터를 확인하기 위한 Python Code Checking
- 코드상 DB url 바꾸기.
- 실행이 된 후 DB에서 확인하기.

#### (대기) @stg서버에 있는 데이터 로컬로 옮기기

---
  
### 22.09.06

#### (진행) @DW 데이터를 확인하기 위한 Python Code Checking
- 코드상 DB url 바꾸기.
- 실행이 된 후 DB에서 확인하기.

#### (대기) @GCP 서버에 배포하기
- pm2로 배포하기.
  - package.json 파일에서 오류가 나서 고치는중.

#### (대기) @stg, prd server DB에 컬럼 추가
- h_psvn_test_sn_rslt_mstr, h_psvn_test_psve_pres_mstr 테이블에 real_rslt_no(실제 방부코드) 컬럼 추가하기
- 티움넷 불러오기, 처방 입력하기 테스트 진행하기.

---

### 22.09.13

#### (진행) @DW 데이터를 확인하기 위한 Python Code Checking
- dataSimulation으로 데이터 입력하고 History 확인하기.
- History/list에서 티움넷, 처방 불러오기가 제대로 수정되는지 확인하기.

#### (완료) @DW 데이터를 확인하기 위한 Python Code Checking
- 코드상 DB url 바꾸기.
- 실행이 된 후 DB(기존 : public, 변경 : pps)에서 확인하기.

#### (완료) @GCP 서버에 배포하기
- pm2로 배포하기.

#### (대기) @stg, prd server DB에 컬럼 추가
- h_psvn_test_sn_rslt_mstr, h_psvn_test_psve_pres_mstr 테이블에 real_rslt_no(실제 방부코드) 컬럼 추가하기
- 티움넷 불러오기, 처방 입력하기 테스트 진행하기.

---

### 22.09.14

#### (진행) @DW 파일 확장자명 이슈
- 확장자명이 파일마다 다르기에 메일을 작성해야함.

#### (진행) @stg서버 테스트
- 티움넷 불러오기 확인중.
- 처방 입력하기 확인 완료.

#### (완료) @DW 데이터를 확인하기 위한 Python Code Checking
- dataSimulation으로 데이터 입력하고 History 확인하기.
- History/list에서 티움넷, 처방 불러오기가 제대로 수정되는지 확인하기.

#### (완료) @stg, prd server DB에 컬럼 추가
- h_psvn_test_sn_rslt_mstr, h_psvn_test_psve_pres_mstr 테이블에 real_rslt_no(실제 방부코드) 컬럼 추가하기

---

### 22.09.15

#### (진행) @DW 데이터 확인을 위한 insert_parquest.py 확인
- 이슈체크
  - 파일 확장자명 이슈인줄 알았으나 서버에서 로컬로 떨굴때 파일 확장자명이 달라짐, 따라서 서버에서는 제대로 동작하고 있음.
  - parquest 파일의 데이터가 동일한 키값으로 이미 존재하고 있으면 업데이트가 안 되고 데이터가 DW에 저장되지 않음.
  - insert 되는 데이터가 실제값 테이블 기준으로 키값(PRD_UNQ_CD, VER, TEST_RSLT_NO)이 동일한게 존재한다면 업데이트가 되지 않음.
    - ex) 기존 DB = TR20211223, 1, A746, 0.1, 3, 4.2 // parquest 파일 = TR20211223, 1, A746, 0.4, 2, 1.7
    - 위와 같은 상황이라면 parquest 파일의 값으로 바꿔줘야하는데 기존 DB에 이미 해당 키값이 존재하므로 insert가 되지 않고 있다.
    - 그리고 파이썬 파일에는 업데이트를 따로 해주지 않음.
- 해결 방안
  - parquest 파일에 과거 데이터가 쌓이는지 확인하기
    - 만약 과거 데이터가 쌓인다면 그 전 데이터를 다 삭제후 다시 데이터 insert해주면 됨.
  - parquest 파일의 데이터가 기존 DB에 존재한다면 기존 DB에 있는 걸 update시켜주기.

#### (대기) @stg서버 테스트
- 티움넷 불러오기 확인중.
  - 위 insert_parquest.py 확인 후 데이터가 제대로 들어가면 그 후 테스트 진행하기.
- 처방 입력하기 확인 완료.

---

### 22.09.16

#### (진행) @DW 데이터 확인을 parquest 파일 확인
- 위 이슈는 이슈리스트 기준 6-1 방부예측 결과 이슈와 동일함.
  <img width="595" alt="image" src="https://user-images.githubusercontent.com/65766105/190680103-e6b49881-6653-45e5-8755-84384b1dc632.png">

- 과거 데이터가 쌓이는지 parquest파일을 확인해야함.
  - 과거 데이터가 존재한다면 데이터를 다 삭제하고 다시 밀어넣으면 됨.
  - 만약 없다면 기존 데이트를 업데이트 해주는 방식으로 해야함.

#### (완료) 확장자명 이슈, 방부예측 결과 이슈 메일 답변
- 질문 2가지
- -2, -3 컬럼중 둘중 하나만 데이터가 들어가야함.  
&rarr; 기존에는 데이터가 null값이어도 0으로 받기로 하였음. 하지만 이번 요구사항은 null은 공백으로 두는 걸로 변경.  

- A7 데이터는 없는 것이 맞습니다. 그러므로 해당 데이터는 특이사항이 아닐경우 비워두는게 맞습니다. (박태훈 연구원님)  
&rarr; 원본 parquest파일을 확인해보니 A7 데이터는 실제로 있었습니다. 이 부분이 parquest파일의 문제인지, 아니면 A7 데이터가 원래 있는게 맞는지는 아모레와 협의가 필요함.

  - 티움넷 사이트
  <img width="589" alt="스크린샷 2022-09-16 오후 10 16 36" src="https://user-images.githubusercontent.com/65766105/190647810-01709b9d-8a1b-4923-bf7d-ea9b29c1b51f.png">

  - 저희 측 웹 사이트
  <img width="589" alt="스크린샷 2022-09-16 오후 10 15 25" src="https://user-images.githubusercontent.com/65766105/190647628-fa2fd85d-25c2-4ecc-bb09-896e8a8de8f7.png">

#### (완료) @stg서버 테스트
- 티움넷 불러오기 확인중.
  - prd 서버 데이터를 stg 서버에 insert하여 테스트 진행 완료함.
  
---

### 22.09.19

#### (진행) @DW 데이터 확인을 parquet 파일 확인
- 과거 데이터가 존재한다면 데이터를 다 삭제하고 다시 밀어넣으면 됨.   
  -> 과거 데이터가 쌓이고 있음. 아모레에서 보내주는 데이터가 며칠씩 뒤에 들어옴.
  - 8월 12일 parquest파일, 8월 10일 날짜에 로그감소값이 존재하지 않음.
  ![image](https://user-images.githubusercontent.com/65766105/190960383-2e9f8bda-1595-4932-83e0-154f8403863b.png)
  - 9월 19일 parquest파일, 8월 10일 날짜에 로그감소값이 존재함.
  ![image](https://user-images.githubusercontent.com/65766105/190961126-f7efd20b-b38a-49d0-8851-bac6bbd57636.png) 
  - 위 두 사진을 보면 며칠 뒤에 8월 10일 날짜 데이터가 들어온다는 걸 확인할 수 있다.
- 따라서 위 상황을 정성민님(DW 담당자)께 전화통화 드려야함.

#### (완료) @방부결과 -2, -3 이슈 
- 기존에는 -2, -3에 0 or null 은 모두 0으로 받기로 하였음.
- 메일 안건상 이제는 null은 공백으로 표기하기로 함.
- front에서 수정 완료.

---

### 22.09.20

#### (진행) 방부결과 오류: 방부처방 데이터 0 표기되는 이슈 (이슈리스트 1번)
- @insert_parquet.py 파일 확인
- 원인 파악 완료
  - 테이블 기준으로 같은 키값이 들어오면 업데이트를 안 해주고 있음.
  - ON CONFLICT ON CONSTRAINT "{pk}" DO NOTHING'을 사용함.
- 해결 방안
  - sql 쿼리문을 수정해야함. 
  - 같은 키값에 데이터가 들어와도 업데이트가 되게 해줘야함.

#### (진행) @DW 데이터 확인을 parquet 파일 확인
- A7 데이터 이슈는 티움넷 자체 프로세스를 이용하는거라 협의 필요함.
- 메일 내용 정리중.
- 과거 데이터가 쌓이는 걸 확인했으니 local, stg, prd 모두 데이터를 delete하고 insert하기.

#### (완료) @정성민님과 화상회의 완료
- A7 데이터 이슈
- 부등호 표현 이슈
- parquet 파일 데이터 딜레이 이슈
- parquet 과거 데이터가 쌓이는지 확인
- 데이터 숫자 색상 표기

#### (완료) @prd 서버 배포 완료
- 테스트 진행 완료.
  - [X] 처방 불러오기
  - [X] 처방 입력하기
  - [X] 티움넷 처방 불러오기

---

### 22.09.21

#### (진행) 방부결과 오류: 방부처방 데이터 0 표기되는 이슈 (이슈리스트 1번)
- sql 쿼리문을 수정 완료.
- CREATEDT, UPDATEDT도 같이 업데이트 되고 있음.
- CREATEDT, UPDATEDT는 업데이트가 안 되게 수정해야함.

#### (진행) @DW 데이터(A7) 확인을 위한 parquet 파일 확인
- A7 데이터 이슈는 티움넷 자체 프로세스를 이용하는거라 협의 필요함.
- 메일 내용 정리 완료. (9/21)
- 답변오는데로 작업 진행 예정.

#### (대기) local, stg, prd
- parquest파일에 과거 데이터가 쌓이는지 확인 완료.
- 과거 데이터 delete후 insert하기.

---

### 22.09.22

#### (진행) 방부결과 오류: 방부처방 데이터 0 표기되는 이슈 (이슈리스트 1번)
- sql 쿼리문을 수정 완료.
- CREATEDT, UPDATEDT도 같이 업데이트 되고 있음.
- 위 두개 컬럼은 잘 안 쓰니까 같이 업데이트 시키게끔 함.
- 단, 다른테이블에서 안 되는 경우가 있음.
  - split로 나눠줬는데 제대로 안 나눠지는 경우가 있음.
  - 해당 부분 split에 특정 문자 수정해야함.

#### (진행) @DW 데이터(A7) 확인을 위한 parquet 파일 확인
- A7 데이터 이슈는 티움넷 자체 프로세스를 이용하는거라 협의 필요함.
- 선택지 두개
  - -2, -3 값이 없을 경우에 무시하도록 구현하기.
  - 2차 곰팡이 시험을 거의 안 하니 조건없이 무조건 7일차 곰팡이값은 무시하도록 구현하기.
    - 단, 두개항목 모두 곰팡이(A)의 경우에는 14일차, 28일차로만 시뮬레이션하도록 구현
- 항목 두개중 2번 선택으로 메일 정리 완료. (9/22)

#### (대기) local, stg, prd
- parquest파일에 과거 데이터가 쌓이는지 확인 완료.
- 과거 데이터 delete후 insert하기.

---

### 22.09.23

#### (진행) @DW 데이터(A7) 확인을 위한 parquet 파일 확인
- DB에 A7 데이터 default를 0으로 설정하기.

#### (완료) 방부결과 오류: 방부처방 데이터 0 표기되는 이슈 (이슈리스트 1번)
- 해결 완료.
  ```python
  values = values.split('\'),')
  ```
- DB에서 확인 완료.

#### (대기) local, stg, prd
- parquest파일에 과거 데이터가 쌓이는지 확인 완료.
- 과거 데이터 delete후 insert하기.

---

### 22.09.26

#### (진행) @전체 DW 테이블 확인하기
- insert_parquest 파일 배포 완료.
- 내일(9/27) stg서버 db 확인하기.

#### (완료) @DW 데이터(A7) 이슈
- dataSimulating/psvn_result에서만 A7 데이터를 사용하고 있음.
- 해당 API에 밑에 코드를 넣어서 수정을 해줬음.
  ```javascript
  result.rows[0].json_build_object.MICR_LOG_DEC_A7 = 0
  ```

#### (완료) @DW 데이터(A7) 이슈, parquest파일 이슈 stg서버 배포 완료

---

### 22.09.27

#### (진행) @전체 DW 테이블 확인하기
- 내일(9/28) stg서버 db 확인하기.

#### (진행) @stg에 올라간 insert_parquest파일 이슈
- syntax error인데 로컬 코드와 다른점이 없음.
- 원인 분석

#### (완료) @amore계정생성 완료.

---

### 22.09.28

#### (진행) @전체 DW 테이블 확인하기
- 내일(9/28) stg서버 db 확인하기.

#### (진행) @stg에 올라간 insert_parquest파일 이슈
- 원인 파악 완료.
  - 내 로컬 디렉토리와 리눅스에 배포된 디렉토리가 달랐음.
- 리눅스에 배포된 디렉토리로 수정 완료.
- jenkins 권한 등록 후 stg, prd 배포 예정.

#### (진행) @jenkin, gitlab 권한 요청중.

---

### 22.09.29

#### (진행) 이슈리스트 13번
- 대시보드 이슈 파악하기.

#### (완료) @jenkin, gitlab 권한 요청중.

---

### 22.09.30

#### (진행) @Jenkin, GitLab 권한 완료.
- 방부예측 GitLab 권한 받기 (심유석 M)

#### (진행) @대시보드 일치율 이슈
- 인수인계 완료(분석팀)
- DataMonitor에 dashboard API 수정중

#### (진행) @A7 데이터 이슈
- Soucretree에 push하기

#### (진행) @전체 DW 테이블 확인하기
- GitLab 권한 받은 후 insert_parquest 재배포
- 재배포 후 DW테이블 체크하기

#### (대기) @amore 권한 받기
- 로컬 피씨 백업 완료
- 윈도우 업데이트 완료
- amore 기술지원센터 전화후 로컬피씨 권한 받기

---

22.10.04

#### (진행) @대시보드 일치율 이슈
- 인수인계 완료(분석팀)
- DataMonitor에 dashboard API 수정중

#### (완료) @전체 DW 테이블 확인하기

#### (완료) @A7 데이터 이슈
- Soucretree에 push하기

#### (완료) @Jenkin, GitLab 권한 완료.
- 방부예측 GitLab 권한 받기 (심유석 M)

#### (완료) @amore 권한 받기
- 로컬 피씨 백업 완료
- 윈도우 업데이트 완료
- amore 기술지원센터 전화후 로컬피씨 권한 받기

---

22.10.05

#### (진행) @대시보드 일치율 이슈
- 인수인계 완료(분석팀)
- DataMonitor에 dashboard API 수정중

#### (진행) @인턴 평가 발표
- ppt 만드는중


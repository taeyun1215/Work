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
- pm2로 배포하기
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
- pm2로 배포하기
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
- pm2로 배포하기
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

#### (대기) @GCP 서버에 배포하기.
- pm2로 배포하기
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

#### (대기) @GCP 서버에 배포하기.
- pm2로 배포하기
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
  
#### (대기) @GCP 서버에 배포하기.
- pm2로 배포하기
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
  
#### (대기) @GCP 서버에 배포하기.
- pm2로 배포하기
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
  
#### (대기) @GCP 서버에 배포하기.
- pm2로 배포하기
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
  
#### (대기) @GCP 서버에 배포하기.
- pm2로 배포하기
  - package.json 파일에서 오류가 나서 고치는중.

#### (대기) @DW 데이터를 확인하기 위한 Python Code Checking
- 코드상 DB url 바꾸기.
- 실행이 된 후 DB에서 확인하기.

#### (대기) @stg서버에 있는 데이터 로컬로 옮기기
- dbeaver에서 insert문 추출 완료.
- 로컬환경에 insert문 입력
  - 그전에 처방 입력하기 프로세스 dataSimulatingstep4에서 의뢰번호를 입력하면 끊김 현상 해결하기.

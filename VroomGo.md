# VRGX, VGP Balance 조회


- API : https://wv2v2nk1df.execute-api.us-east-2.amazonaws.com/CheckBalanceForThirdParty (POST)


- Request

  * Sample
{ 
    "Email": "koreanawesomeguy@gmail.com", 
    "PhoneNumber" : "821041139274", 
    "Caller" : "Vroomgo" 
}
  
  * Request body schema (application/json)
  
  요청 변수 | 설명 | 타입
  ------------ | ------------- | -------------
  MobileNumber | Vroomgo 회원 휴대폰번호 | String/필수
  Email | Vroomgo 회원 이메일 | String/필수
  Caller | Caller Service | String/필수
  
- Response Success

  * Sample 
{
    "status": "3000",
    "response": {
        "VRGX": "10.5",
        "VGP": "10"
    }
}
  
  * Response Schema (application/json)

  필드 | 설명 | 타입
  ------------ | ------------- | -------------
  status | 결과 상태 코드 (정상: 3000, 에러의 경우 https://github.com/coinville/Coconut/blob/master/Vroomgo/Error%20Code.md 참고) | String/필수
  response | 요청 결과 | String/필수
 
 
 # 회원 조회


- API : https://wx9did7o26.execute-api.us-east-2.amazonaws.com/CheckMemberForThirdParty (POST)


- Request

  * Sample
{ 
    "Email": "koreanawesomeguy@gmail.com", 
    "PhoneNumber" : "821041139274", 
    "Caller" : "Vroomgo" 
}
  
  * Request body schema (application/json)
  
  요청 변수 | 설명 | 타입
  ------------ | ------------- | -------------
  MobileNumber | Vroomgo 회원 휴대폰번호 | String/필수
  Email | Vroomgo 회원 이메일 | String/필수
  Caller | Caller Service | String/필수
  
- Response Success

  * Sample 
  {
      "status": 3000,
      "response": "OK"
  }
  
  * Response Schema (application/json)

  필드 | 설명 | 타입
  ------------ | ------------- | -------------
  status | 결과 상태 코드 (정상: 3000, 에러의 경우 https://github.com/coinville/Coconut/blob/master/Vroomgo/Error%20Code.md 참고) | String/필수
  response | 요청 결과 | String/필수
 

# Error Code

- Response Error
  
  * Sample
  {
      "status": "3100",
      "response": "Wrong Caller"
  }
  
  * Response Schema (application/json)

  에러 코드 | 에러 메시지 | 설명
  ------------ | ------------- | -------------
  "3100" | "Wrong Caller" | Caller Service 오류
  "3200" | "Not Member" | 회원가입이 되어있지 않음
  "3300" | "No Asset Information" | VRGX, VGP 자산 정보 없음


# VGP 결제


- API : https://n3x65ok2dd.execute-api.us-east-2.amazonaws.com/StorePaymentForThirdParty (POST)


- Request

  * Sample
{
    "Email": "koreanawesomeguy@gmail.com",
    "PhoneNumber" : "821041139274",
    "Caller" : "Vroomgo",
    "VGPUsage" : "10",
    "VGPBalance" : "100",
    "StoreInfo" : "Familymart",
    "Timestamp" : "1590934309"
}
  
  * Request body schema (application/json)
  
  요청 변수 | 설명 | 타입
  ------------ | ------------- | -------------
  MobileNumber | Vroomgo 회원 휴대폰번호 | String/필수
  Email | Vroomgo 회원 이메일 | String/필수
  Caller | Caller Service | String/필수
  VGPUsage | VGP 사용량 | String/필수
  VGPBalance | VGP 잔액 | String/필수
  StoreInfo | 가맹점 정보 | String/필수
  Timestamp | 결제일시  | String/필수
    
- Response Success

  * Sample 
  {
      "status": 3000,
      "response": "OK"
  }
  
  * Response Schema (application/json)

  필드 | 설명 | 타입
  ------------ | ------------- | -------------
  status | 결과 상태 코드 (정상: 3000, 에러의 경우 https://github.com/coinville/Coconut/blob/master/Vroomgo/Error%20Code.md 참고) | String/필수
  response | 요청 결과 | String/필수
 

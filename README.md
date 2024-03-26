# Final-Project-A09-
A09 최종 프로젝트

# 고유키 기록

넥슨 메이플스토리 API KEY : test_3b341b04580056706630a7005aa630353dc098849203dc369a4dcd875acf97c7c5c4379a7a07b52f361ffef5fab87a55

던파 API KEY : ZWBQ5Hcf27Dz494NprIOqSpXUZqubuLG

# 데이터 분석 목적 설정 초안
1. API 활용하여 데이터 분석 (넥슨 - 메이플, 네오플 - 던파, 라이엇 - 롤, tft)

## 03.26 알아낸 것들
1. 네오플 api 사이트에 들어가서 누르면 나오는 <Request URL> 란에 적혀있는 url 을 이용하면 사이트에서 직접 정보를 json 형태로
   반환시키는 것이 가능하다. 

   예문) 현재 랭킹 1위인 아이디 "뉴타입" 을 가진 유저를 전체 게임에서 조회하고자 한다면

         "https://api.neople.co.kr/df/servers/all/characters?characterName=뉴타입&apikey=ZWBQ5Hcf27Dz494NprIOqSpXUZqubuLG" 
         
         이런식으로 <Request URL> 에 적은 뒤에 요청 버튼을 누르면
         전체 서버에 있는 "뉴타입" 이라는 정보를 가진 유저들의 정보가 json 형식으로 반환된다
         요청 결과는 아래에 있는 Response Body 에서 확인이 가능하다

         내가 수정하기 전 원문은

         "https://api.neople.co.kr/df/servers/<serverId>/characters?characterName=<characterName>&jobId=<jobId>&jobGrowId=<jobGrowId>&isAllJobGrow=<isAllJobGrow>&limit=<limit>&wordType=<wordType>&apikey=<apikey>"

         이런식으로 되어있었는데, 필수로 채워야하는 파라미터인 severId 와 characterName 을 제외하고는 완전히 지워주어야
         정상적인 요청이 가능하다. 이제 이것을 파이썬으로 불러서 리스트에 추가하는 방법을 알아봐야한다...

2. 앞의 예문처럼 url 을 작성해서 변수에 저장을 해준 뒤에,

   url = "https://api.neople.co.kr/df/servers/all/characters?characterName=뉴타입&apikey=ZWBQ5Hcf27Dz494NprIOqSpXUZqubuLG" 다음과 같이 url 변수에 저장해준다

   반환된 데이터를 텍스트 형식으로 변환 > json 형식으로 변환 > pandas 데이터 프레임으로 변환하여 테이블화 시킬 수 있음

   대부분의 정보 요청이 필수 파라미터인 severId 와 characterName 으로 가능하기 때문에, 위의 방식을 공통적으로 사용하는 것으로 캐릭터 장비 정보, 캐시 아이템 정보 등 대부분의 정보를 조회하는 것이 가능할 것이다.
   
   이제 캐릭터, 서버명을 크롤링해오는 법을 알아내야할 필요가 있다
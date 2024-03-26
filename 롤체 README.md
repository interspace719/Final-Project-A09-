# Final-Project-A09-
A09 최종 프로젝트 : 게임 데이터 분석

# 고유키 기록용

## 넥슨 메이플스토리 API KEY : test_3b341b04580056706630a7005aa630353dc098849203dc369a4dcd875acf97c7c5c4379a7a07b52f361ffef5fab87a55

## 던파 API KEY : ZWBQ5Hcf27Dz494NprIOqSpXUZqubuLG

## 라이엇 API 키 : RGAPI-51594ed7-aa70-4a72-b8bf-314c7f733d71


# 데이터 분석 목적 설정 초안
1. API 활용하여 데이터 분석 (넥슨 - 메이플, 네오플 - 던파, 라이엇 - 롤, tft)


## 라이엇 API 꺼내오는 방법 순서

1. 라이엇 데이터의 경우 3가지 순서를 거쳐야 함

2. 우선 유저를 특정할 수 있는 식별자인 puuid 를 추출해야함

3. puuid 를 추출하기 위해서는 우선 league/v1 API 에 저장되어있는 랭크별 닉네임 정보를 가져와야한다

4. /lol/summoner/v4/summoners/by-name/{summonerName} 이 API 를 활용해서 닉네임을 이용해 puuid 를 가져올 것이다

5. 각각의 닉네임을 넣으면서 그 유저의 puuid 를 추출해야한다 - 닉네임을 리스트로 만들고 for 문을 사용하면 쉽게 가능할 것이다

6. 원하는 구간을 설정하면 해당 구간의 결측치를 제거하고 닉네임 리스트를 추출하는 함수를 생성했다

7. /lol/summoner/v4/summoners/by-name/{summonerName} 이용하여, 닉네임 리스트를 넣으면 각 닉네임에 대응하는 puuid 리스트를
   반환하는 함수를 생성했다

8. 생성한 puuid 리스트로 game id 를 추출, 다음을 이용
   game_url = "https://Asia.api.riotgames.com/tft/" + f'match/v1/matches/by-puuid/{random_puu_id}/ids?count=20'
   
   # 여기서 'match/v1/matches/by-puuid/{random_puu_id}/ids?count=20' 앞에 f를 붙이는 이유

   ## "f"는 파이썬의 f-string입니다. f-string은 문자열 내에서 변수 값을 쉽게 사용할 수 있도록 해줍니다. f-string을 사용하면 문자열 안에 중괄호 {} 안에 변수를 넣을 수 있고, 해당 변수의 값이 그 위치에 삽입됩니다.

   ## 예를 들어, f'match/v1/matches/by-puuid/{puu_id}/ids?count=20'에서 {puu_id} 부분은 변수 puu_id의 값을 문자열 안에 삽입하는 것입니다. 이렇게 함으로써 동적인 문자열을 생성할 수 있습니다. 이전에는 문자열 포맷팅이나 문자열 연결 등을 사용하여 변수 값을 문자열에 포함시켰지만, f-string을 사용하면 더 간결하고 가독성이 좋은 코드를 작성할 수 있습니다.


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
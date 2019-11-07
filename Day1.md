# Day1

- Ice Breaking
- Chrome 개발자 도구 Networks 탭 활용하기
- 네이버 웹툰, 다음 웹툰 구조 분석하기



- 다음 웹툰 구조 및 url 분석을 통해 각 요일 웹툰 정보 크롤링하기

```python
# 1. 요청을 보내기 위한 requests 모듈을 import 한다.
# 모듈이 없을 경우 'pip install requests' 를 실행
import requests
import json
# 2. 요청을 보내기 위한 url을 변수에 저장한다.
url = "http://webtoon.daum.net/data/pc/webtoon/list_serialized/fri"
# 3. 해당 url에 요청을 보낸다.
response = requests.get(url)
# 4. 응답을 출력한다.
res = response.json()
print(res["data"][0])
```

- 멜론 티켓 url 분석을 통한 정보 획득하기
  - headers 정보 함께 넣어 정보 요청하기

```python
# 1. 요청을 보내기 위한 requests 모듈을 import 한다.
import requests
# 2. url에 주소를 저장한다.
url = "https://ticket.melon.com/offer/ajax/offerList.json?offerPosType=MAIN_B_CO_3"
# 3. 요청을 보내고 응답을 변수에 저장한다.
headers = {
    'User-Agent': 'Mozilla/5.0 (Windows NT 6.1; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/78.0.3904.87 Safari/537.36',
}
response = requests.get(url, headers=headers)
# 4. 변수에 저장된 내용을 출력한다.
print(response.text)
# (추가사항) 5. new! 공연, 2019 전국투어, 뮤지컬&연극
# 각 부분을 출력해보기
# [parameter 부분을 잘 확인할 것!]
```




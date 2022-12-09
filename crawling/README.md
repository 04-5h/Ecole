# SNS Crawling

## 1. 검색하고 싶은 단어 변경

search_word = "busan"

## 2. 검색하는 기간 변경

start_day = "2022-10-13"

end_day = "2022-10-14"


search_query = search_word + ' since:' + start_day + ' until:' + end_day

## 3. 처음부터 100개의 tweets를 취득
sliced_scraped_tweets = itertools.islice(scraped_tweets, 100)

## 4. Word Cloud를 위해 단어의 리스트 모든 단어를 한 문자열으로 연결
<img width="400" src="https://user-images.githubusercontent.com/80237293/206611746-507c71f6-f142-4ffa-be6b-fe03b7a9edd5.png" />

## 트윗이 긍정적인지 부정적인지 확인
<img width="240" src="https://user-images.githubusercontent.com/80237293/206611003-a338e52b-c02a-43f0-9135-ee08da650edc.png"/>


reference 서울대학교 빅테이터 혁신공유대학 Dr. 야마다 아키히코님

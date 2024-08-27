# aws-ticket-app
 
## ⚡기획의도⚡
**하나로 만든 데이터**를 API를 사용하여<br/>
볼 수 있도록 만들자<br/>

## ✌데이터셋 정보✌
해당 데이터는<br/>
[멜론](https://ticket.melon.com/concert/index.htm?genreType=GENRE_CON, '멜론 티켓')<br/>
[인터파크 티켓](https://tickets.interpark.com/contents/genre/concert, '인터파크 티켓')<br/>
[티켓링크](https://www.ticketlink.co.kr/performance/14, '티켓링크')<br/>
[Yes24](http://ticket.yes24.com/New/Genre/GenreMain.aspx?genre=15456, 'yes24 티켓')<br/>
에서 스크래핑하여 데이터를 가공하였습니다<br/><br/>

## 👍서버 개발 과정👍
+ 먼저 기획의도에 따라 순서를 정함<br/>
1. **Serverless로 서버 배포**할 것<br/>
2. **Docker 활용** 하여 **패키징**할 것<br/>
3. **GitActions** 사용하여 **자동 배포** 할 것<br/>
4. **애자일방법론**에 따라 API 제작, 로컬에서 테스트 후 서버 배포후 재검토의 과정을 거칠것<br/>
5. 회원가입/로그인시 **jwt 인증토큰 발행**<br/>
5-1. 하지만 비회원도 이용 가능하게 하기위해 좋아요기능 관련 API 이외의 API에서는 **JWT 토큰 검증**을 자동이 아닌 **수동**으로 **검사 진행**하여<br/>
   JWT 인증토큰이 존재한다면 자신의 좋아요 리스트를 반영하게 하고 JWT 인증토큰이 없다면 좋아요와 상관없이 이용 가능 하도록 진행 <br/>
6. (아티스트, 콘서트)**좋아요 목록**과 **전체 목록** 정렬/검색 부분에서 구분을 두기 위해 **leftJoin** 사용 하여 전체목록과 좋아요목록 구현<br/>
7. 이미지 검색 기능 구현위해 유저가 이미지를 선택하면 boto3 라이브러리를 이용하여 S3 bucket에 이미지를 업로드 한 뒤 **AWS Rekognition** 의 인물검색 API 사용<br/>
7-1. 해당 기능은 영어로 출력되어 **AWS Translate API**를 한번 더 사용하여 MySQL에 접근 하는 방식으로 해당 인물의 정보와 공연정보를 보여주는 API로 개발<br/>

   
## 🎈결과🎈
만들어진 데이터파일과 서버로 안드로이드 개발을 진행함<br/>
[안드로이드 깃허브 링크](https://github.com/spiegelgo/TicketMerge-android, '안드로이드 깃허브 링크')<br/>
[프로젝트 기술서 링크](https://docs.google.com/presentation/d/10SK2fhhHQwgktnOjM6e3k2yymyNaWv71hm8S_mkchUI/edit?usp=sharing, '프로젝트 기술서 링크')<br/>
[시연 동영상 링크](https://youtu.be/feCfx006Jew, '시연동영상 링크')<br/>

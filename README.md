# Camp51.9_KioskProject_Final

 html, css, javascript를 처음 공부하는 동시에 영등포고등학교 메이커스페이스 Camp51.9의 시설 이용 키오스크를 직접 개발하는 프로젝트. 
 **2020/12/25~

## 개요
 2020년 겨울방학 부터 2021년 여름방학 까지 약 8개월 동안 메이커스페이스를 위한 출입등록 키오스크를 개발하고 실제로 이용하고 피드백을 받아 수정하는 작업을 거쳤습니다. 처음 html을 만지고 개발할때를 생각하면 지금 너무나 큰 발전을 한 것 같아 뿌듯하기도 합니다. 이번 글에서는 마지막으로 키오스크를 설치하고 어떻게 수정하고 어떤 기능을 추가했는지에 대해 정리하겠습니다.


## 개발 과정

 키오스크를 실제로 설치하고 운영하면서 정말 많은 사용자들이 이용했습니다. 그 과정에서 여러가지 피드백이 있었고 보완할점을 수정하고 기능을 추가하면서 더 완벽한 개발로 이어질 수 있도록 하였습니다.



### 비회원 로그인, 여러명 로그인 추가

 새로 오시는 분들이 회원가입을 하는 것을 꺼려 하실 수 있어 비회원 로그인으로 최소한의 정보만 가져오는 방식을 추가하였고 여러명 방문시 대표자 1인만 등록할 수 있도록 기능을 추가하였습니다. 여러명 방문시 대표 외의 인원은 인원수만 적을 수 있도록 했습니다. 따라서 인원수에 대한 정보도 스프레드 시트에 추가하였습니다.

<img src='https://github.com/HwanGonJang/HwanGonJang.github.io/blob/master/Pictures/h5_2.png?raw=true'></img>

<img src='https://github.com/HwanGonJang/HwanGonJang.github.io/blob/master/Pictures/h5_7.png?raw=true'></img>
<img src='https://github.com/HwanGonJang/HwanGonJang.github.io/blob/master/Pictures/h5_8.png?raw=true'></img>


### 웹 배포

 계속해서 웹을 수정해야했기 때문에 키오스크에 계속 번거롭게 파일을 바꿔야했습니다. 따라서 서버를 통해 웹을 배포하는 방법을 생각했으나 웹 하나를 유료 서버로 이용하기에는 비용 부담이 있었습니다. 그래서 생각한 방법으로 Netlify 라는 웹 어플리케이션 호스팅 서비스를 이용하는 것이었습니다. 

<img src='https://github.com/HwanGonJang/HwanGonJang.github.io/blob/master/Pictures/h5_3.png?raw=true'></img>

 이 서비스를 활용하여 웹을 수정하면 바로 올려서 배포하여 번거로움이 줄었고 누구나 볼 수 있다는 장점이 생겼습니다. 



### 메이커스페이스를 더 잘 보여주기 위한 Thinglink 활용

 메이커스페이스를 이용하는 사람들은 모두 출입등록 키오스크를 이용합니다. 따라서 이 키오스크에 메이커스페이스의 모습을 담아 여러가지 시설, 장비, 행사 등을 확인 할 수 있도록 만드는 기능을 추가했습니다. Thinglink라는 서비스를 활용하여 공간 사진들을 올려 한 눈에 확인 할 수 있도록 하였습니다.

<img src='https://github.com/HwanGonJang/HwanGonJang.github.io/blob/master/Pictures/h5_6.png?raw=true'></img>



### 이용한 시설 정보 시트에 추가

 이용자가 어떤 시설과 장비를 이용했는지 알 수 있도록 이 정보를 스프레드 시트에 추가하였습니다.

<img src='https://github.com/HwanGonJang/HwanGonJang.github.io/blob/master/Pictures/h5_2.png?raw=true'></img>



### 외부인 이용 정보(금액) 시트 생성

 메이커스페이스의 장비와 시설은 학생은 무료지만 외부인의 경우 유료로 이용할 수 있습니다. 원래는 외부인 이용 금액과 장비를 수기로 작성했지만 이제 출입등록시 장비 선택에서 사용목적을 입력할 수 있도록 하였고 이 정보를 따로 외부인 이용 스프레드 시트에 저장하였습니다.

<img src='https://github.com/HwanGonJang/HwanGonJang.github.io/blob/master/Pictures/h5_4.png?raw=true'></img>

<img src='https://github.com/HwanGonJang/HwanGonJang.github.io/blob/master/Pictures/h5_5.png?raw=true'></img>



## 결과

 이렇게 아무것도 모르는 상태에서 웹을 개발하고 실제로 운영하는 단계까지 오게 되었습니다. 시트에 나와있듯이 많은 사람들이 이용해주고 계십니다. 피드백을 받아 더 나은 키오스크를 만드는 과정이 굉장히 값진 경험이었고 작년의 저와는 또 다른 지금이 된 것 같습니다. 감사합니다!

<img src='https://github.com/HwanGonJang/HwanGonJang.github.io/blob/master/Pictures/h5_6.png?raw=true'></img>
<img src='https://github.com/HwanGonJang/HwanGonJang.github.io/blob/master/Pictures/h5_1.png?raw=true'></img>




 * Camp51.9 메이커스페이스 홈페이지
 https://www.makeall.com/reservation/info.php?space_no=1677&area=&tsort=4&msort=

 * 배포한 키오스크 웹 앱
 https://thirsty-golick-bbe10d.netlify.app/index.html

 * 키오스크 프로젝트 깃허브
    https://github.com/HwanGonJang/Camp51.9_KioskProject

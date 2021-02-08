# Snu-Remote-Test-Supervision
## 원격 시험 감독 - 감독관용 뷰어

- 아래의 링크를 통해 보시면, 영상과 함께 보실 수 있습니다 🙂 

pdf 보다는 웹링크를 통해 보시는 것을 권장드립니다.

    [https://www.notion.so/8e7d260560d942d2a6b216998fe0a74e](https://www.notion.so/8e7d260560d942d2a6b216998fe0a74e)

---

## ⭐ 주요 과제 및 흐름도

![](%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%80%E1%85%A7%E1%86%A8%20%E1%84%89%E1%85%B5%E1%84%92%E1%85%A5%E1%86%B7%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%20-%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%E1%84%80%E1%85%AA%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC%20%E1%84%87%E1%85%B2%E1%84%8B%E1%85%A5%20e4ed2b6f27684c12aff32da0b00ecb82/Untitled.png])
![](%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%80%E1%85%A7%E1%86%A8%20%E1%84%89%E1%85%B5%E1%84%92%E1%85%A5%E1%86%B7%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%20-%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%E1%84%80%E1%85%AA%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC%20%E1%84%87%E1%85%B2%E1%84%8B%E1%85%A5%20e4ed2b6f27684c12aff32da0b00ecb82/Untitled.png)

- 제가 맡은 부분은 위의 흐름도에서 **감독관용 뷰어**를 만드는 것이었습니다.
- 주요과제는 **(1) RTMP 프로토콜을 통해 실시간으로 재생되는 영상을 스트리밍하는 것**과 
**(2) 과거의 시험 영상을 다시 볼 수 있도록 HLS player를 만드는 것**입니다.
- 또한, 추가적으로 Login, change password, create account창을 만들어 **서울대학교 소속 조교님들이 (snu이메일 계정으로) 가입**을 할 수 있게 하였고, Scheduling test 창을 만들어 시험을 스케줄링하고, 미리 **담당 학생들 명단을 데이터베이스에 기록**할 수 있게 하였습니다.

## 1. Login

(1) [Create Account]()

![%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%80%E1%85%A7%E1%86%A8%20%E1%84%89%E1%85%B5%E1%84%92%E1%85%A5%E1%86%B7%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%20-%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%E1%84%80%E1%85%AA%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC%20%E1%84%87%E1%85%B2%E1%84%8B%E1%85%A5%20e4ed2b6f27684c12aff32da0b00ecb82/Untitled%201.png](%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%80%E1%85%A7%E1%86%A8%20%E1%84%89%E1%85%B5%E1%84%92%E1%85%A5%E1%86%B7%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%20-%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%E1%84%80%E1%85%AA%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC%20%E1%84%87%E1%85%B2%E1%84%8B%E1%85%A5%20e4ed2b6f27684c12aff32da0b00ecb82/Untitled%201.png)

**(2) [Login]()** 

![%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%80%E1%85%A7%E1%86%A8%20%E1%84%89%E1%85%B5%E1%84%92%E1%85%A5%E1%86%B7%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%20-%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%E1%84%80%E1%85%AA%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC%20%E1%84%87%E1%85%B2%E1%84%8B%E1%85%A5%20e4ed2b6f27684c12aff32da0b00ecb82/Untitled%202.png](%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%80%E1%85%A7%E1%86%A8%20%E1%84%89%E1%85%B5%E1%84%92%E1%85%A5%E1%86%B7%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%20-%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%E1%84%80%E1%85%AA%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC%20%E1%84%87%E1%85%B2%E1%84%8B%E1%85%A5%20e4ed2b6f27684c12aff32da0b00ecb82/Untitled%202.png)

[**(3) Change Password**]()

![%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%80%E1%85%A7%E1%86%A8%20%E1%84%89%E1%85%B5%E1%84%92%E1%85%A5%E1%86%B7%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%20-%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%E1%84%80%E1%85%AA%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC%20%E1%84%87%E1%85%B2%E1%84%8B%E1%85%A5%20e4ed2b6f27684c12aff32da0b00ecb82/Untitled%203.png](%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%80%E1%85%A7%E1%86%A8%20%E1%84%89%E1%85%B5%E1%84%92%E1%85%A5%E1%86%B7%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%20-%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%E1%84%80%E1%85%AA%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC%20%E1%84%87%E1%85%B2%E1%84%8B%E1%85%A5%20e4ed2b6f27684c12aff32da0b00ecb82/Untitled%203.png)

- Video

    [%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%80%E1%85%A7%E1%86%A8%20%E1%84%89%E1%85%B5%E1%84%92%E1%85%A5%E1%86%B7%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%20-%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%E1%84%80%E1%85%AA%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC%20%E1%84%87%E1%85%B2%E1%84%8B%E1%85%A5%20e4ed2b6f27684c12aff32da0b00ecb82/(1)_.mov](%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%80%E1%85%A7%E1%86%A8%20%E1%84%89%E1%85%B5%E1%84%92%E1%85%A5%E1%86%B7%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%20-%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%E1%84%80%E1%85%AA%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC%20%E1%84%87%E1%85%B2%E1%84%8B%E1%85%A5%20e4ed2b6f27684c12aff32da0b00ecb82/(1)_.mov)

---

### (1) Create Account

- Login page에서 Create Account를 누르면 회원가입을 할 수 있는 창으로 이동합니다.
- 회원가입 창에서는 학번, 이름, 이메일을 입력받습니다. 아래의 curl 명령어를 통해 회원가입 정보를 데이터베이스에 보냈습니다. 이후 승인이 이뤄지면 회원가입이 가능해집니다.

    curl -X POST [http://3.35.240.138:3333/sign_up](http://3.35.240.138:3333/sign_up) -d ID=2020-54321 -d name=John -d [mail_address=John@snu.ac.kr](mailto:mail_address=John@snu.ac.kr)

### (2) Login Page

- 회원가입 승인이 나면, 임시 비밀번호가 주어집니다.
- 임시번호로 로그인 한 경우, 바로 비밀번호를 변경하도록 Change password 창이 띄워집니다. 비밀번호를 변경하고 나면, 로그인이 완료됩니다.
- 최초 로그인이 아니라면, 자신의 이메일과 비밀번호를 통해 로그인 할 수 있습니다.
- 다음의 curl commend를 입력하였을 때

    (1) 최초 로그인이라면, Change Password라는 명령어가 반환되고

    (2) 입력된 정보가 데이터 베이스에 없다면 error라는 명령어가 반환되며,

    (3) 로그인이 완료된다면 token이 반환됩니다. 이후 이 token을 통해 감독관은 실시간 스트리밍 영상을 보거나 과거 영상을 replay할 수 있습니다.

    curl -X POST [http://3.35.240.138:3333/login](http://3.35.240.138:3333/login) -d [mail_address=John@snu.ac.kr](mailto:mail_address=John@snu.ac.kr) -d PW=temp_password

### (3) Change Password

- 아래의 curl commend를 통해 원하는 비밀번호로 비밀번호를 변경합니다.

    /curl - X POST [http://3.35.240.138:3333/change_password](http://3.35.240.138:3333/change_password) -d [mail_address=John@snu.ac.kr](mailto:mail_address=John@snu.ac.kr) -d PW=qwerty1234

## 2. Main Page

- Main Page에서는 시험을 스케줄링을 할 수 있습니다.
- 스케줄링된 시험은 list view를 통하여 볼 수 있으며, 예정된 시험을 삭제할 수도, 추가할 수도 있습니다.
- 또한, 이 페이지를 통해 live streaming을 볼 수 있는 페이지나 과거 영상을 볼 수 있는 페이지로 넘어갑니다.

### (1) Scheduling Test

- Scheduling test 에서는 시험정보(강의명, 시험명 ex. midterm, 시험 날짜, 시험 시작시간과 끝나는시간)와 학생 정보(이름, 학번, 감독관 번호)를 입력받습니다.

    (1) 시험정보

    curl -X POST [http://3.35.240.138:3333/add_exam_data](http://3.35.240.138:3333/add_exam_data) -d lec=logicdesign -d test=midterm -d testdate=20210108 -d starttime=1400 -d endtime=1530 -d token=

    (2) 학생정보

    curl -X POST [http://3.35.240.138:3333/add_student_data](http://3.35.240.138:3333/add_student_data) -d num=2020-12345 -d name=원준 -d supervNum=1 -d lec=logicdesign -d test=midterm -d testdate=20210108 -d starttime=1400

- Video

[%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%80%E1%85%A7%E1%86%A8%20%E1%84%89%E1%85%B5%E1%84%92%E1%85%A5%E1%86%B7%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%20-%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%E1%84%80%E1%85%AA%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC%20%E1%84%87%E1%85%B2%E1%84%8B%E1%85%A5%20e4ed2b6f27684c12aff32da0b00ecb82/Scheduling_Test.mov](%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%80%E1%85%A7%E1%86%A8%20%E1%84%89%E1%85%B5%E1%84%92%E1%85%A5%E1%86%B7%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%20-%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%E1%84%80%E1%85%AA%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC%20%E1%84%87%E1%85%B2%E1%84%8B%E1%85%A5%20e4ed2b6f27684c12aff32da0b00ecb82/Scheduling_Test.mov)

- 여러개의 시험을 추가해놓으면 이런 식으로 list up됩니다.

    ![%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%80%E1%85%A7%E1%86%A8%20%E1%84%89%E1%85%B5%E1%84%92%E1%85%A5%E1%86%B7%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%20-%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%E1%84%80%E1%85%AA%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC%20%E1%84%87%E1%85%B2%E1%84%8B%E1%85%A5%20e4ed2b6f27684c12aff32da0b00ecb82/Untitled%204.png](%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%80%E1%85%A7%E1%86%A8%20%E1%84%89%E1%85%B5%E1%84%92%E1%85%A5%E1%86%B7%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%20-%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%E1%84%80%E1%85%AA%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC%20%E1%84%87%E1%85%B2%E1%84%8B%E1%85%A5%20e4ed2b6f27684c12aff32da0b00ecb82/Untitled%204.png)

### (2) Live Streaming

스케줄링된 시험을 누른 후 감독관 번호를 입력하면, 라이브 스트리밍을 볼 수 있습니다. 학생이 한명씩 입장될 때마다 뷰어에는 사람이 추가됩니다. 

- **참고한 라이브러리 📚**
    - RTMP 프로토콜을 통해 라이브 영상을 재생하기 위해 unosquare의 ffmediaelement와 ruslan-B의 FFmpeg.AutoGen의 라이브러리를 참조하였습니다.

        [unosquare/ffmediaelement](https://github.com/unosquare/ffmediaelement)

        - unosquare의 라이브러리는 원격시험감독을 만들기 위해 일부 수정하였습니다. 제가 참조한 라이브러리는 위의 라이브러리와 100% 일치하지는 않습니다.

        [Ruslan-B/FFmpeg.AutoGen](https://github.com/Ruslan-B/FFmpeg.AutoGen)

    - 이외에도 webeye의 RTMP Player, openCV의 일부 코드등을 참고하였지만 직접적으로 참조를 하지는 않았습니다.

- 또한, live viewer는 총 세가지의 cs파일을 구현하였습니다.
1. **Live_player** 

    Live player는 rtmp 프로토콜을 통해 받아온 주소를 재생하는 player입니다. 실시간으로 스트리밍 되고 있는 영상을 띄우는 player이므로 play, pause등의 기능은 구현하지 않았고, mute기능만을 추가하였습니다.

    sound 버튼을 누르면 음소거가 해제되고, 버튼을 다시 누르면 음소거가 됩니다.

2. **Live Viewer**

    Live Viewer는 여러개의 RTMP 주소를 받으면, Live player를 통해 여러개의 영상을 띄우는 부분입니다. 주소의 끝부분에는 초기접속 / 재접속 여부를 뜻하는 정보가(0, 1) 함께 들어오는데, 이를 통하여 처음 접속하면 영상을 viewer에 추가하고, 재접속을 하면 영상이 새로고침되도록 구현하였습니다.

    또한, double click을 하면 화면이 확대될 수 있도록 보이지 않는 버튼을 만들었습니다.

3. **Live Tab**
    - 서버와의 통신 프로토콜을 통해 rtmp 주소를 받아오는 부분입니다. refresh button을 누르면 주소를 받을 수 있습니다.

        curl -X POST [http://3.35.240.138:3333/superv_endpoint](http://3.35.240.138:3333/superv_endpoint) -d lec_id=logicdesign.midterm_20210108 -d supervNum=1 -d token=

    - 또한, home으로 가거나 프로그램을 종료하는 경우에는 deactivation 명령어를 보내어 시험을 비활성화 하도록 구현하였습니다.

        curl - X POST [http://3.35.240.138:3333/exam_deactivation](http://3.35.240.138:3333/exam_deactivation) -d lec_id=sf.midterm_20210112 -d token=

- Video

    [%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%80%E1%85%A7%E1%86%A8%20%E1%84%89%E1%85%B5%E1%84%92%E1%85%A5%E1%86%B7%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%20-%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%E1%84%80%E1%85%AA%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC%20%E1%84%87%E1%85%B2%E1%84%8B%E1%85%A5%20e4ed2b6f27684c12aff32da0b00ecb82/(3)_Live_Streaming.mov](%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%80%E1%85%A7%E1%86%A8%20%E1%84%89%E1%85%B5%E1%84%92%E1%85%A5%E1%86%B7%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%20-%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%E1%84%80%E1%85%AA%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC%20%E1%84%87%E1%85%B2%E1%84%8B%E1%85%A5%20e4ed2b6f27684c12aff32da0b00ecb82/(3)_Live_Streaming.mov)

    ![%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%80%E1%85%A7%E1%86%A8%20%E1%84%89%E1%85%B5%E1%84%92%E1%85%A5%E1%86%B7%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%20-%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%E1%84%80%E1%85%AA%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC%20%E1%84%87%E1%85%B2%E1%84%8B%E1%85%A5%20e4ed2b6f27684c12aff32da0b00ecb82/SE-1a92a9d3-7c42-4d06-8b6e-35df3c2aff7b.png](%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%80%E1%85%A7%E1%86%A8%20%E1%84%89%E1%85%B5%E1%84%92%E1%85%A5%E1%86%B7%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%20-%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%E1%84%80%E1%85%AA%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC%20%E1%84%87%E1%85%B2%E1%84%8B%E1%85%A5%20e4ed2b6f27684c12aff32da0b00ecb82/SE-1a92a9d3-7c42-4d06-8b6e-35df3c2aff7b.png)

⭐ 개선해야할 사항

- 초기 delay : 처음에 6명 이상의 학생이 접속하면 최대 1분 30초의 초기 delay가 생기며, 각 학생들의 영상에도 delay가 있습니다. 초기에는 최대 40초까지도 있던 delay가 시간이 지나면 안정됩니다. (5분 이상 지나면 모든 영상의 delay가 10초 이내로 줄어듦)

    시간이 지나면, delay가 줄어들지만 그래도 초기 delay의 문제는 해결해야할 사항이라고 생각합니다.

- 또한, 현재는 refresh 버튼을 눌러야 학생들이 업데이트되도록 구현하였습니다. 이러한 버튼을 누르지 않고서도 학생 정보가 업데이트 된다면 더욱더 좋은 player가 될거라 생각합니다.

### (3) Review Test

- [**HLS (HTTP Live Streaming, HLS)](https://ko.wikipedia.org/wiki/HTTP_%EB%9D%BC%EC%9D%B4%EB%B8%8C_%EC%8A%A4%ED%8A%B8%EB%A6%AC%EB%B0%8D)** 프로토콜을 통해 AWS S3 클라우드에 저장되어있는 영상을 로드하여 재생하는 부분을 구현하였습니다.
- 아래의 github의 HLSTools.NETframework를 참고하였으나 일부 부분은 수정하였습니다. 
(ex. Dispose : TS파일 삭제)

    [tompaana/hls-transcription-sample](https://github.com/tompaana/hls-transcription-sample)

- Review Test 버튼을 클릭하면 HLS Player 페이지로 넘어옵니다. 이때, combobox에 자동으로 감독관이 담당한 과목들이 나오도록 구현하였습니다. 또한, 과목을 선택하면 그 과목의 시험을 본 학생들을 선택할 수 있습니다.

    최종적으로 학생을 선택하면, 해당 학생의 영상을 볼 수 있는 hls 주소가 반환됩니다.

    curl -X POST [http://3.35.240.138:3333/get_test_pre](http://3.35.240.138:3333/get_test_pre) -d token=

    curl -X POST [http://3.35.240.138:3333/previousvideo_student_list](http://3.35.240.138:3333/previousvideo_student_list) -d lec=logicdesign -d testdate=20210111 -d test=final

    curl -X POST [http://3.35.240.138:3333/get_test](http://3.35.240.138:3333/get_test) -d num=2020-12345 -d lec=logicdesign =d token=

- 초기에 play button을 누르면 재생이 시작됩니다. play, pause, stop은 기본적으로 사용할 수 있습니다.
- Slider를 통해 volume과 영상의 speed를 지원합니다. (배속재생 가능)
- time slider를 통해 원하는 부분을 바로 재생할 수 있도록 구현하였습니다.

    ⭐ 이 부분에 대한 설명은 code의 주석처리에 달아놓았습니다.

- home으로 이동하거나 어플리케이션을 중단하는 경우에는 hls가 종료되었다는 command를 서버에 보내주어야합니다. (감독관 만이 주소를 열고 닫을 수 있어야 영상의 주소가 노출되는 경우에도 다른 사람들이 볼 수 없도록 deactivate됨)

    따라서 hls가 종료되는 경우에 아래의 curl command를 통해 review test가 종료되었음을 알렸습니다.

    curl -X POST [http://3.35.240.138:3333/hlsFinish](http://3.35.240.138:3333/hlsFinish) -d httpUrl=https://node-sdk-sample-976067b2-cb45-4960-844f-000466192d2f.s3.ap-northeast-2.amazonaws.com//media/20201228/young_1228_1/young_1228_1.m3u8

- Video

[%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%80%E1%85%A7%E1%86%A8%20%E1%84%89%E1%85%B5%E1%84%92%E1%85%A5%E1%86%B7%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%20-%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%E1%84%80%E1%85%AA%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC%20%E1%84%87%E1%85%B2%E1%84%8B%E1%85%A5%20e4ed2b6f27684c12aff32da0b00ecb82/(4)_HLS_player.mov](%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%80%E1%85%A7%E1%86%A8%20%E1%84%89%E1%85%B5%E1%84%92%E1%85%A5%E1%86%B7%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%20-%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%E1%84%80%E1%85%AA%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC%20%E1%84%87%E1%85%B2%E1%84%8B%E1%85%A5%20e4ed2b6f27684c12aff32da0b00ecb82/(4)_HLS_player.mov)

## 프로젝트 첨부

- 배포버전

    아래의 파일을 다운로드 받으신 후 exe파일을 설치하시면 바로 이용이 가능합니다 😊

    [원격시험감독_감독관용뷰어_배포.zip](%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%80%E1%85%A7%E1%86%A8%20%E1%84%89%E1%85%B5%E1%84%92%E1%85%A5%E1%86%B7%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%20-%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%E1%84%80%E1%85%AA%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC%20%E1%84%87%E1%85%B2%E1%84%8B%E1%85%A5%20e4ed2b6f27684c12aff32da0b00ecb82/__.zip)

- 최종 프로젝트 첨부

    소스 코드에 대한 저작권은 백지혜에게 있습니다.

    [FFmePlayer_snu_final.zip](%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%80%E1%85%A7%E1%86%A8%20%E1%84%89%E1%85%B5%E1%84%92%E1%85%A5%E1%86%B7%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%20-%20%E1%84%80%E1%85%A1%E1%86%B7%E1%84%83%E1%85%A9%E1%86%A8%E1%84%80%E1%85%AA%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC%20%E1%84%87%E1%85%B2%E1%84%8B%E1%85%A5%20e4ed2b6f27684c12aff32da0b00ecb82/FFmePlayer_snu_final.zip)

감사합니다 :)

![https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fwww.notion.so%2F8e7d260560d942d2a6b216998fe0a74e&count_bg=%2379C83D&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=hits&edge_flat=false)](https://hits.seeyoufarm.com)](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fwww.notion.so%2F8e7d260560d942d2a6b216998fe0a74e&count_bg=%2379C83D&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=hits&edge_flat=false)](https://hits.seeyoufarm.com))

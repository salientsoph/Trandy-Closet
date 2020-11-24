# 회의록 11/24

**주요 이슈** : 기획안 수정, WBS, 각 분야 아키텍처 통합

**주요 회의 내용** : 기획안 완료, WBS 완료, 시스템 구성 아키텍처 통합

<br>

### 시스템 구상도 초안

<details>
<summary>보기</summary>
<div markdown="3">

![image-20201124145134712](C:\Users\coolu\AppData\Roaming\Typora\typora-user-images\image-20201124145134712.png)  

</div>
</details>

<br>

<details>
<summary>김학용 멘토님 11/21 토요일 멘토링 관련 답변 요약</summary>
<div markdown="1">

-   주어진 기간과 예산을 고려하여 성공 시킬 수 있는 아이템을 선별하자.
-   옷 추천과 스마트 옷장을 하나로 묶으면 더 나은 아이템이 된다고 보인다.
-   AR 기능을 주어진 기간 내에 할 수 있다면 당연히 하는게 맞을 것이다.
-   전체 시나리오를 정교화할 필요가 있다.
-   옷을 추천하는데도 올해의 색상이나 현재의 트렌드를 반영하는 것이 가능하면 해야 되겠지만, 그게 가능하지 않거나 학습하는데 시간이 걸린다면 다른 대안을 찾아라.
-   스마트 미러를 이용하면 가장 좋다. 하지만 예산을 고려하여 작은 LCD나 컴퓨터용 모니터를 이용하라. 멘토들은 되는 것만 보이라고 했지만 김학용 멘토님의 의견은 하드보드 이용 간단한 옷장 + LCD(소형 테블릿)로 데모를 보이는 것이 더 좋다.
-   IoT - 온습도 측정을 합리화
    -   단순히 보여주는 것은 약하다. 반응을 하도록
    -   습도 조절을 하는 방법이 간단하면 시도하지만 그렇지 않으면 의미가 없다.
    -   습도가 높으니 제습제를 넣어주세요 라는 알림 / 웃을 자동으로 열어 환기를 시키는 등의 반응이 필요
-   아직까지 약하다
    -   특정한 쇼핑몰(의류) 한 곳에서 옷 정보를 크롤링해서 본인이 가지고 있는 옷만으로의 최선의 매칭과 본인이 가진 옷과 쇼핑몰의 옷의 조합 중에서 최선의 매칭을 함께 제공
    -   가능하면 구매까지 할 수 있도록 하면 더 좋을 것 같음
-   현재의 스마트홈은 단순히 스마트 기기만 있는 것이 아니라 스마트 기기와 서비스가 결합되는 추세인데 그걸 반영한다고 하면 활용성 등에서 더 점수를 잘 받을 수 있을 것 같다.
-   장기적으로 쇼핑몰은 확대한다고 할 수 있다.


</div>
</details>

<br>

<details>
<summary>빅데이터, 클라우드 강사님 추가 의견/조언</summary>
<div markdown="2">

**빅데이터 강사님 추가 의견**

1.  자기가 이미 갖고 있는 옷인데, 그걸 기억 못하고 밖에서 다시 삼
    -   내가 가진 옷을 보여주면 좋을 거 같다
2.  내가 갖고 있는 옷을 봄, 여름, 가을, 겨울로 나누어 보여주면 좋을 거 같다

**빅데이터 강사님 조언**

1.  데이터 보관 관련
    -   aws는 빅데이터반, 클라우드반 각자 쓰고 나중에 병합하든가 그냥 로컬에서 우리반 서버로 쓰면 됨
    -   s3는 우리쪽에선 준비안됨 -> 클라우드에서 준비해야함
        수집해오고, ai 반에서 학습에 필요한 데이터 주는건 aws 서버 또는 로컬 사용
        가지고 온걸 어딘가에는 보관 -> 다른 반이랑 협의해서 s3에 넣든, 몽고db에 넣던 결정하기
    -   db 연동은 거기서 거기.. 어떤 db을 써야하는지 결정된건 없음(1,2 시간만 공부하면 쓸수있음)
2.  db에 대한 이미지 관련
    -   db에 다량의 이미지 파일 저장이 가능한지 아니면 이미지에 대한 서버를 따로 만들어야 하는건지?
        -   보통은 하드디스크 파일에 넣고, db에는 그 패스만 저장함
        -   사이즈가 많기 보다는 갯수가 많은게 문제.. 이건 고민해보겠다 -> 마리아db 사용 추천(파일 이름만 저장, aws 하드디스크 특정 디렉토리에 파일을 저장)
        -   사이즈가 크면 s3 사용하면 되는데 지금은 그 경우는 아닌듯. 갯수가 많을 때는 마리아 db 사용해라

-   이번 기회에 클라우드에서 얘기하는 AWS 관련 새로운 공부를 하면 경험에 좋을 것이다.

**클라우드 강사님**

강사님

1.  단순한 이미지 파일은 S3에 넣는게 편리함
    -   비용문제 - 100GB 저장 시 월 3불정도

2.  DB는 AWS 에 서비스하는 RDB 로 진행할 예정

</div>
</details>

<br>

### DB 선택

빅데이터가 데이터를 수집할 S3 버킷 + 사용자가 입력하는 옷을 저장할 S3버킷

DB에는 각각의 path만 라벨링하여 넣어준다. -> RDB

<br>

### 데이터 크기에 따른 과금 문제

S3 버킷이라는게 용량은 무제한 가능

S3 스탠다드 기준 - 기가당 0.023불

100기가 이용시 한달에 3불 내외 - 200기가까지도 괜찮지 않을까 예상된다.

-> 데이터를 크게 가져가자!

<br>
# 회의록 11/20

**주요 이슈** : 주제 선정

**주요 회의 내용** : 후보 주제에 대한 멘토 전달용 기획안 작성 (분야별)

<br>

### 프로젝트 주제

<details>
<summary>
1.  스마트 재활용품 분류 </summary>
<div markdown="1">
**프로젝트 목적**

-   주제4 색 기반 제품 분류 프로세스 자동화와 스마트 공장 프로젝트 변형
    -   색 기반 제품 분류 자동화 서비스와 국내 스마트 공장 현황과 사회적 인식을 제공하는 서비스를 개발한다.

**프로젝트 수행 방향**

-   **빅데이터**

    -   Python or R을 사용한 쓰레기 이미지 크롤링 수집
    -   구축데이터분석을 통해 현 주제의 문제 근거를 제시 사용되는 데이터

-   **AI**
-   사물 인식
    -   카테고리 분류
    -   쓰레기의 재활용 가능 불가능 판별
    -   기술
        -   CNN
            multinomial classification
    
-   **IoT**
-   실시간 이미지 정보 추출 및 데이터화
    -   선별된 쓰레기통 자동 개폐
    -   모니터링 APP 제작 (쓰레기통이 다 찼는지, 고장유무 등)
    -   센싱 디바이스 → 서버 간 무선 데이터 전송
    
-   **클라우드**

    -   클라우드 기반의 클라이언트 서비스 배포환경 구축

    -   기술

        -   EC2 : 가상서버

        -   S3 : 가상저장소

        -   DynamoDB : NoSql 

        -   CloudWatch : 로그모니터링, 알림 등

        -   RESTful API 개발 연동

참고 : https://youtu.be/FYTrhtD182c

</div>
</details>

<details>
<summary>
2.  출결 관리 시스템 </summary>
<div markdown="2">

**프로젝트 목적**

-   주제 8 안면 인식 스마트 도어와 CCTV 관련 정보 제공 프로젝트 변형
    -   안전한 삶을 유지하기 위한스 마트도어의 안면인식 서비스와 관심있는 지역의CCTV에 대한 정보를 제공하는 시스템을 개발한다.

**프로젝트 수행 방향**

-   **빅데이터**

    -   수강생 데이터 수집
    -   데이터분석을 통해 현 주제의 문제 근거를 제시
    -   사용되는 데이터 시각화

-   **AI**

    -   얼굴 인식 구분으로 누구인지 확인
    -   마스크 착용 유무 판단
    -   기술
        -   CNN
        -   openCV face_classifier
        -   cv2.face.LBPHFaceRecognizer_create()

-   **IoT**

    -   실시간 이미지 정보 추출 및 데이터화
    -   출입문 및 차단봉 제어 & 무선 통신
    -   출결 서비스 제공 APP 제작
    -   카카오톡 전송

-   **클라우드**

    -   클라우드 기반의 클라이언트 서비스 배포환경 구축

    -   기술

        -   EC2 : 가상서버

        -   S3 : 가상저장소

        -   DynamoDB : NoSql 

        -   CloudWatch : 로그모니터링, 알림 등

        -   RESTful API 개발 연동

</div>
</details>

<details>
<summary>
3.  관상을 통한 직업 추천 </summary>
<div markdown="3">

**프로젝트 목적**

-   얼굴 인식을 통해 관상을 확인 → 각 분야별 현직자들의 관상들과의 비교 → 어느 분야에 적합한지 / 어느 정도 적합한지 퍼센트를 통해 알려줌 OR 원하는 직업군이 있다면 지금 내 얼굴에서 어떤 점을 보완하고 바꾼다면 좋은 지 알려줌

**프로젝트 수행 방향**

-   **빅데이터**

    -   얼굴인식에 사용될 데이터 수집
    -   직업군에 영향을 끼치는 변수탐색 및 분석

-   **AI**

    -   얼굴 인식
    -   유사도 확인
    -   생김새 별 직군 분류
    -   새로 들어온 사진의 직군 예측
    -   기술
        -   CNN
            multinomial classification
        -   face detection
        -   openCV

-   **IoT**

    -   스마트폰 카메라 정보 추출, 데이터화 & APP UI, UX 제작
    -   스마트폰 -> 서버 데이터 무선 통신
    
-   **클라우드**

    -   클라우드 기반의 클라이언트 서비스 배포환경 구축

    -   기술

        -   EC2 : 가상서버

        -   S3 : 가상저장소

        -   DynamoDB : NoSql 

        -   CloudWatch : 로그모니터링, 알림 등

        -   RESTful API 개발 연동

문제점 : 직업별 인물 데이터셋 확보, IoT 요소

</div>
</details>

<details>
<summary>
4.  옷의 유사도로 비슷한 제품의 위치/가격 정보 제공 </summary>
<div markdown="4">
**프로젝트 목적**

-   관심있는 옷을 고르고 카메라에 인식하면, 다른 브랜드의 옷들 중 유사한 옷을 찾아내서 추천해주고 가게의 위치를 알려줌

**프로젝트 수행 방향**

-   **빅데이터**

    -   대형 쇼핑몰의 물품들을 크롤링 활용
    -   기존 쇼핑 소요시간 외 불편한점 분석

-   **AI**

    -   클러스터링으로 데이터셋의 의상들을 군집화
    -   내가 찍은 옷이 어떤 것과 비슷한지 유사도 판별
    -   기술
        -   비지도학습
        -   clustering
            mean shift, GMM등

-   **IoT**

    -   LED를 통한 길안내 정보 제공(고령 대상)
    -   스마트폰 카메라 정보 추출, 데이터화 & APP UI, UX 제작
    -   스마트폰 → 서버 데이터 무선 통신
    
-   **클라우드**

    -   클라우드 기반의 클라이언트 서비스 배포환경 구축

    -   기술

        -   EC2 : 가상서버

        -   S3 : 가상저장소

        -   DynamoDB : NoSql 

        -   CloudWatch : 로그모니터링, 알림 등

        -   RESTful API 개발 연동

문제점

-   IoT 요소
-   쇼핑시간단축 등 여러가지 좋을 수도 있지만, 기업입장에선 쇼핑시간단축이 좋지 않을 수 있다는 점을 생각하면, [소비자>사측, 소비자<사측] 어떤 부분으로 다가가야 하는지 고민



</div>
</details>

<details>
<summary>
5.  스마트 옷장 </summary>
<div markdown="5">

**프로젝트 목적**

-   옷장 내부의 옷 정보 저장하여 코디추천(색기반) (IOT)
-   다양한 사이트의 코디를 수집하여 적절한 색 배합 학습하기
-   당시 계절과 온도에 맞춰진 코디 추천
-   증강현실을 통해 옷장의 옷 걸쳐보기

**프로젝트 수행 방향**

-   **빅데이터**
    -   의상 색 조합에 대한 고민 必
-   **AI**

    -   내가 입을 옷의 패션이 좋은지 나쁜지 판별
    -   고른 옷과 어울릴 옷 색기반 분류
    -   사물 인식
    -   의상의 어울림 정도 예측
    -   색기반 옷 분류
    -   기술
        -   CNN
        -   binary classification (내 패션 좋은지 안좋은지)
        -   색기반 분류

-   **IoT**

    -   옷장 내부 실시간 이미지 정보 추출 및 데이터화
    -   옷장 자동 제어
    -   증강현실을 제공하기 위한 실시간 카메라 이미지 정보 추출 및 데이터화
    -   LCD를 통한 코디 정보 제공
    -   fan, 온습도, 가습기 제어

-   **클라우드**

    -   클라우드 기반의 클라이언트 서비스 배포환경 구축

    -   기술

        -   EC2 : 가상서버

        -   S3 : 가상저장소

        -   DynamoDB : NoSql 

        -   CloudWatch : 로그모니터링, 알림 등

        -   RESTful API 개발 연동

문제점 : 난이도, 데이터셋 라벨링

</div>
</details>
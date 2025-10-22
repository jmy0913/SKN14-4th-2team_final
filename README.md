###### SKN14_4rd_2TEAM
# 주제 : 기업 정보 분석 및 요약 챗봇

## 프로젝트 소개  
특정 기업의 정보나 관련 소식을 알고 싶을 때 쉽게 찾을 수 있도록 도와주는 챗봇입니다.
LLM의 널리지 컷오프 특성상 최신정보를 알기어렵기때문에 최신재무재표를 기반으로
특정 기업의 상황이나 주식 , 뉴스등을 한번에 보여줄수있는 대시보드를 제작하였습니다.

## 1️⃣ 팀 소개
 ### 팀 명 : 젬봇
### 개발 기간
> 2025.08.07 ~ 2025.08.08
### 팀원

<table width="100%">
  <tr>
    <td align="center">
      <img src="images/gyg.png" width="150" alt="강윤구 사진"/>
    </td>
    <td align="center">
      <img src="images/kur.png" width="150" alt="김의령 사진"/>
    </td>
    <td align="center">
      <img src="images/kkr.png" width="150" alt="김광령 사진"/>
    </td>
    <td align="center">
      <img src="images/wjh.jpeg" width="150" alt="이원지희 사진"/>
    </td>
    <td align="center">
      <img src="images/jmy.png" width="150" alt="정민영 사진"/>
    </td>
    <td align="center">
      <img src="images/jjg.jpg" width="150" alt="정전규 사진"/>
    </td>
  </tr>
  <tr>
    <td align="center">
      <b><a href="https://github.com/">강윤구</a></b>
    </td>
    <td align="center">
      <b><a href="https://github.com/my-cookies-26">김의령</a></b>
    </td>
    <td align="center">
      <b><a href="https://github.com/iamkkr2030">김광령</a></b>
    </td>
    <td align="center">
      <b><a href="https://github.com/jinijini20">이원지희</a></b>
    </td>
    <td align="center">
      <b><a href="https://github.com/jmy0913">정민영</a></b>
    </td>
    <td align="center">
      <b><a href="https://github.com/jung33010">전정규</a></b>
    </td>
  </tr>
</table>

### 역할 분배
| 작업명          | 담당자       | 산출물          |
|:-------------|:----------|:-------------|
| 프로젝트 주제 선정   | 전체 팀원     |              |
| 로그인 기능 | 강윤구 , 김광령     |   RDB       |
| 랭그래프 개발        | 정민영       | 파이썬 파일,벡터DB     |
| Django 개발 | 정민영, 김의령  | django project |
| AWS DOCKER 배포  | 정민영       |  Dockerfile, Docker-compose.yml, docker/default.conf   |
| README 작성    | 전정규      | README.md 파일 |
| ppt 제작       | 강윤구, 이원지희 | PPT          |
| 발표           | 강윤구       |              |

## 2️⃣ 프로젝트 개요
### 프로젝트 필요성

**1. 정보 접근성과 이해도 향상<br>**
- 기업의 사업보고서나 재무제표는 용어가 어렵고 구조가 복잡해 일반 투자자나 비전문가가 이해하기 힘든 경우가 많습니다. 
챗봇이 주요 내용인 매출 변화, 핵심 사업, 리스크 요소 등을 쉽게 풀어 설명해주면 누구나 빠르게 핵심 정보를 파악할 수 있어 
정보의 접근성과 이해도를 크게 높일 수 있습니다.

**2. 시간 절약 및 업무 효율화<br>**
- 수십~수백 페이지에 달하는 보고서를 직접 읽고 분석하는 데는 많은 시간이 소요됩니다. 챗봇을 활용하면 사용자가 필요한 부분만 
골라서 빠르게 확인할 수 있어 분석 시간과 수고를 줄일 수 있으며, 투자자, 회계사, 일반 사용자 모두에게 업무 효율 향상이라는 
이점을 제공합니다.

**3. 생성형 ai 사이트에서도 세부적인 사항은 알기 힘듭니다.<br>**
- 요즘 gpt나 gemini 같은 수많은 생성형 ai 사이트들이 있지만 이런 곳에서도 기업의 사업 보고서 같은 세부적인 내용은 알기 힘듭니다.
그렇기 때문에 환각 현상이 발생하여 원하는 정보를 얻지 못할 수 있습니다.

<hr>

### 프로젝트 목표

**1. 비전문가도 쉽게 이해할 수 있는 요약 제공**

- 어려운 용어나 구조를 쉽게 풀어, 누구나 핵심 내용을 빠르게 파악할 수 있도록 함.

**2. 사업보고서와 재무제표의 핵심 정보 자동 추출 및 요약**

- 매출, 영업이익, 주요 사업, 위험요소 등 주요 항목을 자동으로 분석하고 요약.

**3. 사용자 맞춤형 질문응답 기능 제공**

- “이 회사의 수익성은 어떤가요?”, “최근 3년 매출 추이는?”과 같은 질문에 맞춤형 답변 제공.

**4. 최신 공시 정보 실시간 반영 및 업데이트**

- DART api를 활용, 외부 데이터와 연동하여 최신 보고서 반영 가능.

**5. 웹 기반 챗봇 인터페이스 구현**

- 사용자가 PC에서 쉽게 접근할 수 있도록 직관적인 웹 챗봇 인터페이스 제공.

**6. 질문자가 원하는 수준에 따라 답변 수준 분류**

- 답변을 간단하고 쉽게 설명해주는 초급부터 구체적이고 전문적인 고급까지 답변 수준을
분류하여 설명

<hr>

## 3️⃣ 기술 스택 및 파일 구조
| 항목              | 내용                                                                                                                                                                                                                                                                                                         |
| :---------------- |:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Language** | ![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white) ![LangChain](https://img.shields.io/badge/LangChain-00863D?style=for-the-badge&logo=langchain&logoColor=white) ![RAG](https://img.shields.io/badge/RAG-8A2BE2?style=for-the-badge&logoColor=white) ![LangGraph](https://img.shields.io/badge/LangGraph-1E90FF?style=for-the-badge&logo=graphviz&logoColor=white) |
| **Development** | ![VS Code](https://img.shields.io/badge/VS%20Code-007ACC?style=for-the-badge&logo=visual-studio-code&logoColor=white) ![PyCharm](https://img.shields.io/badge/PyCharm-000000?style=for-the-badge&logo=pycharm&logoColor=white) |
| **Server** | ![Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white) |
| **Deployment & Infra** | ![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white) ![Amazon AWS](https://img.shields.io/badge/Amazon_AWS-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white) |
| **Embedding** | ![BAAI/bge-m3](https://img.shields.io/badge/BAAI/bge--m3-000000?style=for-the-badge&logo=huggingface&logoColor=white) |
| **LLM Model** | ![GPT-4o](https://img.shields.io/badge/GPT--4o-4B91FF?style=for-the-badge&logo=openai&logoColor=white) |
| **Collaboration Tool** | ![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white) |
| **Vector DB** | ![FAISS](https://img.shields.io/badge/FAISS-4B8BEA?style=for-the-badge&logo=facebook&logoColor=white) |
| **Database** | ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white) |
| **API 활용** | ![Open Dart API](https://img.shields.io/badge/Open%20DART%20API-002D61?style=for-the-badge&logoColor=white) <br> ![Yahoo Finance](https://img.shields.io/badge/yfinance-144E8C?style=for-the-badge&logo=yahoo&logoColor=white) <br> ![PyKRX](https://img.shields.io/badge/pykrx-1F9F3F?style=for-the-badge&logoColor=white) <br> ![Naver News](https://img.shields.io/badge/Naver%20News%20Crawling-03C75A?style=for-the-badge&logo=naver&logoColor=white) ![Google API](https://img.shields.io/badge/Google%20Login%20API-4285F4?style=for-the-badge&logo=google&logoColor=white) <br> ![Naver API](https://img.shields.io/badge/Naver%20Login%20API-03C75A?style=for-the-badge&logo=naver&logoColor=white) <br> ![Kakao API](https://img.shields.io/badge/Kakao%20Login%20API-FFCD00?style=for-the-badge&logo=kakao&logoColor=black) <br> |

<hr>

## ⚙️ repository folder structure
```markdown
jembot_all_docker/
├── _homework/                          # Django 프로젝트 설정 디렉토리
│   ├── asgi.py                         # ASGI 애플리케이션 설정 (비동기 웹 서버)
│   ├── settings.py                     # Django 프로젝트 메인 설정 파일
│   ├── timeout_screenshot.png          # 타임아웃 관련 스크린샷 (문서)
│   ├── urls.py                         # 프로젝트 메인 URL 라우팅 설정
│   ├── wsgi.py                         # WSGI 애플리케이션 설정 (동기 웹 서버)
│
├── accounts/                           # 사용자 계정 관리 앱
│   ├── adapter.py                      # 소셜 로그인 어댑터 (프로필 이미지 저장 로직)
│   ├── admin.py                        # Django 관리자 페이지 설정
│   ├── apps.py                         # 앱 설정 파일
│   ├── forms.py                        # 사용자 폼 정의 (회원가입, 로그인 등)
│   ├── urls.py                         # 계정 관련 URL 라우팅
│   ├── views.py                        # 계정 관련 뷰 함수들
│
├── app/                                # 메인 애플리케이션 앱
│   ├── __init__.py                     # Python 패키지 초기화
│   ├── admin.py                        # Django 관리자 페이지 설정
│   ├── apps.py                         # 앱 설정 파일
│   ├── auth_views.py                   # 인증 관련 뷰 (구글 OAuth 등)
│   ├── migrations/                     # 데이터베이스 마이그레이션 파일들
│   │   ├── __init__.py
│   │   ├── 0001_initial.py            # 초기 마이그레이션
│   │   └── 0002_remove_customuser_google_id_alter_customuser_name_and_more.py
│   ├── models.py                       # 데이터베이스 모델 정의 (CustomUser 등)
│   ├── tests.py                        # 테스트 파일
│   ├── urls.py                         # 메인 앱 URL 라우팅
│   ├── utils2/                         # 유틸리티 함수들
│   │   ├── __init__.py
│   │   ├── api_get.py                  # API 호출 관련 함수
│   │   ├── chain_setting.py            # LangChain 설정
│   │   ├── corp_list.json              # 기업 목록 데이터
│   │   ├── faiss_index_bge_m3/         # 사업보고서 FAISS 벡터 DB (BGE 모델) --- 구글 드라이브 링크 제공
│   │   ├── faiss_index3/               # 회계기준서 FAISS 벡터 DB (BGE 모델) --- 구글 드라이브 링크 제공
│   │   ├── graph_node.py               # 그래프 노드 정의
│   │   ├── graph_setting.py            # 그래프 설정
│   │   ├── main.py                     # 메인 유틸리티 함수
│   │   ├── normalize_code_search.py    # 코드 검색 정규화
│   │   ├── retreiver_setting.py        # 검색기 설정
│   │   ├── stock_chain.py              # 주식 관련 LangChain
│   │   ├── stock_node.py               # 주식 노드 정의
│   │   └── test.ipynb                  # 테스트 노트북
│   └── views.py                        # 메인 뷰 함수들 (채팅, 주식 등)
│
├── images/                             # 이미지 파일들
│   └── img.png                         # 일반 이미지
│
├── media/                              # 사용자 업로드 파일 저장소
│   └── profile_pics/                   # 프로필 사진 저장 디렉토리
│       ├── 471203945-6b40c57f-021e-4941-b01d-13a581173301.gif
│       ├── Golden-Retriever_wtoN2sa.jpg
│       ├── Golden-Retriever.jpg
│       ├── image.png
│       ├── kakao_icon_1ZlWi1d.png
│       ├── kakao_icon_789lysH.png
│       ├── kakao_icon_iglyz0I.png
│       ├── kakao_icon_NGyG1Se.png
│       ├── kakao_icon.png
│       ├── naver_icon_kt8qWMc.png
│       ├── naver_icon_l8rmE9E.png
│       ├── naver_icon_pLdUwc0.png
│       ├── naver_icon.png
│       ├── rasdf.png
│       ├── robot-icon_BaYzrWU.png
│       └── robot-icon.png
│
├── static/                             # 정적 파일들 (CSS, JS, 이미지)
│   ├── css/                            # CSS 스타일시트
│   │   ├── app/                        # 앱별 CSS
│   │   │   ├── main.css                # 메인 페이지 스타일
│   │   │   └── stock.css               # 주식 페이지 스타일
│   │   ├── layout/                     # 레이아웃 관련 CSS
│   │   │   ├── base.css                # 기본 레이아웃 스타일
│   │   │   ├── footer.css              # 푸터 스타일
│   │   │   └── header.css              # 헤더 스타일
│   │   ├── home.css                    # 홈페이지 스타일
│   │   └── profile.css                 # 프로필 페이지 스타일
│   ├── images/                         # 정적 이미지 파일들
│   │   ├── google_icon.svg             # 구글 아이콘
│   │   ├── kakao_icon.png              # 카카오 아이콘
│   │   ├── naver_icon.png              # 네이버 아이콘
│   │   └── robot-icon.png              # 로봇 아이콘 (기본 프로필)
│   └── js/                             # JavaScript 파일들
│       └── app/                        # 앱별 JavaScript
│           ├── main_chat.js            # 메인 채팅 기능
│           ├── main.js                 # 메인 페이지 기능
│           └── stock.js                # 주식 페이지 기능
│
├── templates/                          # HTML 템플릿 파일들
│   ├── account/                        # 계정 관련 템플릿
│   │   ├── login.html                  # 로그인 페이지
│   │   ├── logout.html                 # 로그아웃 페이지
│   │   ├── profile_edit.html           # 프로필 수정 페이지
│   │   ├── profile.html                # 프로필 페이지 (마이페이지)
│   │   └── signup.html                 # 회원가입 페이지
│   ├── app/                            # 메인 앱 템플릿
│   │   ├── login.html                  # 앱 로그인 페이지
│   │   ├── main.html                   # 메인 페이지 (채팅)
│   │   └── stock.html                  # 주식 페이지
│   ├── layout/                         # 레이아웃 템플릿
│   │   ├── base.html                   # 기본 레이아웃 (헤더, 푸터 포함)
│   │   ├── footer.html                 # 푸터 템플릿
│   │   └── header.html                 # 헤더 템플릿
│   ├── socialaccount/                  # 소셜 계정 관련 템플릿
│   │   ├── signup.html                 # 소셜 회원가입 페이지
│   │   └── snippets/                   # 소셜 로그인 스니펫
│   │       └── provider_list.html      # 소셜 로그인 제공자 목록
│   └── home.html                       # 홈페이지 템플릿
│
├── .env                                # 환경 변수 파일 (API 키, 데이터베이스 설정 등)
├── .gitignore                          # Git 무시 파일 목록
├── docker-compose.yml                  # Docker Compose 설정 (서비스 정의)
├── Dockerfile                          # Docker 이미지 빌드 설정
├── manage.py                           # Django 관리 명령어 스크립트
├── requirements.txt                    # Python 패키지 의존성 목록
└── setup.sql                           # 데이터베이스 초기 설정 SQL
```

> 🔗 **FAISS 벡터 DB 다운로드 링크**
> - [faiss_index3 (회계기준서 벡터 DB) / faiss_index_bge_m3 (사업보고서 벡터 DB)](https://drive.google.com/drive/folders/19y5kH1-mgCo3-0_Rbuxq3gCFL7zoI9ar?usp=sharing)


# ⚙️ JemBot 실행 방법 (클라우드 인스턴스 + Docker)

## 1. 사전 준비
- 클라우드 인스턴스에 Docker 설치
- MySQL 인스턴스 or 도커 컨테이너 준비 (IP 주소 확인)

## 2. Docker / docker-compose 설치 (인스턴스에서)
```bash
# Ubuntu
sudo apt update
sudo curl https://get.docker.com | bash
sudo apt install docker-compose-plugin -y

# CentOS/RHEL
sudo yum install docker docker-compose
sudo systemctl start docker
sudo systemctl enable docker
sudo usermod -aG docker $USER
```

## 3. 설정 파일 준비

### 깃허브 클론 (jembot_all_docker 폴더 사용)
```bash
git clone https://github.com/SKNETWORKS-FAMILY-AICAMP/SKN14-4th-2Team
```

### .env 파일 생성 (jembot_all_docker 폴더 내에서)
```env
# LangSmith 설정
LANGSMITH_API_KEY=your_langsmith_api_key
LANGSMITH_ENDPOINT=https://api.smith.langchain.com/
skn14_langchain=skn14_langchain
LANGSMITH_TRACING=true

# API 키들
DART_API_KEY=your_dart_api_key
OPENAI_API_KEY=your_openai_api_key
NAVER_CLIENT_ID=your_naver_client_id
NAVER_CLIENT_SECRET=your_naver_client_secret

# 소셜 로그인 API 키
GOOGLE_OAUTH2_CLIENT_ID=your_google_oauth2_client_id
GOOGLE_OAUTH2_CLIENT_SECRET=your_google_oauth2_client_secret
KAKAO_CLIENT_ID=your_kakao_client_id
KAKAO_CLIENT_SECRET=your_kakao_client_secret
NAVER_LOGIN_CLIENT_ID=your_naver_login_client_id
NAVER_LOGIN_CLIENT_SECRET=your_naver_login_client_secret
```

### 소셜 로그인 리다이렉트 URL 설정
각 소셜 로그인 제공자 콘솔에서 리다이렉트 URL을 다음으로 설정:
- **Google**: `http://[인스턴스_퍼블릭_IP]:80/accounts/google/login/callback/`
- **Naver**: `http://[인스턴스_퍼블릭_IP]:80/accounts/naver/login/callback/`
- **Kakao**: `http://[인스턴스_퍼블릭_IP]:80/accounts/kakao/login/callback/`

- 각 소셜 로그인 제공자별로, ip주소만으로 접속을 허가하지 않을때는 인스턴스 퍼블릭 ip를 무료 도메인과 연결하여 사용 필요
- 이 경우 settings.py의 ALLOWED_HOSTS에 연결한 도메인 주소도 같이 넣어야 하고, 소셜 로그인 리다이렉트 url 설정에서도 ip 대신 도메인 주소 기준으로 넣어야 함


### jembot_all_docker/_homeowork/settings.py 수정
```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'jembotdb',
        'USER': 'jembot',
        'PASSWORD': 'jembot',
        'HOST': '[MySQL_인스턴스_IP]',  # 여기에 실제 MySQL IP 입력
        'PORT': '3306',
        'OPTIONS': {
            'charset': 'utf8mb4',
        },
    }
}


ALLLOWED_HOSTS = [AWS 인스턴스 IP주소, 혹은 허용할 특정 IP 주소(연결 도메인 등)]
```

### FAISS 벡터 DB 추가
- `app/utils2/faiss_index_bge_m3/` 폴더 다운로드 후 배치
- `app/utils2/faiss_index3/` 폴더 다운로드 후 배치

## 4. 실행 (빌드 + 실행 한 번에) ---> jembot_all_docker 폴더에서 실행 필요
```bash
docker-compose up --build -d
```

## 5. 접속
- **메인**: http://[인스턴스_퍼블릭_IP]:80

## 6. 문제 해결
```bash
# 로그 확인
docker-compose logs

# 재시작 (빌드 포함)
docker-compose down
docker-compose up --build -d

# 방화벽 확인 (80번 포트 열기)
sudo ufw allow 80
```

## 4️⃣ 시스템 아키텍처

<img src="images/img.png" width="auto" alt="시각화 사진"/>

 **1. 질문 입력**<br>
**사용자는 챗봇을 통해 질문을 입력합니다.<br>**
- 예시:
“이 회사 최근 매출은 얼마나 늘었어?”
“현대자동차의 주력 사업이 뭐야?”
“2023년 말 기준 자산총계 알려줘”
이 입력은 그대로 LLM에게 넘기지 않고, **사전 처리 과정(분류 및 의도 파악)**을 거칩니다.


**2. 질문 유형 파악**<br>
**이 단계에서 질문이 어떤 유형인지 파악합니다.**
- 예시:
  - 사업정보 질문 (예: 주력 사업, 신사업, 시장 점유율 등)
  - 재무정보 질문 (예: 손익계산서, 재무상태표, 수익성 지표 등)
  - 회계정보 질문 (예: 재무제표 해석 방법, 회계 기준 질문 등)
  - 복합 정보 (두 가지 이상의 정보를 묻는 경우)
  - 그 외 질문 (기업과는 관련없는 질문)

**3. 적절한 데이터 소스 선택 및 검색**<br>
**질문 유형에 따라 다음과 같은 방식으로 데이터를 찾습니다.**
- 벡터 검색 : 사업보고서 같은 비정형 텍스트는 chunk 단위로 나눠 임베딩하고, FAISS 벡터 DB에 저장해 둡니다.


- DART API 활용 : 공시된 재무제표나 정형 데이터는 DART Open API를 통해 호출합니다.<br>
예시: "삼성전자 2023년 영업이익" → API를 호출하여 숫자 추출


- 혼합 접근 (Hybrid)
만약 질문이 복합적이면 벡터db 검색 + DART API 병행
<br>예시 : “작년 매출과 무슨 사업을 했는지 알려줘”

- 답변 생성 (LLM 기반 생성)
검색된 자료를 기반으로 LLM 모델이 답변을 생성합니다.<br>
예시 : “현대차는 2024년 대비 약 20% 매출이 증가하여, 2025년 총 140조 원의 매출을 기록했습니다.”

<hr>

##  5️⃣ 중요 코드 설명
#### 1. `api_get.py`

get_financial_state() 함수는 기업 코드, 연도, 보고서 코드, 연결 구분을 받아 DART API로 요청을 보냅니다.

응답이 성공적이면 각 항목(계정명, 당기/전기 금액, 통화)을 포맷팅해 리스트로 반환합니다.

오류 발생 시 [API 오류] 메시지를 포함한 리스트를 반환합니다.

---

#### 2. `chain_setting.py`

메인 챗봇 langgraph에서 사용하는 각 chain을 설정하는 함수 파일입니다. (프롬프트 포함)

---

#### 3. `normalize_code_search.py`
normalize_company_name()은 입력된 기업명을 정규화하여 corp_list에서 가장 유사한 공식 기업명으로 매칭합니다.

parse_extracted_text()는 텍스트에서 회사명과 연도 정보를 추출하여 딕셔너리 형태로 반환합니다.

find_corporation_code()는 정규화된 기업명을 기반으로 corp_list.json에서 해당 기업의 고유 코드를 찾아 반환합니다.

---

#### 4. `retriever_setting.py`
HuggingFace의 BAAI/bge-m3 임베딩 모델을 사용하여 로컬에 저장된 두 개의 FAISS 인덱스(faiss_index3, faiss_index_bge_m3)를 로드합니다.

각각의 인덱스에서 top-6 유사 문서를 검색할 수 있는 accounting_retriever와 business_retriever를 생성합니다.

---

#### 5. `graph_node.py`
메인 챗봇 시스템에 사용되는 langgraph의 각 노드를 생성한 함수 파일입니다.

---

#### 6. `graph_setting.py'
graph_node.py에서 생성한 각 노드들을 사용하여 langgraph를 생성하는 함수 파일입니다.

---

#### 7. `main.py`
graph_settings.py에서 생성한 langgraph를 가져와서, 실제 사용자 데이터를 받아서 langgraph의 State를 반환하는 함수 파일입니다.

---

#### 8. `stock_chain` 
주식 분석 리포트를 제공해주는 페이지에서 사용하는 주식(기업) 분석 RAG 체인을 반환하는 함수 파일입니다.

---

#### 9. `stock_node`
stock_chain에서 가져온 주식(기업) 분석 RAG 체인으로, 사용자의 입력(기업명)을 받고 해당 기업에 대한 사업보고서/재무제표를 RAG로 가져오고 리포트를 작성해주는 실제 실행 함수 파일입니다.



# ♒ 흐름

## 1. 사용자 인증 흐름 (일반 로그인 및 소셜 로그인)

### 🔐 소셜 로그인 흐름:

```
사용자
    ↓
Django 서버 (소셜 로그인 버튼 클릭)
    ↓
소셜 로그인 API (Google/Kakao/Naver) - 외부 사이트로 리디렉션
    ↓
사용자 인증 완료 후 Django로 콜백
    ↓
Django Allauth가 인증 코드 처리 & 사용자 정보 가져오기
    ↓
세션 생성
    ↓
사용자 대시보드
```

---

### 🔑 일반 로그인 흐름 (이메일/비밀번호):

```
사용자 (이메일/비밀번호 입력)
    ↓
Django Allauth 인증 (DB에서 이메일/비밀번호 확인)
    ↓
세션 생성
    ↓
사용자 대시보드
```
## 2. 챗봇 답변 흐름

```
사용자 질문
     ↓
Django 서버 (웹 인터페이스)
     ↓
LangGraph
     ↓ (질문 분류 & 회사명/연도 추출)
OpenAI GPT-4o (분류/추출 작업)
     ↓
병렬 처리:
   ├── FAISS 벡터 DB (회계기준서/사업보고서 검색)
   └── DART Open API (실시간 재무제표 조회)
     ↓
수집된 모든 데이터 + 프롬프트
     ↓
OpenAI GPT-4o (최종 답변 생성)
     ↓
Django 서버
     ↓
챗봇 응답
```
## 3. 주식 정보 요청 흐름(주식검색)

```
사용자 주식 검색
    ↓
Django 서버
    ↓
yfinance / pykrx (주식 데이터 조회)
    ↓
데이터 가공 및 포맷팅
    ↓
사용자에게 결과 제공
```
## 4. 뉴스 정보 요청 흐름
```
사용자 요청
    ↓
Django 서버
    ↓
네이버 뉴스 Open API
    ↓
Beautiful Soup (HTML 파싱/데이터 정제)
    ↓
뉴스 정보 제공
```

## 5 주식 리포트 제공 흐름
```
사용자 요청 (기업명)
    ↓
Django 서버
    ↓
Langchain 워크플로우 실행
    ↓
FAISS 벡터 DB (사업보고서) + DART API (재무제표)
    ↓
OpenAI GPT-4o (분석 리포트 생성)
    ↓
주식 분석 리포트 제공
```

## 6️⃣ Django WEBAPP 구현

**화면설계 와이어 프레임**
  <img src="images/wire.png" width="auto" alt="화면1"/>

### 구현 사항
#### 1. 채팅창 옆에 뉴스와 주식을 볼 수 있는 칸을 구현하여 기업에 관한 정보를 쉽게 얻을 수 있도록 구현
<img src="images/chat_page.png" width="auto" alt="결과1"/><br>
<img src="images/chat_page2.png" width="auto" alt="결과1-1"/><br>
- 밑의 입력창에 기업명을 적으면 그 기업과 관련된 기사들이 뜨는 식으로 구현했습니다.
- 주식 칸에서 기업명을 검색하면 그 기업의 주가 정보가 나오도록 구현했습니다.

#### 2. 관심기업 및 종합보고서 기능 그리고 주식조회와 왼쪽의 댓글코멘트와 좋아요의 기능을 추가
<img src="images/stock.png" width="auto" alt="결과3"/><br>
<img src="images/stock2.png" width="auto" alt="결과3-1"/><br>
- 해당 주식에 대한 여러 사람들의 생각을 볼 수 있게 댓글창을 구현하였으며 거기다 댓글에 좋아요를 눌러 서로 교류할 수 있도록 하였습니다.

#### 3. 회원가입, 로그인, 마이페이지 기능 추가
<img src="images/login.png" width="auto" alt="로그인"/><br>
<img src="images/signup.png" width="auto" alt="회원가입"/><br>
<img src="images/mypage.png" width="auto" alt="마이페이지"/><br> 
<img src="images/mypage_edit.png" width="auto" alt="마이페이지 수정"/><br>
- 로그인 및 로그인한 회원의 정보와 그 정보를 수정할 수 있는 기능을 추가하였습니다.

<hr>

## 7️⃣ 성능 개선 노력
- **벡터db와 api 동시 사용**

  - 저희 챗봇은 정적 데이터 검색을 위한 벡터 DB와 동적 정보 조회를 위한 실시간 API를 
  결합한 하이브리드 검색 구조를 구현했습니다. 이 접근법은 벡터 DB에 모든 데이터를 
  저장하는 것의 현실적인 제약을 극복하고, 내장 데이터만으로는 답변할 수 없는 최신 정보나 
  외부 데이터 기반의 질문에 효과적으로 대응할 수 있습니다.
  
 
- **질문 유형 다양화**
  - 사용자 질문의 복잡성과 다양성에 대응하기 위해, 질문의 의도를 5가지 유형으로 먼저 
  분류하는 의도 분류 단계를 도입했습니다. 분류된 유형에 따라
  각기 다른 전문 체인과 리트리버가 동적으로 선택되어 질문을 처리합니다. 이러한 멀티-체인 
  아키텍처는 단일 파이프라인 방식보다 훨씬 더 정교하고 맥락에 맞는 답변을 생성하여 응답의 
  전문성을 극대화합니다.


- **Langgraph 활용**
  - LangGraph를 활용해 질문 분류, 정보 추출, 응답 생성을 단계별 노드로 나누고, 조건 분기로 흐름을 자동 제어하도록 구성했습니다.
  이 구조를 통해 복잡한 질문도 유연하게 처리할 수 있고, 각 질문에 맞는 적절한 응답 체인을 선택해 정확도를 높였습니다.
  또한 유지보수가 쉬워지고, 사용자 수준별(초급~고급) 대응도 가능해져 전반적인 성능이 향상되었습니다.

<hr>


## 한 줄 회고
- 전정규:기존 streamlit과 다르게 django로 새롭게 구현하는게 신기하고 어려웠습니다. 이번프로젝트 팀원들 모두 고생많으셨습니다. 
- 이원지희: Django로 웹을 구현 시도 해보고  Langrpah를 연동하며, 그과정에서 발생한 문제를 해결하며 많은것을 배웠습니다.
- 김광령:django를 활용하여 웹 페이지를 실제로 구현하는 게 힘들긴 했지만 좋은 경험이었습니다.
- 정민영:LangGraph 구조 설계와 Django 웹 페이지 구현을 통해 수많은 오류를 해결하며, 문제 해결 능력과 기술적 깊이를 쌓은 값진 경험이었습니다.
- 김의령:Django에 맞게 HTML, CSS, JavaScript 구조를 설계하고, RAG와 연동을 구현하는 과정에서 중간중간 많은 어려움이 있었지만, 원하는 결과물을 도출해낼 수 있었어서 뜻깊은 시간이었습니다.
- 강윤구:장고의 백엔드 흐름과 작동 원리를 전체적으로 이해하는 시간이었다

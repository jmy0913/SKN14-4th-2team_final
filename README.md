## 📊 기업 정보 분석 및 요약 챗봇 Portfolio (정민영)

### 🎯 프로젝트 주제 및 개요
- **목표**: 비전문가도 이해할 수 있게 기업의 사업/재무 핵심 정보를 요약하고, 최신 공시/시장 데이터와 결합해 질의응답을 제공
- **기간**: 2025.08.07 ~ 2025.08.08 (2일)
- **핵심**: 벡터 검색(FAISS) + 실시간 API(DART, yfinance/pykrx)를 결합한 하이브리드 검색과 LangGraph 기반 워크플로우

### 🔗 시연 영상: https://youtu.be/Dd6SCocLpJo?si=vHYwAnm9P3TEYT75

### 🙋 나의 역할
- **LangGraph 개발**: 질문 유형 분류(사업/재무/회계/복합/기타), 회사명/연도 추출, 하이브리드 검색 분기, 응답 생성 체인을 단계별 노드로 분리하고 조건 분기로 흐름을 자동 제어하도록 설계/구현
- **검색·체인 설계**: BAAI/bge-m3 임베딩 기반 이중 FAISS 인덱스(회계기준서·사업보고서) 리트리버 구성, 기업명 정규화 매칭, 질문 유형별 전문 체인·리트리버 동적 선택(멀티-체인) 구현
- **Django 웹 개발**: 웹 챗 UI, 뉴스/주식 사이드 패널, 관심기업·종합보고서, 댓글/좋아요, 회원/마이페이지 등 핵심 화면 구현
- **배포**: Docker 기반 배포 구성(AWS Docker 배포), 웹서버 설정 포함

### 📈 구현한 결과

| 항목 | 내용                                                                                                                      |
|:---|:------------------------------------------------------------------------------------------------------------------------|
| **하이브리드 검색 구조** | 비정형 텍스트(사업보고서/회계기준서)는 chunk 단위로 임베딩해 FAISS 벡터 DB로, 정형 재무 데이터는 DART Open API로 조회해 최신성/정확성 확보. 복합 질문은 벡터 검색 + DART API 병행 |
| **질문 유형 분기(멀티-체인)** | 질문 의도(5종)를 먼저 분류한 뒤 유형별 전문 체인·리트리버를 동적으로 선택, 단일 파이프라인보다 정교한 맥락 맞춤형 응답 생성                                                |
| **이중 FAISS 인덱스 리트리버** | BAAI/bge-m3 임베딩으로 회계기준서(faiss_index3)·사업보고서(faiss_index_bge_m3) 두 인덱스를 로드, 각각 top-6 유사 문서를 검색하는 회계/사업 리트리버 구성           |
| **기업명 정규화·정보 추출** | 입력 기업명을 corp_list와 매칭해 공식 기업명으로 정규화하고 회사명/연도를 추출, 정규화된 기업명으로 고유 기업 코드를 조회해 DART API 호출에 활용                              |
| **답변 수준 분류** | 질문자가 원하는 수준(초급~고급)에 따라 쉬운 설명부터 전문적 설명까지 답변 수준을 분류해 제공                                                                   |
| **웹 인터페이스** | 챗봇과 함께 뉴스/주식 정보를 동시 제공, 관심기업·리포트, 댓글/좋아요, 회원/마이페이지, 소셜 로그인 구현                                                           |


### 🏗️ 시스템 아키텍처
<img src="images/img.png" width="auto" alt="아키텍처"/>

-  입력 → 질문 분류/정보 추출(LangGraph, GPT-4o) → 병렬 검색(FAISS · DART API) → 컨텍스트 결합 → 응답 생성(GPT-4o) → UI
-  LangGraph: 질문 분류·정보 추출·응답 생성을 단계별 노드로 분리하고 조건 분기로 흐름을 자동 제어
-  주식 리포트: LangChain 워크플로우로 FAISS(사업보고서) + DART API(재무제표)를 결합해 GPT-4o가 기업 분석 리포트를 생성
-  주식·뉴스: yfinance/pykrx, 네이버 뉴스(Open API + 크롤링/BeautifulSoup)로 조회 후 정제하여 UI에 표시

### ✨ 핵심 기능

| 기능 | 설명 |
|:---|:---|
| **기업 Q&A** | 사업/재무/회계/복합/기타 질문 유형 분류 후 맞춤 응답 제공 |
| **답변 수준 분류** | 초급(쉬운 설명)~고급(전문적 설명)까지 사용자가 원하는 수준으로 답변 제공 |
| **주식 분석 리포트** | 기업명 입력 시 사업보고서(FAISS) + 재무제표(DART)를 RAG로 가져와 GPT-4o가 분석 리포트 생성 |
| **최신 정보 반영** | 공시(DART)와 시장 데이터(yfinance/pykrx) 실시간 조회 |
| **주식/뉴스 패널** | 챗 영역과 나란히 배치해 탐색 효율 증대 |
| **관심기업·리포트/댓글·좋아요** | 사용자 참여 기능 제공 |
| **회원/소셜 로그인·마이페이지** | 사용자 관리 및 정보 수정 |

### 🚀 성능 개선 노력 (AI)

| 개선 포인트 | 내용 |
|:---|:---|
| **벡터 DB와 API 동시 사용** | 정적 데이터 검색용 벡터 DB와 동적 정보 조회용 실시간 API를 결합한 하이브리드 구조로, 벡터 DB에 모든 데이터를 저장하는 현실적 제약을 극복하고 내장 데이터만으로는 답할 수 없는 최신·외부 데이터 질문에 대응 |
| **질문 유형 다양화(멀티-체인)** | 질문 의도를 5가지로 먼저 분류하고, 유형별로 서로 다른 전문 체인·리트리버를 동적으로 선택. 단일 파이프라인 대비 더 정교하고 맥락에 맞는 답변으로 응답 전문성 극대화 |
| **LangGraph 활용** | 질문 분류·정보 추출·응답 생성을 단계별 노드로 나누고 조건 분기로 흐름을 자동 제어. 복잡한 질문도 유연하게 처리하고 질문에 맞는 응답 체인을 선택해 정확도를 높였으며, 사용자 수준별(초급~고급) 대응과 유지보수성까지 확보 |

### 🖼️ 서비스 화면
<img src="images/chat_page.png" width="auto" alt="채팅 페이지"/>
<br/>
<img src="images/chat_page2.png" width="auto" alt="채팅 페이지2"/>
<br/>
<img src="images/stock.png" width="auto" alt="주식 정보"/>
<br/>
<img src="images/stock2.png" width="auto" alt="주식 정보2"/>
<br/>
<img src="images/login.png" width="auto" alt="로그인"/>
<br/>
<img src="images/signup.png" width="auto" alt="회원가입"/>
<br/>
<img src="images/mypage.png" width="auto" alt="마이페이지"/>
<br/>
<img src="images/mypage_edit.png" width="auto" alt="마이페이지 수정"/>

### 🛠️ 기술 스택

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-00863D?style=for-the-badge&logo=langchain&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-1E90FF?style=for-the-badge&logo=graphviz&logoColor=white)
![RAG](https://img.shields.io/badge/RAG-8A2BE2?style=for-the-badge&logoColor=white)
![Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Amazon AWS](https://img.shields.io/badge/Amazon_AWS-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white)
![FAISS](https://img.shields.io/badge/FAISS-4B8BEA?style=for-the-badge&logo=facebook&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![BAAI/bge-m3](https://img.shields.io/badge/BAAI/bge--m3-000000?style=for-the-badge&logo=huggingface&logoColor=white)
![GPT-4o](https://img.shields.io/badge/GPT--4o-4B91FF?style=for-the-badge&logo=openai&logoColor=white)
![Open DART API](https://img.shields.io/badge/Open%20DART%20API-002D61?style=for-the-badge&logoColor=white)
![yfinance](https://img.shields.io/badge/yfinance-144E8C?style=for-the-badge&logo=yahoo&logoColor=white)
![pykrx](https://img.shields.io/badge/pykrx-1F9F3F?style=for-the-badge&logoColor=white)
![Naver News](https://img.shields.io/badge/Naver%20News%20Crawling-03C75A?style=for-the-badge&logo=naver&logoColor=white)
![Google/Naver/Kakao Login API](https://img.shields.io/badge/Social%20Login-6A5ACD?style=for-the-badge&logoColor=white)

> 전체 프로젝트 깃허브 링크: https://github.com/SKNETWORKS-FAMILY-AICAMP/SKN14-4th-2Team

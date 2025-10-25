## 📊 기업 정보 분석 및 요약 챗봇 Portfolio (정민영)

### 🎯 프로젝트 주제 및 개요
- **목표**: 비전문가도 이해할 수 있게 기업의 사업/재무 핵심 정보를 요약하고, 최신 공시/시장 데이터와 결합해 질의응답을 제공
- **기간**: 2025.08.07 ~ 2025.08.08 (2일)
- **핵심**: 벡터 검색(FAISS) + 실시간 API(DART, yfinance/pykrx)를 결합한 하이브리드 검색과 LangGraph 기반 워크플로우

### 🔗 시연 영상: https://youtu.be/Dd6SCocLpJo?si=vHYwAnm9P3TEYT75

### 🙋 나의 역할
- **LangGraph 개발**: 질문 유형 분류(사업/재무/회계/복합/기타), 회사명/연도 추출, 하이브리드 검색 분기, 응답 생성 체인 설계/구현
- **Django 웹 개발**: 웹 챗 UI, 뉴스/주식 사이드 패널, 관심기업·종합보고서, 댓글/좋아요, 회원/마이페이지 등 핵심 화면 구현
- **배포**: Docker 기반 배포 구성(AWS Docker 배포), 웹서버 설정 포함

### 📈 구현한 결과
- **하이브리드 검색 구조**: 비정형 텍스트는 FAISS, 정형 재무 데이터는 DART Open API로 조회해 최신성/정확성 확보
- **질문 유형 분기**: 질문 의도(5종)별 전문 체인·리트리버를 동적으로 선택, 맥락 맞춤형 응답
- **웹 인터페이스**: 챗봇과 함께 뉴스/주식 정보를 동시 제공, 관심기업·리포트, 댓글/좋아요, 회원/마이페이지, 소셜 로그인 구현


### 🏗️ 시스템 아키텍처
<img src="images/img.png" width="auto" alt="아키텍처"/>

-  입력 → 질문 분류/정보 추출(LangGraph, GPT-4o) → 병렬 검색(FAISS · DART API) → 컨텍스트 결합 → 응답 생성(GPT-4o) → UI
-  주식·뉴스: yfinance/pykrx, 네이버 뉴스(Open API + 크롤링)로 조회 후 정제하여 UI에 표시

### ✨ 핵심 기능
- **기업 Q&A**: 사업/재무/회계/복합/기타 질문 유형 분류 후 맞춤 응답 제공
- **최신 정보 반영**: 공시(DART)와 시장 데이터(yfinance/pykrx) 실시간 조회
- **주식/뉴스 패널**: 챗 영역과 나란히 배치해 탐색 효율 증대
- **관심기업·리포트/댓글·좋아요**: 사용자 참여 기능 제공
- **회원/소셜 로그인·마이페이지**: 사용자 관리 및 정보 수정

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

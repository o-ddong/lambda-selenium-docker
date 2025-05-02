# 🐳 lambda-selenium-docker

AWS Lambda 환경에서 Selenium을 Docker 이미지로 실행할 수 있도록 구성한 프로젝트입니다.  
Headless Chrome을 사용하여 브라우저 자동화나 웹 크롤링 작업을 Lambda에서도 손쉽게 실행할 수 있습니다.

---

## 🔍 상세 설명 (블로그 참고)

> 이 프로젝트의 개발 동기 및 진행 과정, 트러블슈팅 등 자세한 내용은 아래 블로그에 정리되어 있습니다.  
👉 [블로그: 🐳 Docker + ECR + Lambda로 크롤링 도전!](https://velog.io/@odh0112/Docker-ECR-Lambda%EB%A1%9C-%ED%81%AC%EB%A1%A4%EB%A7%81-%EB%8F%84%EC%A0%84)

---

## 🚀 빠른 시작

이미지 빌드 이후 ECR 업로드 및 람다 실행 관련해서는 블로그 참고해 주시면 됩니다.

```bash
# 1. 저장소 클론
git clone https://github.com/yourname/lambda-selenium-docker.git
cd lambda-selenium-docker

# 2. Docker 이미지 빌드
docker build --platform linux/x86_64 -t crawler -f Dockerfile .
```

---

## 📁 디렉터리 구조

```
lambda-selenium-docker/
├── Dockerfile           # Lambda Python 3.13 Dockerfile
├── python3.9/
│ ├── Dockerfile         # Lambda Python 3.9 Dockerfile
│ └── chrome-deps.txt    # Python 3.9 버전용 Chrome 의존성 리스트 (yum)
├── chrome-deps.txt      # Python 3.13 버전용 Chrome 의존성 리스트 (dnf)
├── install-browser.sh   # 공통 Chrome 설치 스크립트
├── crawler.py           # 크롤링 실행 스크립트
├── requirements.txt     # 파이썬 필요한 패키지 모음
└── README.md
```

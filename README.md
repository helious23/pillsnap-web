# PillSnap Web

PillSnap 서비스의 공식 웹사이트 및 랜딩 페이지입니다.

## 🌐 라이브 사이트

- **Production**: https://www.pillsnap.co.kr
- **Hosting**: Cloudflare Pages
- **Repository**: https://github.com/helious23/pillsnap-web

## 📁 프로젝트 구조

```
web/
├── assets/                 # 정적 자원 파일
│   ├── css/               # 스타일시트
│   │   └── style.css
│   ├── images/            # 이미지 파일
│   │   ├── favicon-32.png
│   │   ├── favicon.ico
│   │   ├── icon-64.png
│   │   └── icon-128.png
│   └── js/                # JavaScript 파일
│       ├── config.js      # 환경 설정 (자동 생성)
│       └── main.js
├── .github/
│   └── workflows/
│       └── deploy.yml     # GitHub Actions 배포 워크플로우
├── index.html             # 메인 페이지
├── privacy.html           # 개인정보처리방침
├── terms.html             # 이용약관
├── robots.txt             # 검색 엔진 크롤러 설정
├── sitemap.xml            # 사이트맵
├── .env.example           # 환경 변수 예제
├── .env                   # 환경 변수 (Git 제외)
├── .gitignore             # Git 제외 파일
├── build.sh               # 빌드 스크립트
└── README.md              # 이 파일
```

## 🚀 배포

### 자동 배포 (Cloudflare Pages)

1. `main` 브랜치에 push하면 자동으로 배포됩니다
2. Cloudflare Pages가 GitHub webhook을 통해 자동으로 감지하고 배포합니다

```bash
git add .
git commit -m "feat: 변경사항 설명"
git push origin main
```

### 환경 변수 설정

1. `.env.example` 파일을 복사하여 `.env` 파일 생성:

```bash
cp .env.example .env
```

2. `.env` 파일에 실제 값 입력:

```env
# Google Analytics Configuration
VITE_GA_MEASUREMENT_ID=G-YOUR_ACTUAL_ID

# Cloudflare Web Analytics Configuration
VITE_CF_BEACON_TOKEN=your_actual_token_here

# Web3Forms Configuration
VITE_WEB3FORMS_ACCESS_KEY=your_web3forms_key
```

3. GitHub Secrets 설정 (프로덕션용):
   - Repository Settings → Secrets and variables → Actions
   - 다음 시크릿 추가:
     - `GA_MEASUREMENT_ID`
     - `CF_BEACON_TOKEN`
     - `WEB3FORMS_ACCESS_KEY`

### 로컬 빌드

```bash
# 환경 변수를 적용하여 빌드
./build.sh
```

## 📊 분석 도구

### Google Analytics 4

1. [Google Analytics](https://analytics.google.com) 접속
2. 관리 → 데이터 스트림에서 측정 ID 확인
3. `.env` 파일의 `VITE_GA_MEASUREMENT_ID`에 설정

### Cloudflare Web Analytics

1. [Cloudflare Dashboard](https://dash.cloudflare.com) 접속
2. Analytics & Logs → Web Analytics
3. 사이트 추가 후 토큰 복사
4. `.env` 파일의 `VITE_CF_BEACON_TOKEN`에 설정

## 🔧 개발

### 로컬 서버 실행

```bash
# Python 사용
python -m http.server 8080

# Node.js 사용 (http-server 설치 필요)
npx http-server -p 8080
```

### 코드 수정 시

1. HTML/CSS/JS 파일 수정
2. 로컬에서 테스트
3. `git push`로 자동 배포

## 🔐 보안

- 환경 변수는 절대 커밋하지 않습니다 (`.gitignore`에 포함)
- API 키는 GitHub Secrets를 통해 관리합니다
- Cloudflare Pages의 환경 변수 기능을 활용합니다

## 📝 유지보수

### 이미지 최적화

- 웹용 이미지는 적절한 크기로 압축
- favicon은 여러 크기 제공 (32px, 64px, 128px)

### SEO 최적화

- `robots.txt` 정기적 업데이트
- `sitemap.xml` 페이지 추가 시 업데이트
- Open Graph 메타 태그 관리

## 🤝 기여

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Open a Pull Request

## 📄 라이선스

© 2025 PillSnap. All rights reserved.
# TeraGRID - 선박 사이버 보안 관제 시스템

TeraGRID는 선박 사이버 보안 관제를 위한 웹 기반 플랫폼입니다.

## 🚀 빠른 시작

### 로컬에서 실행

1. 저장소 클론
```bash
git clone <repository-url>
cd TeraGRID
```

2. 웹 서버 실행
```bash
# Python 3
python3 -m http.server 8000

# 또는 Node.js
npx http-server -p 8000
```

3. 브라우저에서 접속
```
http://localhost:8000
```

## 📄 페이지 구조

### 전체 페이지 목록
모든 페이지는 [pages.html](pages.html)에서 확인할 수 있습니다.

### 주요 섹션

- **공통 (Common)**: 로그인, 계정 복구, 프로필 관리
- **육상 관제**: 전체 선단 현황 대시보드
- **선박 상세 분석**: 자산 관리, 네트워크 구성
- **컴플라이언스 센터**: UR E26 규제 준수, 문서 관리
- **사이버 리스크 센터**: 경보, 사고 관리, 취약점 분석
- **인프라 로그**: IP/OT 트래픽 로그, 원격 접속 로그
- **정책 및 구성**: 존 설정, 허용 목록, 플레이북
- **관리**: 사용자 관리, 시스템 설정
- **선상 대시보드**: 선박 위기 대응 인터페이스

## 🌐 GitHub Pages 배포

### 자동 배포 (권장)

1. GitHub 저장소 생성
2. Settings → Pages로 이동
3. Source를 "Deploy from a branch" 선택
4. Branch를 "main" 선택
5. Save 클릭

### 수동 배포

```bash
# GitHub 저장소 추가 (처음 한 번만)
git remote add origin https://github.com/YOUR_USERNAME/TeraGRID.git

# 푸시
git push -u origin main
```

배포 후 `https://YOUR_USERNAME.github.io/TeraGRID/` 에서 접근 가능합니다.

## 📁 파일 구조

```
TeraGRID/
├── index.html                    # 로그인 페이지 (진입점)
├── pages.html                    # 전체 페이지 목록
├── common.css                    # 공통 스타일시트
├── img/                          # 이미지 리소스
└── [54개 페이지 파일들]
```

## 🛠️ 기술 스택

- HTML5
- CSS3 (Flexbox, Grid, Custom Properties)
- JavaScript (최소한의 클라이언트 인터랙션)
- Chart.js (데이터 시각화)
- Leaflet.js (지도)

## 📚 문서

- [CLAUDE.md](CLAUDE.md) - 프로젝트 상세 문서
- [DESIGN_SYSTEM.md](DESIGN_SYSTEM.md) - 디자인 시스템 가이드
- [UPDATES.md](UPDATES.md) - 업데이트 내역

## 📝 라이선스

이 프로젝트는 내부 사용을 위한 것입니다.


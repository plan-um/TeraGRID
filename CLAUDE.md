# TeraGRID - 선박 사이버 보안 관제 시스템

## 📚 INDEX (항상 읽을 것)
- Line 10-100: Core Decisions
- Line 102-200: Architecture & File Structure
- Line 202-400: Page Reference Guide
- Line 402-500: Component Patterns
- Line 502-600: Navigation & Routing
- Line 602-700: Known Issues & Future Work

---
메뉴구조도는 아래 문서를 그대로 참조해.

/Users/hallymchoi/Dev/Obsi/01 Project 문서/테라그리드-문서/테라그리드 메뉴구조도 1.0.md

---

## 🎯 Core Decisions

### 프로젝트 개요
**TeraGRID**는 선박 사이버 보안 관제를 위한 웹 기반 플랫폼입니다.
- **육상 관제 (FleetCommand)**: 전체 선단 모니터링 및 관리
- **선상 대시보드 (BridgeView)**: 선박 현장 위기 대응 인터페이스

### 핵심 설계 원칙

#### 1. Just-In-Time 페이지 개발
- 메뉴 구조도 기반 54개 페이지 (실제 52개 생성)
- 한글+숫자 파일명 규칙: `[번호]_[페이지명].html`
- 예: `3-1-2-1_HW자산목록.html`

#### 2. 파일명 규칙
```
스토리보드번호_페이지명.html
- 공백 없음
- 한글 그대로 사용
- 숫자는 하이픈(-)으로 구분
```

#### 3. 디자인 시스템
**색상 팔레트**:
- Primary: #7c3aed (보라색)
- Success: #10b981 (녹색)
- Warning: #f59e0b (황색)
- Danger: #ef4444 (적색)
- Gray: #f9fafb ~ #111827

**타이포그래피**: 시스템 폰트 스택
```css
font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
```

#### 4. 반응형 전략
- Desktop: 1400px+
- Tablet: 768px - 1400px
- Mobile: < 768px
- 사이드바는 모바일에서 숨김

---

## 🏗️ Architecture & File Structure

### 디렉토리 구조
```
TeraGRID/
├── index.html                    # 로그인 페이지 (진입점)
├── common.css                    # 공통 스타일시트
├── CLAUDE.md                     # 프로젝트 문서
├── img/                          # 이미지 리소스
│   ├── Logotype.svg
│   ├── Avatar.png
│   ├── search-lg.svg
│   ├── home-line.svg
│   └── [기타 아이콘들]
└── [52개 페이지 파일들]
```

### 기술 스택
- **HTML5**: 시맨틱 마크업
- **CSS3**: Flexbox, Grid, Custom Properties
- **JavaScript**: 최소한의 클라이언트 인터랙션
- **이미지**: SVG (아이콘), PNG (사진)

### 공통 컴포넌트
**common.css에 정의된 재사용 컴포넌트**:
- `.sidebar` - 네비게이션 사이드바
- `.card` - 카드 컨테이너
- `.table` - 데이터 테이블
- `.badge` - 상태 뱃지
- `.btn-*` - 버튼 변형들
- `.form-*` - 폼 요소들
- `.modal` - 모달 다이얼로그

---

## 📄 Page Reference Guide

### 섹션별 페이지 목록

#### 공통 (Common) - 3 pages
| 파일명 | 스토리보드 | 설명 |
|--------|-----------|------|
| index.html | 1-1 | 로그인 페이지 (진입점) |
| 1-2_아이디비밀번호찾기.html | 1-2 | 이메일로 계정 복구 |
| 1-3_내정보관리.html | 1-3 | 사용자 프로필 관리 |

#### 육상 관제 - 대시보드 (Fleet Command) - 1 page
| 파일명 | 스토리보드 | 설명 |
|--------|-----------|------|
| 2-1_대시보드.html | 2-1 | 전체 선단 현황 지도 기반 대시보드 |

#### 선박 상세 분석 (Vessel Analysis) - 9 pages
| 파일명 | 스토리보드 | 설명 |
|--------|-----------|------|
| 3-1-1_선박상세대시보드.html | 3-1-1 | 선박 사이버 보안 상태 요약 |
| 3-1-2-1_HW자산목록.html | 3-1-2-1 | HW(CBS) 자산 목록 테이블 |
| 3-1-2-2_HW자산상세.html | 3-1-2-2 | HW 자산 상세 정보 및 이력 |
| 3-1-2-3_HW자산등록수정.html | 3-1-2-3 | HW 자산 등록/수정 폼 |
| 3-1-2-4_SW자산목록.html | 3-1-2-4 | SW 자산 목록 및 취약점 정보 |
| 3-1-2-5_SW자산상세.html | 3-1-2-5 | SW 자산 상세 정보 |
| 3-1-2-6_SW자산등록수정.html | 3-1-2-6 | SW 자산 등록/수정 폼 |
| 3-1-3-1_퍼듀모델.html | 3-1-3-1 | 퍼듀 모델 네트워크 다이어그램 |
| 3-1-3-2_구성도모드.html | 3-1-3-2 | 네트워크 구성도 시각화 |

#### 컴플라이언스 센터 (Compliance) - 7 pages
| 파일명 | 스토리보드 | 설명 |
|--------|-----------|------|
| 3-2-1_컴플라이언스대시보드.html | 3-2-1 | UR E26 규제 준수 현황 |
| 3-2-2-1_URE26문서목록.html | 3-2-2-1 | UR E26 문서 목록 |
| 3-2-2-2_URE26문서생성.html | 3-2-2-2 | 자동 문서 생성 폼 |
| 3-2-2-3_URE26문서상세.html | 3-2-2-3 | 문서 뷰어/에디터 |
| 3-2-3-1_감사목록.html | 3-2-3-1 | 내부/외부 감사 이력 |
| 3-2-3-2_감사등록수정.html | 3-2-3-2 | 감사 일정 등록/수정 |
| 3-2-3-3_감사상세.html | 3-2-3-3 | 감사 결과 및 체크리스트 |

#### 사이버 리스크 센터 (Cyber Risk) - 10 pages
| 파일명 | 스토리보드 | 설명 |
|--------|-----------|------|
| 4-1-1_경보목록.html | 4-1-1 | 보안 경보 실시간 목록 |
| 4-1-2_경보상세.html | 4-1-2 | 경보 상세 + MITRE ATT&CK 매핑 |
| 4-1-3_사고관리.html | 4-1-3 | 사고 목록 및 처리 현황 |
| 4-1-4_사고대응.html | 4-1-4 | 플레이북 기반 사고 대응 |
| 4-2-1_취약점목록.html | 4-2-1 | 취약점 통합 조회 |
| 4-2-2_취약점상세.html | 4-2-2 | 취약점 상세 및 조치 가이드 |
| 4-2-3-1_SW취약버전목록.html | 4-2-3-1 | SW 취약 버전 정보 |
| 4-2-3-2_SW취약버전등록수정.html | 4-2-3-2 | 취약 버전 등록/수정 |
| 4-2-4_스캔관리.html | 4-2-4 | 취약점 스캔 명령 및 결과 |
| 4-3-1_위협인텔리전스.html | 4-3-1 | 위협 정보 피드 |

#### 인프라 로그 (Infrastructure Logs) - 3 pages
| 파일명 | 스토리보드 | 설명 |
|--------|-----------|------|
| 5-1-1_IP트래픽로그.html | 5-1-1 | IP 트래픽 로그 조회 |
| 5-1-2_OT트래픽로그.html | 5-1-2 | OT 프로토콜 트래픽 로그 |
| 5-2-1_원격접속로그.html | 5-2-1 | 원격 접속 세션 로그 |

#### 정책 및 구성 (Policy & Configuration) - 13 pages
| 파일명 | 스토리보드 | 설명 |
|--------|-----------|------|
| 6-1-1_존설정.html | 6-1-1 | 네트워크 존 정책 및 격리 설정 |
| 6-1-1-1_PIN입력.html | 6-1-1-1 | PIN 인증 모달 |
| 6-2-1-1_허용CBS목록.html | 6-2-1-1 | CBS 화이트리스트 |
| 6-2-1-2_허용CBS등록수정.html | 6-2-1-2 | CBS 등록/수정 폼 |
| 6-2-1-3_탐지차단로그.html | 6-2-1-3 | 비인가 CBS 탐지 로그 |
| 6-2-2-1_허용장치목록.html | 6-2-2-1 | 외부 장치 화이트리스트 |
| 6-2-2-2_허용장치등록수정.html | 6-2-2-2 | 장치 등록/수정 폼 |
| 6-2-2-3_탐지차단로그.html | 6-2-2-3 | 비인가 장치 탐지 로그 |
| 6-3-1_백업복원정책.html | 6-3-1 | CBS 백업/복원 관리 |
| 6-5-1_플레이북목록.html | 6-5-1 | 대응 플레이북 목록 |
| 6-5-2_플레이북생성수정.html | 6-5-2 | 플레이북 에디터 |

#### 관리 (Management) - 2 pages
| 파일명 | 스토리보드 | 설명 |
|--------|-----------|------|
| 7-1-1_사용자관리.html | 7-1-1 | 사용자 계정 관리 |
| 7-2-1_시스템설정.html | 7-2-1 | 시스템 환경 설정 |

#### 선상 대시보드 (Bridge View) - 6 pages
| 파일명 | 스토리보드 | 설명 |
|--------|-----------|------|
| 8-1-1_선상메인대시보드.html | 8-1-1 | 선박 위기 대응 메인 화면 (다크 테마) |
| 8-1-2_사고경보목록.html | 8-1-2 | 선상 사고 경보 목록 |
| 8-1-3_네트워크상태.html | 8-1-3 | 선박 네트워크 상태 다이어그램 |
| 8-1-4_사고대응가이드.html | 8-1-4 | 플레이북 체크리스트 |
| 8-1-5_원격접속관리.html | 8-1-5 | 원격 접속 모니터링 및 제어 |
| 8-2-1_시스템설정.html | 8-2-1 | 선상 시스템 설정 |

### 총 페이지 수: 52개
- 공통: 3개
- 대시보드: 1개
- 선박 상세 분석: 9개
- 컴플라이언스: 7개
- 사이버 리스크: 10개
- 인프라 로그: 3개
- 정책 및 구성: 13개
- 관리: 2개
- 선상 대시보드: 6개

---

## 🧩 Component Patterns

### 1. 사이드바 네비게이션
```html
<aside class="sidebar">
    <div class="logo">
        <img src="img/Logotype.svg" alt="TeraGRID" class="logo-svg">
    </div>
    <div class="search-box">
        <img src="img/search-lg.svg" alt="Search" class="search-icon">
        <input type="text" placeholder="검색">
    </div>
    <nav class="nav-menu">
        <a href="#" class="nav-item active">
            <img src="img/home-line.svg" alt="" class="nav-icon">
            <span>홈</span>
        </a>
        <!-- 추가 메뉴 항목들 -->
    </nav>
</aside>
```

### 2. 카드 레이아웃
```html
<div class="card">
    <div class="card-header">
        <h3 class="card-title">제목</h3>
        <button class="menu-btn">⋮</button>
    </div>
    <!-- 카드 내용 -->
</div>
```

### 3. 데이터 테이블
```html
<table class="table">
    <thead>
        <tr>
            <th>컬럼1</th>
            <th>컬럼2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>데이터1</td>
            <td>데이터2</td>
        </tr>
    </tbody>
</table>
```

### 4. 상태 뱃지
```html
<span class="badge badge-success">정상</span>
<span class="badge badge-warning">경고</span>
<span class="badge badge-danger">위험</span>
<span class="badge badge-info">정보</span>
```

### 5. 폼 구성
```html
<div class="form-group">
    <label class="form-label">레이블</label>
    <input type="text" class="form-input" placeholder="입력">
</div>
```

### 6. 모달 다이얼로그 (PIN 입력 등)
```html
<div class="modal-overlay">
    <div class="modal">
        <div class="modal-header">제목</div>
        <div class="modal-body">내용</div>
        <div class="modal-footer">
            <button class="btn btn-secondary">취소</button>
            <button class="btn btn-primary">확인</button>
        </div>
    </div>
</div>
```

---

## 🔌 Navigation & Routing

### 페이지 간 링크 규칙

#### 1. 로그인 플로우
```
index.html (로그인)
  ├─> 1-2_아이디비밀번호찾기.html (비밀번호 찾기)
  └─> 2-1_대시보드.html (로그인 후)
```

#### 2. 선박 상세 플로우
```
2-1_대시보드.html
  └─> 3-1-1_선박상세대시보드.html
        ├─> 3-1-2-1_HW자산목록.html → 3-1-2-2_HW자산상세.html
        ├─> 3-1-2-4_SW자산목록.html → 3-1-2-5_SW자산상세.html
        └─> 3-1-3-1_퍼듀모델.html
```

#### 3. 경보/사고 플로우
```
4-1-1_경보목록.html
  └─> 4-1-2_경보상세.html
        └─> 4-1-3_사고관리.html
              └─> 4-1-4_사고대응.html
```

#### 4. 정책 설정 플로우 (PIN 필요)
```
6-1-1_존설정.html
  └─> [정책 변경 시] 6-1-1-1_PIN입력.html (모달)
```

### Breadcrumb 패턴
```html
<div class="breadcrumb">
    <a href="2-1_대시보드.html">대시보드</a>
    <span class="breadcrumb-separator">/</span>
    <a href="3-1-1_선박상세대시보드.html">선박 상세</a>
    <span class="breadcrumb-separator">/</span>
    <span>HW 자산 목록</span>
</div>
```

---

## ⚠️ Known Issues

### 1. 미구현 기능
- JavaScript 인터랙션 (모달, 토글 등)
- 실시간 데이터 업데이트
- 차트 라이브러리 통합
- 지도 API 연동
- 폼 검증 로직
- 페이지네이션 동작
- 파일 업로드 기능

### 2. 데이터 처리
- 현재는 정적 샘플 데이터
- 백엔드 API 연동 필요
- WebSocket 실시간 통신 미구현

### 3. 접근성
- ARIA 레이블 추가 필요
- 키보드 네비게이션 개선 필요
- 스크린 리더 최적화 필요

### 4. 보안
- CSRF 토큰 미구현
- XSS 방어 로직 필요
- PIN 인증 실제 구현 필요

---

## 📦 Dependencies

### 현재 의존성
- **없음** (순수 HTML/CSS)

### 향후 필요한 라이브러리
1. **차트**: Chart.js 또는 D3.js
2. **지도**: Leaflet 또는 Mapbox
3. **아이콘**: 이미 SVG로 제공됨
4. **UI 프레임워크**: 선택 사항 (현재 커스텀 CSS 사용)

### 권장 백엔드 스택
- **API**: RESTful 또는 GraphQL
- **실시간**: WebSocket (Socket.io)
- **인증**: JWT 또는 Session
- **데이터베이스**: PostgreSQL (관계형) + Redis (캐시)

---

## 🚀 Next Steps

### 우선순위 1: 핵심 기능 구현
1. JavaScript 기본 인터랙션
   - 모달 open/close
   - 탭 전환
   - 드롭다운 메뉴
   - 폼 검증

2. 데이터 시각화
   - 차트 라이브러리 통합
   - 네트워크 다이어그램 인터랙티브화
   - 지도 API 연동

### 우선순위 2: 백엔드 연동
1. API 엔드포인트 정의
2. 데이터 모델 설계
3. 실시간 업데이트 구현
4. 인증/인가 시스템

### 우선순위 3: 개선 사항
1. 접근성 향상
2. 성능 최적화
3. 국제화 (i18n) 지원
4. 단위 테스트 작성

---

## 📝 Development Notes

### 파일 수정 시 주의사항
1. **파일명 변경 금지**: 메뉴 구조도와 일치해야 함
2. **common.css 수정 시**: 모든 페이지에 영향을 미침
3. **링크 변경 시**: 전체 네비게이션 플로우 확인 필요

### 새 페이지 추가 시
1. 메뉴 구조도 업데이트
2. 파일명 규칙 준수
3. common.css 활용
4. 네비게이션 링크 업데이트
5. CLAUDE.md 문서 업데이트

### 코드 스타일 가이드
- 들여쓰기: 4 spaces
- 한글 주석 권장
- BEM 방식 클래스 네이밍
- 시맨틱 HTML 사용

---

**마지막 업데이트**: 2025-10-04
**버전**: 1.0.0
**작성자**: Claude (Anthropic)

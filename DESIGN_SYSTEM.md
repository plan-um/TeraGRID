# TeraGRID Design System

## 🎨 Overview
TeraGRID의 선박 사이버 보안 관제 시스템을 위한 디자인 시스템입니다. 깔끔하고 프로페셔널한 블루 테마를 기반으로, 해양 산업과 사이버 보안의 신뢰성을 표현합니다.

**디자인 철학**: Linear, Stripe, Vercel과 같은 모던한 SaaS 플랫폼에서 영감을 받아, 직관적이고 효율적인 사용자 경험을 제공합니다.

---

## 🎨 Color Palette

### Primary Colors (Blue Theme)
```css
--primary: #0056B3;           /* 메인 블루 */
--primary-hover: #005BAA;     /* 호버 상태 */
--primary-dark: #0A1E3C;      /* 다크 네이비 */
--primary-light: #0066FF;     /* 라이트 블루 */
```

### Accent Colors
```css
--accent: #00B8D4;            /* 시안 */
--accent-light: #00E5FF;      /* 라이트 시안 */
--accent-hover: #00BCD4;      /* 시안 호버 */
```

### Status Colors
```css
--success: #10b981;           /* 정상/성공 */
--warning: #f59e0b;           /* 경고 */
--danger: #ef4444;            /* 위험/오류 */
--info: #00D4FF;              /* 정보 */
```

### Neutral Colors
```css
--gray-50: #f8fafc;
--gray-100: #f1f5f9;
--gray-200: #e2e8f0;
--gray-300: #cbd5e1;
--gray-400: #94a3b8;
--gray-500: #64748b;
--gray-600: #475569;
--gray-700: #334155;
--gray-800: #1e293b;
--gray-900: #0f172a;
```

### Background Colors
```css
--bg-main: #ffffff;           /* 메인 배경 */
--bg-secondary: #f8fafc;      /* 보조 배경 */
--bg-dark: #0A1E3C;           /* 다크 모드 배경 */
```

### Border Colors
```css
--border-color: #e2e8f0;      /* 기본 테두리 */
--border-hover: #0056B3;      /* 호버 테두리 */
```

---

## 📝 Typography

### Font Family
```css
font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
```

시스템 네이티브 폰트를 사용하여 빠른 로딩과 플랫폼별 최적화된 가독성을 제공합니다.

### Font Weights
- **400 (Regular)**: 본문 텍스트
- **500 (Medium)**: 강조된 텍스트, 네비게이션
- **600 (Semi-bold)**: 제목, 라벨
- **700 (Bold)**: 주요 헤딩, 강조

### Headings
```css
h1 {
    font-size: 32px;
    font-weight: 700;
    letter-spacing: -0.02em;
    line-height: 1.2;
}

h2 {
    font-size: 24px;
    font-weight: 700;
    letter-spacing: -0.01em;
}

h3 {
    font-size: 18px;
    font-weight: 600;
}

h4 {
    font-size: 16px;
    font-weight: 600;
}
```

### Body Text
```css
body {
    font-size: 14px;
    line-height: 1.6;
    color: var(--gray-900);
}

/* Small text */
.text-sm {
    font-size: 13px;
}

/* Extra small text */
.text-xs {
    font-size: 12px;
}
```

---

## 🧩 Components

### Logo
**파일**: `img/TG_logo-01.png`
- 네이비, 블루, 시안 계열의 방패 모양
- 보안과 신뢰를 상징
- 높이: 36px (사이드바), 56px (로그인 페이지)

### Buttons

#### Primary Button
```css
.btn-primary {
    background-color: var(--primary);
    color: white;
    padding: 10px 16px;
    border-radius: 8px;
    font-weight: 600;
    box-shadow: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
}

.btn-primary:hover {
    background-color: var(--primary-hover);
    box-shadow: 0 4px 6px -1px rgba(0, 86, 179, 0.2);
    transform: translateY(-1px);
}
```

#### Secondary Button
```css
.btn-secondary {
    background: var(--bg-main);
    border: 1px solid var(--border-color);
    color: var(--gray-700);
    padding: 10px 16px;
    border-radius: 8px;
}

.btn-secondary:hover {
    background-color: var(--gray-50);
    border-color: var(--gray-300);
}
```

#### Danger Button
```css
.btn-danger {
    background-color: var(--danger);
    color: white;
}

.btn-danger:hover {
    background-color: #dc2626;
}
```

### Cards
```css
.card {
    background: var(--bg-main);
    border: 1px solid var(--border-color);
    border-radius: 12px;
    padding: 24px;
    box-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.02);
    transition: all 0.2s;
}

.card:hover {
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
}
```

### Navigation

#### Sidebar
- Width: 280px
- Background: White with subtle shadow
- Fixed position
- Active state: Blue accent with left border

```css
.nav-item.active {
    background-color: rgba(0, 86, 179, 0.08);
    color: var(--primary);
    font-weight: 600;
}

.nav-item.active::before {
    content: '';
    position: absolute;
    left: 0;
    width: 3px;
    height: 20px;
    background: var(--primary);
    border-radius: 0 2px 2px 0;
}
```

### Form Elements

#### Input Fields
```css
.form-input {
    padding: 10px 12px;
    border: 1px solid var(--border-color);
    border-radius: 8px;
    background: var(--bg-main);
    transition: all 0.2s;
}

.form-input:focus {
    border-color: var(--primary);
    box-shadow: 0 0 0 3px rgba(0, 86, 179, 0.1);
}

.form-input:hover {
    border-color: var(--gray-300);
}
```

### Tables
```css
.table th {
    background-color: var(--gray-50);
    font-size: 12px;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.05em;
    color: var(--gray-600);
}

.table tr:hover {
    background-color: var(--gray-50);
}
```

### Badges
```css
.badge-success {
    background-color: #d1fae5;
    color: #065f46;
}

.badge-warning {
    background-color: #fef3c7;
    color: #92400e;
}

.badge-danger {
    background-color: #fee2e2;
    color: #991b1b;
}

.badge-primary {
    background-color: rgba(0, 86, 179, 0.1);
    color: var(--primary);
}
```

### Tabs
```css
.tabs {
    background: var(--bg-main);
    border: 1px solid var(--border-color);
    border-radius: 10px;
    padding: 4px;
}

.tab-btn.active {
    background-color: var(--gray-100);
    color: var(--gray-900);
    font-weight: 600;
    box-shadow: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
}
```

---

## 🌙 Dark Theme (선상 대시보드)

### Background Colors
```css
body {
    background-color: #1a1a1a;
    color: #ffffff;
}
```

### Widgets
```css
.widget-bridge {
    background: linear-gradient(135deg, rgba(10, 30, 60, 0.95) 0%, rgba(0, 31, 63, 0.95) 100%);
    border: 1px solid rgba(0, 86, 179, 0.3);
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.5), 0 0 0 1px rgba(0, 86, 179, 0.1);
}
```

### Header
```css
.bridge-header {
    background: linear-gradient(135deg, #0A1E3C 0%, #001F3F 100%);
    border-bottom: 2px solid #0056B3;
}
```

---

## 📐 Spacing System

### Padding/Margin Scale
```
4px   - xs
8px   - sm
12px  - md
16px  - lg
20px  - xl
24px  - 2xl
32px  - 3xl
48px  - 4xl
```

### Border Radius
```
6px   - Small elements (badges)
8px   - Medium elements (buttons, inputs)
10px  - Large elements (cards, modals)
12px  - Extra large (main containers)
16px  - Special (bridge dashboard widgets)
20px  - Login container
```

---

## 🎭 Shadows

### Elevation System
```css
/* Level 1: Subtle */
box-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.02);

/* Level 2: Default */
box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05), 0 2px 4px -1px rgba(0, 0, 0, 0.03);

/* Level 3: Raised */
box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);

/* Level 4: Modal */
box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);

/* Colored Shadow (Primary Button) */
box-shadow: 0 4px 6px -1px rgba(0, 86, 179, 0.2), 0 2px 4px -1px rgba(0, 86, 179, 0.1);
```

---

## ✨ Animations & Transitions

### Hover Effects
```css
transition: all 0.2s ease;

/* Button hover */
transform: translateY(-1px);

/* Card hover */
box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
```

### Focus States
```css
/* Input focus */
.form-input:focus {
    box-shadow: 0 0 0 3px rgba(0, 86, 179, 0.1);
}
```

### Pulse Animation (Critical Alerts)
```css
@keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.7; }
}

animation: pulse 2s infinite;
```

---

## 📱 Responsive Design

### Breakpoints
```css
/* Desktop */
@media (min-width: 1400px) { }

/* Tablet */
@media (max-width: 1400px) { }
@media (max-width: 1024px) { }

/* Mobile */
@media (max-width: 768px) { }
@media (max-width: 500px) { }
```

### Mobile Adaptations
- 사이드바: 모바일에서 숨김
- 그리드: 1열로 변경
- 패딩: 축소 (32px → 16px)
- 폰트 크기: 약간 축소

---

## 🎯 Design Principles

### 1. Clarity (명확성)
- 직관적인 정보 계층
- 명확한 시각적 피드백
- 일관된 용어 사용

### 2. Efficiency (효율성)
- 빠른 정보 접근
- 최소한의 클릭
- 키보드 단축키 지원

### 3. Consistency (일관성)
- 통일된 디자인 패턴
- 예측 가능한 동작
- 재사용 가능한 컴포넌트

### 4. Accessibility (접근성)
- 충분한 색상 대비
- 키보드 네비게이션
- 스크린 리더 호환

### 5. Trust (신뢰성)
- 프로페셔널한 외관
- 명확한 상태 표시
- 오류 방지 및 복구

---

## 🚀 Usage Guidelines

### Logo Usage
1. **위치**: 왼쪽 상단 (사이드바 또는 헤더)
2. **크기**: 최소 32px, 최대 56px
3. **여백**: 상하좌우 최소 12px
4. **변형 금지**: 비율 유지, 회전 금지

### Color Usage
1. **Primary**: 주요 액션, 활성 상태, 링크
2. **Accent**: 보조 강조, 차트 포인트
3. **Success**: 정상 상태, 완료 표시
4. **Warning**: 경고, 주의 필요
5. **Danger**: 오류, 위험, 삭제

### Button Hierarchy
1. **Primary**: 가장 중요한 액션 (1개만)
2. **Secondary**: 보조 액션
3. **Danger**: 위험한 액션 (삭제, 종료)

### Text Hierarchy
1. **H1**: 페이지 제목 (1개만)
2. **H2**: 섹션 제목
3. **H3**: 카드/위젯 제목
4. **Body**: 일반 텍스트
5. **Small**: 메타 정보, 설명

---

## 📦 File Structure

```
TeraGRID/
├── common.css           # 공통 스타일시트 (메인 디자인 시스템)
├── index.html           # 로그인 페이지 (블루 그라디언트)
├── 2-1_대시보드.html     # 육상 관제 대시보드 (라이트 모드)
├── 8-1-1_선상메인대시보드.html  # 선상 대시보드 (다크 모드)
└── img/
    ├── TG_logo-01.png   # 메인 로고
    └── [icons...]       # 각종 아이콘 (SVG)
```

---

## 🔄 Version History

### Version 2.0 (2025-10-13)
- **NEW**: TeraGRID 로고 적용
- **NEW**: 블루 테마 색상 시스템
- **UPDATE**: common.css 완전 리뉴얼
- **UPDATE**: 로그인 페이지 재디자인
- **UPDATE**: 선상 대시보드 블루 테마 적용
- **IMPROVED**: 호버 효과 및 인터랙션
- **IMPROVED**: 그림자 및 레이어링

### Version 1.0 (2025-10-04)
- Initial design system
- Purple theme
- 52 pages created

---

## 📞 Contact & Support

디자인 시스템 관련 문의:
- **Email**: design@teragrid.com
- **Docs**: /DESIGN_SYSTEM.md
- **Dev Docs**: /CLAUDE.md

---

**Last Updated**: 2025-10-13
**Version**: 2.0.0
**Created by**: Claude (Anthropic)

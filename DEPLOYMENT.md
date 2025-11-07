# GitHub Pages 배포 가이드

## 1단계: GitHub 저장소 생성

1. GitHub에 로그인
2. 우측 상단의 `+` 버튼 클릭 → `New repository` 선택
3. 저장소 이름 입력 (예: `TeraGRID`)
4. Public 또는 Private 선택
5. **README, .gitignore, license는 추가하지 않음** (이미 있음)
6. `Create repository` 클릭

## 2단계: 원격 저장소 추가 및 푸시

터미널에서 다음 명령어 실행:

```bash
cd /Users/hallymchoi/Dev/Projects/TeraGRID

# 원격 저장소 추가 (YOUR_USERNAME과 REPO_NAME을 실제 값으로 변경)
git remote add origin https://github.com/YOUR_USERNAME/REPO_NAME.git

# 푸시
git push -u origin main
```

## 3단계: GitHub Pages 활성화

1. GitHub 저장소 페이지로 이동
2. `Settings` 탭 클릭
3. 왼쪽 메뉴에서 `Pages` 클릭
4. `Source` 섹션에서:
   - `Deploy from a branch` 선택
   - Branch: `main` 선택
   - Folder: `/ (root)` 선택
5. `Save` 클릭

## 4단계: 배포 확인

몇 분 후 다음 URL에서 사이트 접근 가능:
```
https://YOUR_USERNAME.github.io/REPO_NAME/
```

예: `https://hallymchoi.github.io/TeraGRID/`

## 주요 페이지

- **메인 페이지**: `https://YOUR_USERNAME.github.io/REPO_NAME/` (로그인 페이지)
- **전체 페이지 목록**: `https://YOUR_USERNAME.github.io/REPO_NAME/pages.html`

## 문제 해결

### 브랜치 이름이 'main'이 아닌 경우
```bash
# 현재 브랜치 확인
git branch

# 브랜치 이름 변경 (필요시)
git branch -M main
```

### 이미 원격 저장소가 있는 경우
```bash
# 기존 원격 저장소 확인
git remote -v

# 기존 원격 저장소 제거 후 재추가
git remote remove origin
git remote add origin https://github.com/YOUR_USERNAME/REPO_NAME.git
```


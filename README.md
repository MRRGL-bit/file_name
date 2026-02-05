# K Drama Hunters

드라마 촬영지 여행 가이드 웹사이트입니다. React + Vite + Tailwind CSS로 구성되어 있습니다.

## 구글 지도 API 연동

상단 Tour Map에 구글 지도를 사용하려면 API 키를 설정하세요.

### 1. API 키 발급 (이미 있으면 생략)

1. [Google Cloud Console](https://console.cloud.google.com/) 로그인
2. **API 및 서비스** → **사용자 인증 정보** → **사용자 인증 정보 만들기** → **API 키**
3. **Maps Embed API** 사용 설정: **API 및 서비스** → **라이브러리** → "Maps Embed API" 검색 → **사용** 클릭
4. (권장) API 키 제한 설정: **애플리케이션 제한**에서 "HTTP 리퍼러" 선택 후, 로컬·배포 도메인 추가  
   예: `http://localhost:*`, `https://your-site.vercel.app/*`

### 2. 로컬에서 연동

1. 프로젝트 루트에 `.env` 파일 생성
2. 아래 한 줄 추가 (키를 본인 키로 바꿈):

   ```
   VITE_GOOGLE_MAPS_API_KEY=여기에_발급받은_API_키_입력
   ```

3. `npm run dev`로 실행하면 Tour Map에 구글 지도가 API 키로 로드됩니다.

### 3. Vercel 배포 시 연동

1. [Vercel](https://vercel.com) → 해당 프로젝트 → **Settings** → **Environment Variables**
2. **Name**: `VITE_GOOGLE_MAPS_API_KEY`  
   **Value**: 발급받은 구글 지도 API 키
3. **Save** 후 재배포(또는 다음 푸시 시 자동 배포)

키가 없어도 지도 링크(새 탭)는 그대로 동작하며, 상단 임베드 지도만 키 없이 기본 URL로 표시됩니다.

---

## 로컬 실행

```bash
# 의존성 설치
npm install

# 개발 서버 실행 (http://localhost:5173)
npm run dev

# 프로덕션 빌드
npm run build

# 빌드 결과 미리보기
npm run preview
```

## Git에 올리기

```bash
git init
git add .
git commit -m "Initial commit: K Drama Hunters"
git branch -M main
git remote add origin https://github.com/사용자명/저장소명.git
git push -u origin main
```

### 수정사항을 file_name 저장소에 올리기

- **한 번에 커밋 + 푸시**: `npm run ship` (변경 파일이 있을 때만 커밋 후 푸시)
- **커밋 후 자동 푸시**: 이 프로젝트에 설정된 `post-commit` 훅이 커밋할 때마다 `git push origin main`을 실행합니다.  
  (`git add .` → `git commit -m "메시지"` 만 해도 자동으로 푸시됨)

## Vercel로 배포하기

1. [Vercel](https://vercel.com)에 로그인합니다.
2. **Add New** → **Project**를 선택합니다.
3. GitHub/GitLab/Bitbucket에서 이 저장소를 연결하거나, **Import Git Repository**로 저장소 URL을 입력합니다.
4. Vercel이 자동으로 프로젝트 타입(Vite)을 감지합니다.  
   - **Build Command**: `npm run build`  
   - **Output Directory**: `dist`  
   - **Install Command**: `npm install`
5. **Deploy**를 클릭하면 빌드 후 배포됩니다.
6. 이후 저장소에 푸시할 때마다 자동으로 재배포됩니다.

### 수동 배포 (Vercel CLI)

```bash
npm i -g vercel
vercel
```

프롬프트에 따라 로그인 후 프로젝트를 연결하면 배포됩니다.

## 기술 스택

- **React 18**
- **Vite 5**
- **Tailwind CSS 3**
- **lucide-react** (아이콘)

## 라이선스

© 2026 K DRAMA HUNTERS KOREA. ALL RIGHTS RESERVED.

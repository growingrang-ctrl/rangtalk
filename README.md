# 랑쌤과의 느슨톡 — 배포 가이드

## 폴더 구조
```
rangsaem-app/
├── api/
│   └── search.js     ← Anthropic API 키를 숨기는 서버 함수
├── public/
│   └── index.html    ← 사이트 프론트엔드
└── vercel.json       ← Vercel 설정
```

---

## 배포 방법 (Vercel, 무료)

### 1단계 — GitHub에 올리기
1. [github.com](https://github.com) 접속 → 로그인 (없으면 가입)
2. 우상단 **+** → **New repository**
3. Repository name: `rangsaem-app` → **Create repository**
4. 파일 업로드: **uploading an existing file** 클릭
5. 이 폴더 안의 파일들을 전부 드래그앤드롭 (폴더 구조 유지)
6. **Commit changes** 클릭

### 2단계 — Vercel에 배포하기
1. [vercel.com](https://vercel.com) 접속 → GitHub 계정으로 로그인
2. **Add New Project** → `rangsaem-app` 선택 → **Import**
3. **Deploy** 클릭 (설정 건드릴 것 없음)
4. 배포 완료되면 `xxx.vercel.app` URL 생성됨

### 3단계 — API 키 등록 (중요!)
1. Vercel 대시보드 → 해당 프로젝트 클릭
2. **Settings** → **Environment Variables**
3. 아래 내용 입력:
   - Name: `ANTHROPIC_API_KEY`
   - Value: `sk-ant-api03-...` (본인의 Anthropic API 키)
4. **Save** 클릭
5. **Deployments** 탭 → **Redeploy** (환경변수 적용을 위해 재배포 필요)

---

## API 키 발급
[console.anthropic.com/settings/keys](https://console.anthropic.com/settings/keys)
- 무료 크레딧 $5 제공
- 검색 1회 약 $0.003~0.005 (약 4~7원)

---

## 완료
이제 사용자는 API 키 없이 URL만으로 바로 사용 가능합니다.

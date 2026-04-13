# 🗓 노션 캘린더 위젯

노션 DB와 연동되는 심플 캘린더 위젯이에요.

## 파일 구조
```
calendar-widget/
├── api/
│   └── events.js       ← 노션 API 호출 (서버)
├── public/
│   └── index.html      ← 캘린더 위젯 UI
└── vercel.json         ← Vercel 설정
```

## 배포 방법 (Vercel)

### 1. GitHub에 올리기
```bash
git init
git add .
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/[내계정]/calendar-widget.git
git push -u origin main
```

### 2. Vercel 연결
1. vercel.com 접속 → Add New Project
2. GitHub 레포 선택 → Import
3. **Environment Variables** 에 아래 두 개 추가:
   - `NOTION_TOKEN` = `ntn_xxxxxxxxxx` (노션 통합 토큰)
   - `NOTION_DB_ID` = `ad817161d52345f9a9a5694a22a5aa11` (캘린더 DB ID)
4. Deploy 클릭!

### 3. 노션에 임베드
배포 완료 후 생성된 URL (예: `https://calendar-widget-heev.vercel.app`)을
노션 페이지에서 `/embed` 로 삽입하면 끝!

## 주요 기능
- 오늘 날짜 파란 배경 강조
- 중요 일정 핑크 배경 + 핑크 점
- 날짜 클릭 → 해당 날 일정만 보기
- ↻ 버튼으로 새로고침
- 토큰은 서버에만 보관 (보안 안전)

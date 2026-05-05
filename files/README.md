# kun.log

프레젠테이션 모음 - GitHub Pages + Reveal.js

## 📖 소개

이 저장소는 프레젠테이션을 온라인으로 호스팅하고 공유하기 위한 공간입니다.

## 🚀 시작하기

### 로컬에서 확인
1. 저장소 복제:
```bash
git clone https://github.com/GuiuSung/kun.log.git
cd kun.log
```

2. 간단한 HTTP 서버 실행:
```bash
# Python 3
python -m http.server 8000

# Node.js (http-server)
npx http-server
```

3. 브라우저에서 `http://localhost:8000` 열기

### GitHub Pages로 배포
1. 저장소 Settings → Pages
2. Source: `main` 브랜치 선택
3. Save 클릭
4. `https://GuiuSung.github.io/kun.log`에서 접속 가능

## 📁 폴더 구조

```
kun.log/
├── index.html                    # 홈페이지 (프레젠테이션 목록)
├── presentation-sample.html      # 샘플 프레젠테이션
├── presentation-1.html           # 새로운 프레젠테이션 (추가 예정)
├── README.md                     # 이 파일
└── assets/
    ├── images/                   # 이미지 폴더
    └── css/                      # 커스텀 스타일
```

## 🎨 새로운 프레젠테이션 추가하기

### 방법 1: HTML 직접 작성
1. `presentation-name.html` 파일 생성
2. 아래 기본 템플릿 사용:

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>제목</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/reveal.js@4.5.0/dist/reveal.css">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/reveal.js@4.5.0/dist/theme/black.css">
</head>
<body>
    <div class="reveal">
        <div class="slides">
            <section>
                <h1>제목</h1>
            </section>
            <section>
                <h2>슬라이드 2</h2>
            </section>
        </div>
    </div>
    
    <script src="https://cdn.jsdelivr.net/npm/reveal.js@4.5.0/dist/reveal.js"></script>
    <script>
        Reveal.initialize();
    </script>
</body>
</html>
```

3. `index.html`에 링크 추가:
```html
<a href="presentation-name.html" class="presentation-card">
    <div class="card-header">
        <h3>프레젠테이션 제목</h3>
    </div>
    <div class="card-body">
        <p>프레젠테이션 설명</p>
    </div>
</a>
```

### 방법 2: 마크다운 사용 (더 간단함)
마크다운 파일을 별도로 작성하고 Reveal.js에 포함:

```html
<section data-markdown="slides.md"></section>
```

## ⌨️ 프레젠테이션 조작법

| 키 | 기능 |
|---|---|
| `→` / `←` | 다음/이전 슬라이드 |
| `↓` / `↑` | 세로 네비게이션 |
| `ESC` | 전체 개요 보기 |
| `F` | 전체화면 |
| `S` | 발표자 노트 (별도 창) |
| `B` / `.` | 검은 화면 |

## 🎨 테마 변경

`<link>` 태그에서 테마 변경:

```html
<!-- 기본 테마들 -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/reveal.js@4.5.0/dist/theme/black.css">
<!-- black, white, league, sky, beige, simple, serif, blood, night, moon, solarized -->
```

## 🔧 커스터마이징

### 색상 변경 (CSS)
```css
:root {
    --r-main-color: #fff;
    --r-main-bg-color: #222;
    --r-heading-color: #fff;
    --r-link-color: #42b983;
}
```

### 폰트 변경
```css
:root {
    --r-main-font: 'Your Font', sans-serif;
    --r-code-font: 'Monaco', monospace;
}
```

## 📚 참고 자료

- [Reveal.js 공식 문서](https://revealjs.com/)
- [GitHub Pages 가이드](https://docs.github.com/en/pages)
- [마크다운 가이드](https://www.markdownguide.org/)

## 📝 라이센스

MIT License

## 💬 피드백

문제가 있거나 개선 사항이 있으면 Issues를 통해 알려주세요!

---

**Happy Presenting! 🎉**

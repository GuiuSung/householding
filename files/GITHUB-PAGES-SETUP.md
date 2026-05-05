# 🚀 GitHub Pages 배포 가이드

## Step 1: 로컬 저장소 클론

```bash
# 터미널 열기
git clone https://github.com/GuiuSung/kun.log.git
cd kun.log
```

## Step 2: 파일 추가

준비된 파일들을 저장소에 추가합니다:
- `index.html` - 홈페이지
- `presentation-sample.html` - 샘플 프레젠테이션
- `README.md` - 프로젝트 설명

## Step 3: Git 커밋 및 푸시

```bash
# 모든 파일 추가
git add .

# 커밋
git commit -m "Add initial presentation setup"

# 푸시
git push origin main
```

## Step 4: GitHub Pages 활성화

### 4-1. GitHub 웹사이트에서
1. https://github.com/GuiuSung/kun.log 접속
2. **Settings** 탭 클릭
3. 좌측 메뉴에서 **Pages** 선택

### 4-2. Pages 설정
- **Source** 섹션에서 **Deploy from a branch** 선택
- **Branch**: `main` 선택
- **Folder**: `/ (root)` 선택
- **Save** 클릭

## Step 5: 배포 확인

약 1-2분 후:
1. Settings → Pages로 다시 가보기
2. 맨 위에 초록색 체크마크와 배포 URL 표시됨
3. `https://GuiuSung.github.io/kun.log`로 접속 가능

## ✅ 배포 확인 체크리스트

- [ ] GitHub에 파일이 모두 푸시됨
- [ ] Settings → Pages에서 branch가 `main`으로 설정됨
- [ ] 배포 상태가 "ready" 또는 "Active"
- [ ] URL로 접속 가능

## 🔄 이후 업데이트 방법

새로운 프레젠테이션 추가할 때마다:

```bash
# 새 파일 작성 (예: presentation-2.html)
# index.html에 링크 추가

# 커밋 및 푸시
git add .
git commit -m "Add new presentation"
git push origin main

# 자동으로 배포됨 (1-2분 소요)
```

## ❓ 문제 해결

### URL에 접속해도 404 에러가 나요
- [ ] Repository settings에서 Pages가 활성화되었나?
- [ ] Branch가 `main`으로 설정되었나?
- [ ] 파일이 정말로 푸시되었나? (`git log`로 확인)
- [ ] 시간이 충분히 지났나? (1-2분 기다려보기)

### 변경사항이 반영되지 않아요
- [ ] 파일을 수정 후 `git push` 했나?
- [ ] 브라우저 캐시 삭제 (Ctrl+Shift+Delete)
- [ ] 몇 분 더 기다려보기

### CNAME이나 커스텀 도메인을 원해요
- Settings → Pages에서 Custom domain 설정 가능
- 도메인 DNS 설정 필요 (자세한 방법은 GitHub 문서 참고)

## 📖 추가 자료

- [GitHub Pages 공식 문서](https://docs.github.com/en/pages)
- [Reveal.js 문서](https://revealjs.com/)
- [마크다운 가이드](https://www.markdownguide.org/)

---

이제 당신의 프레젠테이션이 전 세계에서 접속 가능해집니다! 🎉

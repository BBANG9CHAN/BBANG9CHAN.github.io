# BBANG9CHAN.github.io

만들어 본 것들을 정리해 두는 페이지입니다. GitHub Pages로 배포합니다. → <https://bbang9chan.github.io>

빌드 도구 없이 HTML·CSS 파일만 있습니다. 파일을 고쳐 `main` 에 push 하면 1~2분 뒤 사이트에 반영됩니다.

## 파일

| 파일 | 내용 |
|---|---|
| `index.html` | 페이지 전체 |
| `style.css` | 디자인. 색은 맨 위 `:root` 에 모여 있고, 다크 모드 색은 바로 아래 블록에 있음 |
| `favicon.svg` | 브라우저 탭 아이콘 |
| `.nojekyll` | GitHub Pages 의 Jekyll 변환을 끔 (파일을 그대로 배포) |
| `docs/` | 작업 기록 (`YYYY-MM-DD-주제.md`) |

## 미리보기

이 폴더에서:

```bat
python -m http.server 8000
```

브라우저에서 <http://localhost:8000> 을 엽니다.

## 항목 추가·수정

`index.html` 에서 `<li class="item">` 하나가 항목 하나입니다. 기존 항목을 복사해서 고치면 됩니다.

- 비공개 저장소: GitHub 링크 대신 `<span class="label">비공개</span>` (lotto_auto 항목 참고)
- 아직 만드는 중: 이름 옆에 `<span class="label">만드는 중</span>` (hub 항목 참고)

## 그림 넣기 (선택)

이미지를 `assets/screenshots/` 에 넣고, 항목 설명 아래에 한 줄 추가합니다.

```html
<img class="shot" src="assets/screenshots/job_watch.png" alt="Job Watch 화면" loading="lazy">
```

> 웹후크 URL, 개인 검색 조건, 로또 번호·구매 이력처럼 공개되면 안 되는 내용이 화면에 보이지 않는지 확인한 뒤 올리세요.

# 2026-10-19 GitHub Pages 정리 페이지 만들기

## 목표

GitHub에 올린 것들을 한 페이지에 정리해서 <https://bbang9chan.github.io> 로 띄운다.

## 진행

1. **10-19** 포트폴리오형 구성안을 제안함: 큰 소개 문구, 프로젝트 카드(스크린샷 자리·핵심 기능·기술 태그), 기술 스택.
   lotto_auto 는 사용자 결정으로 저장소 링크 없이 설명만 넣기로 함.
2. **10-20** 로컬 미리보기를 본 사용자가 "포트폴리오 느낌이 너무 나고 과장된 것 같다, 했던 것 정리 정도가 좋다"고 해서
   소박한 목록형으로 다시 만듦.
   - 뺀 것: 큰 소개 문구, 키워드 배지, 카드와 스크린샷 자리, 핵심 기능 목록, 기술 스택 섹션, 상단 메뉴
   - 남긴 것: 이름과 한두 줄 소개, "만든 것들" 목록(이름, 한두 문장 설명, 쓴 도구 한 줄, GitHub 링크)

## 결정

- 저장소: `BBANG9CHAN/BBANG9CHAN.github.io` (공개). 사용자 사이트 저장소라 `main` 브랜치 루트를 그대로 배포. `.nojekyll` 로 Jekyll 변환을 끈다.
- 빌드 도구 없이 `index.html` + `style.css`. 글꼴은 Pretendard(jsDelivr CDN), 못 받으면 시스템 글꼴. 라이트/다크 자동 전환.
- 항목 (설명은 각 저장소 README에서 뽑음)
  - job_watch, megabox_watch: 공개 저장소, GitHub 링크
  - lotto_auto: 비공개 저장소. 링크 없이 설명만, "비공개" 표시
  - hub: `gh repo view BBANG9CHAN/hub --json visibility` 로 PUBLIC 확인 후 포함. 아직 만드는 중이라 "만드는 중" 표시
- 넣지 않은 것: 웹후크 URL, 로또 번호·구매/당첨 이력·구매 요일/시간, 개인 경로, 이메일·실명, 실제 화면 캡처

## 확인한 것

- 로컬 미리보기에서 데스크톱·휴대폰(375px), 라이트·다크 확인. 가로 넘침 없음.
- `index.html` 에 경로·웹후크·이메일·번호 같은 문자열이 없는지 grep 으로 확인.
- 미리보기 서버: Claude 앱의 `preview_start` 는 `G:\dev\.claude\launch.json` 을 요구해서 "G:\dev 최상위에는 프로젝트 폴더만" 규칙과 맞지 않음.
  대신 이 폴더에서 `python -m http.server` 로 띄웠다.

## 배포 (10-20)

- 사용자 승인 후 `gh repo create BBANG9CHAN/BBANG9CHAN.github.io --public` 로 저장소를 만들고 `main` 을 push.
- Pages 원본: `main` 브랜치 / 루트. 설정 확인은 `gh api repos/BBANG9CHAN/BBANG9CHAN.github.io/pages`.
- 이후 수정은 `main` 에 push 하면 1~2분 뒤 사이트에 반영된다.

## 다른 PC(BANG9)에서

```bat
git clone https://github.com/BBANG9CHAN/BBANG9CHAN.github.io G:\dev\BBANG9CHAN.github.io
```

SessionStart 훅이 `G:\dev` 아래 git 저장소를 자동으로 pull 하므로, 한 번 clone 해 두면 이후로는 따로 받을 필요가 없다.

## 남은 일

- 필요하면 항목에 그림 추가 (방법은 README)

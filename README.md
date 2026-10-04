# tetris-game

고전 아케이드 스타일의 테트리스. HTML, CSS, JavaScript로 구성되어 빌드나 패키지 설치 없이 실행됩니다.

## 시작 페이지

저장소 루트의 `index.html`이 시작 페이지입니다. `style.css`와 `game.js`는 상대 경로로 연결되어 GitHub Pages의 `/tetris-game/` 경로에서도 정상적으로 로드됩니다.

```text
tetris-game/
├── index.html
├── style.css
├── game.js
├── .nojekyll
├── .gitignore
├── README.md
└── .github/workflows/pages.yml
```

## GitHub Pages 배포

1. GitHub에서 `tetris-game`이라는 새 저장소를 만듭니다. 무료 개인 계정으로 Pages를 사용하려면 공개 저장소로 만듭니다.
2. 이 폴더의 파일을 저장소 루트에 올립니다. `.github/workflows/pages.yml`과 `.nojekyll`도 포함하고, `tetris-game` 폴더 자체를 한 단계 더 중첩하지 마세요.
3. 기본 브랜치를 `main`으로 설정합니다.
4. **Settings → Pages → Build and deployment → Source**에서 **GitHub Actions**를 선택합니다.
5. **Actions → Deploy game to GitHub Pages → Run workflow**에서 `main`을 선택해 실행합니다. 이후 `main`에 푸시하면 자동으로 배포됩니다.
6. 성공 후 **Settings → Pages** 또는 배포 작업에 표시된 주소로 접속합니다. 일반적인 주소는 `https://YOUR_USERNAME.github.io/tetris-game/`입니다.

워크플로는 게임 파일만 `_site`에 모아 배포합니다. `index.html`이 배포 결과의 루트에 위치합니다.

로컬 폴더를 Git으로 올리는 경우, 빈 저장소를 만든 뒤 이 폴더에서 실행합니다. `YOUR_USERNAME`을 본인의 GitHub 사용자명으로 바꾸세요.

```sh
git init
git add .
git commit -m "Add Tetris game and GitHub Pages deployment"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/tetris-game.git
git push -u origin main
```

## 로컬 실행

`index.html`을 브라우저로 열거나 다음 명령을 실행한 뒤 `http://localhost:8000`에 접속합니다.

```sh
python -m http.server 8000
```

## 조작

| 키 | 동작 |
| --- | --- |
| Enter | 시작 / 계속하기 |
| ← / → | 좌우 이동 |
| ↑ | 회전 |
| ↓ | 빠르게 내리기 |
| Space | 즉시 낙하 |
| P | 일시정지 / 계속하기 |

모바일은 화면 아래 버튼으로 조작합니다. 최고 점수는 브라우저에 저장되며 소리는 상단 버튼으로 켭니다. Google Fonts에 접속할 수 없어도 시스템 글꼴로 게임을 실행할 수 있습니다.

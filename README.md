# 나만의 컬러플 캐릭터 키링 만들기 디지털 툴

이 폴더는 GitHub Pages에 바로 게시할 수 있도록 **웹페이지(`index.html`)와 예시 이미지 2개를 분리한 배포판**입니다.

## 1. 폴더 구조

```text
컬러플_키링_GitHub_Pages/
├── index.html                 ← 웹페이지 코드 (첫 화면)
├── images/
│   ├── example1.png           ← 예시 1: 검정 테두리가 있는 고화질 캐릭터
│   └── example2.png           ← 예시 2: 파스텔 컬러 캐릭터
├── .nojekyll                  ← GitHub Pages에서 Jekyll 처리 비활성화 (선택)
└── README.md                  ← 지금 읽는 업로드 안내서
```

**중요:** `index.html`과 `images` 폴더는 같은 위치에 둡니다. `images` 안의 그림 파일 이름과 대소문자를 그대로 유지합니다. 압축 파일 자체가 아니라 **압축을 풀었을 때 나오는 파일과 폴더**를 GitHub 저장소에 올립니다.

## 2. GitHub 웹사이트에서 파일 올리기

1. [github.com](https://github.com)에 로그인한 후, 웹페이지를 공개할 **저장소(Repository)**로 들어갑니다. 없다면 **New repository**로 새로 만듭니다. GitHub Free 이용 시 GitHub Pages용 저장소는 **Public**으로 설정합니다.
2. 내려받은 ZIP 파일을 컴퓨터에서 **압축 해제**합니다.
3. 저장소 화면에서 **Add file → Upload files**를 선택합니다.
4. 압축을 푼 폴더 안의 **`index.html`, `images` 폴더, `README.md`**를 업로드 창으로 드래그합니다. `.nojekyll` 파일은 가능하면 함께 올려주세요. 브라우저에서 폴더 업로드가 안 되면 `images` 폴더를 먼저 만든 후 그 안에서 이미지 2개를 업로드하는 방식으로 진행할 수 있습니다.
5. 업로드 목록에 `index.html`, `images/example1.png`, `images/example2.png`가 올바르게 보이는지 확인합니다.
6. 아래의 **Commit changes**(또는 변경 사항 제안/병합)를 눌러 파일을 반영합니다.

> 기존에 같은 이름의 `index.html`이 있다면 새 파일이 기존 파일을 대체하도록 반영합니다. 이전 파일을 보관하려면 먼저 이름을 바꾸거나 백업합니다.

## 3. GitHub Pages 공개하기

1. 저장소에서 **Settings → Pages**로 이동합니다.
2. **Build and deployment → Source**를 **Deploy from a branch**로 정합니다.
3. **Branch**를 **main**, **Folder**를 **/(root)**로 선택하고 **Save**를 누릅니다.
4. 게시 작업이 완료되면 Pages 설정 화면의 **Visit site** 링크에서 열 수 있습니다.

보통 주소는 다음 형식입니다.

```text
https://내아이디.github.io/저장소이름/
```

사용자명과 저장소 이름은 예시입니다. 실제 주소는 GitHub Pages 설정 화면에서 확인하세요.

## 4. 이미지 연결 원리

`index.html`에 다음과 같은 **상대 경로**가 사용됩니다.

```html
<img src="images/example1.png" alt="예시 1 썸네일">
<img src="images/example2.png" alt="예시 2 썸네일">
```

자바스크립트에서도 다음 방식으로 불러옵니다.

```javascript
const SAMPLE1 = 'images/example1.png';
const SAMPLE2 = 'images/example2.png';
```

따라서 **`index.html`을 `images` 안으로 넣거나, 이미지를 다른 위치로 옮기면 표시되지 않습니다.**

## 5. 예시 이미지 바꾸기

새 이미지를 각각 `example1.png`, `example2.png`로 이름 지어 기존 파일과 교체하면 HTML 코드를 고칠 필요가 없습니다. 파일 이름을 바꾸는 경우에는 `index.html`의 모든 이미지 경로도 함께 바꿉니다.

## 6. 공개 전 확인

- 미리보기에서 예시 1·2가 각각 보이는지 확인합니다.
- 검정 테두리 / 검정 실루엣 미리보기와 PNG·SVG 저장을 확인합니다.
- 아래쪽 **개인정보 처리방침** 버튼이 열리는지 확인합니다.
- GitHub Pages 호스팅에서는 방문자 접속 관련 기술 기록이 플랫폼에 의해 처리될 수 있습니다. 필요하다면 개인정보 처리방침을 실제 운영 환경에 맞게 다시 확인합니다.
- **예시 이미지의 저작권·공개 배포 허락 여부를 확인**하세요. 허락이 불분명하면 직접 제작한 그림 또는 사용 허용 이미지를 사용하세요.

## 문제 해결

- **이미지가 안 보일 때:** 저장소의 `images` 폴더 안에 PNG가 있는지, 철자와 대소문자가 정확한지 확인합니다.
- **404 오류가 날 때:** `index.html`이 저장소 최상단에 있는지, Pages가 `main` + `/(root)`로 설정되어 있는지 확인합니다.
- **변경 사항이 보이지 않을 때:** GitHub Pages 배포 완료 여부를 확인하고, 브라우저 새로고침(필요하면 Ctrl+F5)합니다.

---

GitHub 공식 도움말: https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site

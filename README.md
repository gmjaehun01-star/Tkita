Tkita 홍보 페이지 — 올리는 방법과 고치는 방법
1. 무료로 인터넷에 올리기 (GitHub Pages)
GitHub에서 새 저장소(repository)를 만듭니다. 이름은 `tkita` 정도로 하고 Public으로 설정합니다.
이 폴더의 `index.html` 파일과 `images` 폴더를 통째로 업로드합니다.
저장소 상단 Settings → Pages 로 들어갑니다.
Source를 Deploy from a branch, Branch를 main / (root) 로 지정하고 Save를 누릅니다.
2~3분 뒤 `https://내계정명.github.io/tkita/` 주소로 접속됩니다. https는 자동으로 붙습니다.
수정할 때는 GitHub에서 `index.html`을 열고 연필 아이콘을 눌러 고친 뒤 Commit하면
1~2분 뒤 사이트에 바로 반영됩니다.
2. 내용 고치기
`index.html` 파일을 메모장이나 VS Code로 열면, 위쪽에 다음과 같은 부분이 있습니다.
    <script id="content">
    const SITE = {
      ...
    };
    </script>

이 안쪽만 고치시면 됩니다. 아래쪽의 style, script 부분은 건드리지 않으셔도 됩니다.
자주 고치실 항목
고치고 싶은 것	찾을 곳
무료 체험 신청 주소	`trialUrl`, `applyUrl`
첫 화면 문구	`heroTitle`, `heroText`
첫 화면에서 흘러가는 자막 예시	`heroDemo`
성능 수치	`stats`
도입 기관 이름 (자동 슬라이드)	`refs`
제품 설명·기능	`products` 안의 각 항목
소개 영상	`products` 안의 `youtube`
유튜브 영상 연결하는 법
유튜브에 영상을 올린 뒤 주소를 봅니다.
    https://www.youtube.com/watch?v=AbCdEfGhIjK
                                    ^^^^^^^^^^^  이 부분(11자리)만 복사

`youtube:""` 를 `youtube:"AbCdEfGhIjK"` 로 바꾸면 페이지에서 바로 재생됩니다.
비워두면 "소개 영상 준비 중입니다" 안내가 표시됩니다.
도입 기관 이름 넣는 법
`refs` 목록에 기관명을 넣으면 자동으로 옆으로 흘러갑니다.
공개 동의를 받은 기관만 실제 이름으로 바꾸시고, 나머지는 `○○대학교` 형태로 두시면 됩니다.
    refs: [ "○○대학교 국제처", "○○교육청", ... ]

개수는 자유롭게 늘리거나 줄일 수 있습니다. 8개 이상이면 자연스럽게 흘러갑니다.
3. 페이지 구성
`#/` — 전체 소개 (첫 화면, 제품 4종, 성능, 도입 현황, 무료 체험)
`#/caption` — TkitaCaption
`#/talk` — TkitaTalk
`#/mobile` — TkitaMobile
`#/meet` — TkitaMeet
제품별 주소를 그대로 복사해서 메일이나 제안서 QR에 쓰실 수 있습니다.
4. 이미지 교체
`images` 폴더의 파일을 같은 이름으로 덮어쓰면 교체됩니다.
새 이미지를 추가하실 때는 `images` 폴더에 넣고, `products` 안의 `shots` 목록에
`["images/파일명.png", "설명글"]` 형태로 한 줄 추가하시면 됩니다.
5. 도입 기관 로고 넣기
로고 이미지를 `images/refs` 폴더에 넣습니다. (PNG 권장, 배경이 투명하면 가장 깔끔합니다)
`index.html` 의 `refs` 목록에 아래처럼 한 줄 추가합니다.
refs: [
         { logo:"images/refs/univ-a.png", name:"○○대학교" },
         { logo:"images/refs/office-b.png", name:"○○교육청" },
         "○○고등학교"
       ]

글자와 로고를 섞어 넣어도 됩니다. 로고가 있는 기관은 로고로, 없는 기관은 글자로 표시됩니다.
로고 이미지 만들 때
가로로 긴 형태가 가장 잘 맞습니다. 세로 100~200px 정도면 충분합니다.
배경은 투명(PNG) 이 가장 좋고, 흰 배경도 괜찮습니다.
너무 작거나 글씨가 많은 로고는 흘러갈 때 읽히지 않으니, 심볼+기관명이 함께 있는 형태를 쓰세요.
8개 이상 넣으면 빈틈 없이 자연스럽게 이어집니다.
주의
기관 로고는 해당 기관의 사용 동의를 받은 경우에만 올리셔야 합니다.
동의 전에는 `"○○대학교"` 처럼 글자로 두시면 됩니다.

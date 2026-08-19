# VINCERE — The Dynamic of Conquest

FEARLESS 한국지부 / 개인 소장·공유용 페어 아카이브.

## 1. 폴더 구조

```
VINCERE/
├─ index.html                 ← 브라우저로 이 파일을 열면 됩니다
├─ img/
│   ├─ main.png               ← 첫 화면 메인 이미지 (가로형 16:9 권장)
│   ├─ logo.png               ← VINCERE Conquest 로고 (01 DOSSIER 에서 사용)
│   ├─ dive.png               ← A / 서인혁 (빨간머리)
│   ├─ null.png               ← B / 박유준 (검은머리)
│   ├─ g01.png ~ g08.png      ← 갤러리 (세로형 3:4)
│   └─ rel01.png ~ rel04.png  ← 소중한 인연 배너 (가로 2000×405)
└─ fonts/
    └─ NEMESYS-Regular.ttf    ← 영문·숫자 디스플레이 폰트
```

파일을 넣기 전에도 사이트는 정상 동작합니다. 없는 이미지는 빨간 빗금
플레이스홀더로, 없는 폰트는 비슷한 각진 폰트로 자동 대체됩니다.

> 로고 PNG가 검정 기반이라 어두운 배경에서 묻히므로 **흰 플레이트** 위에
> 올려두었습니다. 흰 판이 싫으면 index.html 에서 `.plate` 의
> `background:#f2f2f0` 를 지우고 `filter:invert(1)` 등으로 바꾸면 됩니다.

### 사용 폰트

| 용도 | 폰트 |
|---|---|
| 영문·숫자 디스플레이 | NEMESYS (없으면 Chakra Petch / Orbitron) — 챕터 제목, 라벨 |
| 클래식 세리프 대문자 | Bodoni Moda — 첫 화면 VINCERE, DOSSIER 항목 값 |
| 화려한 영어 필기체 | Great Vibes — 부제, 캐치프레이즈, CH04 Vincere, 로딩 화면 |
| 클래식 명조 | Noto Serif KR + Bodoni Moda — 목차 #01·#02·#03 문구 |
| 한글 본문 | Noto Sans KR |
| 라벨·수치 | JetBrains Mono |

필기체를 더 가늘고 고전적으로 바꾸려면 `--f-script` 값에서
`'Pinyon Script'` 를 앞으로 옮기면 됩니다.

## 2. 챕터 구성

```
00  OVERTURE     로고 · DIVE × NULL · 캐치프레이즈 · [성향표] [배려 리스트] 버튼
01  DOSSIER      페어 개요 · 코드 · 소속
02  SUBJECT.A    DIVE / 서인혁 — 가이드 A급, 팀 어텐션, 능력 「제압」
03  SUBJECT.B    NULL / 박유준 — 센티넬 S급, 암살기동부대, 능력 「암전」
04  DYNAMIC      정복의 역학 · 상호 구원
05  CHRONICLE    서사 타임라인 (PH 00 ~ PH 09)
06  GALLERY      이미지
07  RULES        규칙 · 연락처
```

## 3. 로딩 화면

첫 진입 시 지지직거리는 글리치 로딩 화면이 뜹니다. RGB 분리·주사선·화면
찢김·노이즈가 겹쳐 있고, 폰트 로딩이 끝나면 자동으로 사라집니다
(최소 약 1.9초, 최대 6초 안전장치). 애니메이션을 끄는 접근성 설정
(`prefers-reduced-motion`)에서는 글리치 없이 조용히 지나갑니다.

## 4. 성향표 / 배려 리스트 / 프롬프트

첫 화면의 **TENDENCY** · **CONSIDERATION** · **PROMPT** 버튼,
또는 화면 어디서나 우상단 **성향표 / 배려** 버튼으로 열립니다.
오버레이 안에서 탭으로 세 목록을 전환합니다. ESC 또는 바깥을 누르면 닫힙니다.

- **성향표** — `1t1d :: FEARLESS DIVE` 선언문 + O/△/X 매트릭스 + 보조 태그
- **배려 리스트** — 더 이상 모시지 않는 드림 19작품 57명, 작품명·캐릭터 검색 가능
- **프롬프트** — DIVE / NULL / NULL 여성화 3종. `COPY` 버튼으로 전체 복사,
  칸을 눌러 직접 수정도 가능 (수정해도 원본 파일은 바뀌지 않습니다)

첫 화면 하단에 바로가기 버튼이 두 개 있습니다.

- **링크 · 연락망 / LINKS & CONTACT** → 08 RULES · CONTACT
- **소중한 인연들 / RELATIONSHIP** → 07 RELATIONS

## 5. 갤러리 — 그림 출처

모든 갤러리 이미지에 **@ZZ____S2__** 출처가 붙어 있습니다.
카드 하단과 크게 본 화면의 `ART BY` 에 표시되며, **사이트에서는 수정할 수
없습니다.** (보는 사람이 임의로 바꾸지 못하도록 읽기 전용입니다)

출처를 바꾸려면 `DATA.gallery` 의 `artist` 값을 고치세요.

```js
{ src:"img/g01.png", cap:"SCENE 01", artist:"@ZZ____S2__" }
```

이미지를 누르면 크게 열리고, `‹` `›` 버튼 또는 좌우 방향키로 넘길 수 있습니다.

## 5-1. 사원증 (ID CARD)

DIVE / NULL 프로필 사진 아래에 FEARLESS 사원증이 붙어 있습니다.
**카드를 한 번 누르면 3D로 뒤집혀 뒷면**이 보입니다. (키보드는 Enter / Space)

| 앞면 | 뒷면 |
|---|---|
| 증명사진 · 코드네임 · 본명 | 마그네틱 스트라이프 |
| CODE / CLASS / RANK / UNIT | 능력명 + 설명 |
| 바코드 | 캐치프레이즈 (필기체) |
| | 자산 안내 · 서명란 |

내용은 `index.html` 의 `CH 02` / `CH 03` 안에 있는
`<!-- 사원증 : 탭하면 뒤집힘 -->` 주석을 찾아 고치면 됩니다.

## 6. 소중한 인연 (07 RELATIONS)

가로로 긴 배너를 세로로 쌓고, 누르면 새 탭으로 링크가 열립니다.
`DATA.relations` 에서 관리합니다.

```js
relations: [
  { name:"이름 · 페어명", kr:"한 줄 소개",
    tag:"CONNECTION 01", src:"img/rel01.png", url:"https://..." }
]
```

- `url` 을 비워두면 클릭되지 않는 자리표시로 표시됩니다
- 배너는 **2000 × 405 (약 5:1)** 가로형을 권장합니다
- PC 에서는 배너 왼쪽에 이름·소개가 얹히고 오른쪽에 `VISIT ↗` 버튼이,
  모바일에서는 배너 아래로 내려가 세로로 쌓입니다
- 항목을 늘리려면 배열에 추가하고 `img/rel05.png` 처럼 파일을 넣으면 됩니다

## 7. 내용 수정

`index.html` 아래쪽 `<script>` 안의 **`const DATA = { ... }`** 한 곳만
고치면 됩니다.

| 키 | 내용 |
|---|---|
| `chronicle` | 서사 타임라인. `who`는 `"A"` / `"B"` / `"AB"` |
| `stmt` | 성향표 상단 선언문 (code / line / sub) |
| `careHd` | 배려 리스트 상단 문구 |
| `dropped` | 더 이상 모시지 않는 드림 목록 (`w` 작품 / `en` 영문 / `c` 캐릭터 배열) |
| `careNote` | 배려 리스트 하단 안내문 |
| `prompts` | 프롬프트 3종 (`who` / `kr` / `tag` / `text`) |
| `gallery` | 갤러리 이미지 경로·캡션·`artist`(그림 출처, 읽기 전용 표시) |
| `matrix` | 성향표. `mark`는 `"O"`(가능) / `"T"`(협의) / `"X"`(불가) |
| `tags` | 보조 태그. `type`은 `"pos"` / `"neg"` / `""` |
| `relations` | 소중한 인연 배너 (`name` / `kr` / `tag` / `src` / `url`) |
| `rules` | 규칙 카드 (OOC / 수정 / 공유 / 고유성) |
| `notice` | 강조 공지 문구 (HTML 가능, `<em>` 은 빨간 강조) |
| `links` | 링크 · 연락망. `url` 을 비우면 '링크 입력' 자리표시 |
| `contact` | 문의 방법 · 최종 수정일 |

캐릭터 성격·능력·관계성 본문은 HTML 안에 직접 들어 있습니다.
`CH 02`, `CH 03`, `CH 04` 주석을 찾아 문단을 고치면 됩니다.

## 8. 모바일

- 하단에 가로 스크롤 챕터 바가 생기고, 현재 챕터가 자동으로 따라옵니다
- 서사 타임라인은 좌측 축 + 단일 열로 재배치됩니다
- 상단/하단 노치 영역(safe-area)을 피해서 배치됩니다
- 성향표는 표 대신 항목별 카드 형태로 접힙니다


## 9. 링크 넣는 법

`DATA.links` 의 `url` 에 주소를 넣으면 자동으로 클릭 가능한 링크가 됩니다.

```js
links: [
  { label:"TISTORY", kr:"티스토리 — OOC 첨부", url:"https://dive.tistory.com/", hot:true },
  { label:"LUV3R",   kr:"러버미",              url:"https://dive.luv3r.me/",   hot:true },
  { label:"ETC",     kr:"기타 링크",           url:"" }        // 비우면 자리표시
]
```

현재 티스토리와 러버미 링크는 이미 연결되어 있습니다.

`hot:true` 인 항목은 빨간 테두리로 강조됩니다.

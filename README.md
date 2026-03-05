# toss-front-plugin-template

**Toss FRONT 플러그인 개발을 위한 공식 템플릿 저장소입니다.** ([🔗 Toss SDK 연동 - 공식 홈페이지](https://tossplace.com/sector/plugin))

`toss-front-plugin-template` 저장소는 Toss FRONT 환경에서 실행되는 플러그인을 빠르고 효율적으로 구현할 수 있도록 돕는 프로젝트 템플릿을 제공합니다.

## 1. 개요
업종별 맞춤 UI와 결제 기능을 통합하여 개발하고 싶은 경우에 적합합니다.

## 2. 템플릿 목록

`toss-front-plugin-template` 저장소는 플러그인 실행 방식과 개발 언어에 따라 각 템플릿 폴더로 나뉘어 있습니다:

| 템플릿 폴더 이름             | 사용 언어      | 주요 용도                                  |
|:----------------------|:-----------|:---------------------------------------|
| **`front-plugin-js`** | Javascript | 프론트 플러그인의 기본 기능이 예시로 구현되어있는 자바스크립트 템플릿 |

예제 코드는 다음과 같은 파일들로 구성되어 있습니다:

### 2-1. front-plugin-js

```
.
├─ global.css    # 전역 스타일
├─ index.html    # 진입점 (home으로 이동)
├─ home.html     # 기본 대기 화면(renderIdlePage)
├─ order.html    # 메디케시 사용 + 결제 플로우
└─ sdk.js        # SDK 유틸리티
```


## 3. 시작하기

문서를 참고해주세요 ([🔗 Toss FRONT 플러그인 개발 가이드](https://docs.tossplace.com/guide/front-integration/getting-started.html)).

## 4. 현재 구현 플로우 (TO-BE 기준)

- 기본 화면: `renderIdlePage`에서 `메디케시 사용` 버튼 제공
- 메디케시 사용 화면: `renderUsePointPage`
- 결제 금액 확인 화면: `renderOrderPage`
- 결제 성공 화면: `renderResultPage`
- 결제 실패 화면: `renderOrderResultPage`

## 5. 임시 Mock 시나리오

웹소켓/백엔드 연동 전까지 `order.html?scenario=...` 로 QA 가능합니다.

- `eligible`: 메디케시 사용 가능 후 결제
- `insufficient`: 최소 사용 금액 미달(메디케시 화면 스킵)
- `paymentFailure`: 결제 실패 화면 확인
- `paymentSuccessMock`: 결제 성공 화면 확인(결제 API 호출 없이)

## 6. TODO

- 백엔드 웹소켓 이벤트로 기본 화면에서 자동 진입
- 백엔드 계약 데이터(진료금액/보유캐시/최소사용금액/적립금) 연결
- 메디케시 사용 확정 API 연동
- 결제 승인 정보 저장 및 정산/취소 연동


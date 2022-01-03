---
description: 이석 확인 기능에 대한 설명입니다.
---

# 이석 확인

### 개요

이석 확인 기능은 `학습실`에서 자습하는 학생들의 이석 정보를 편리하게 모아 볼 수 있는 기능입니다. 이석 확인 기능을 위한 부가 정보들은 아래와 같습니다. 이 부가 정보들은 기본값이 정해져 있으며, 처음 `이석 확인` 메뉴를 클릭했을 시 자동으로 설정됩니다.

| 부가 정보 이름 | 부가 정보 설명      | 기본값                       |
| -------- | ------------- | ------------------------- |
| 학습실      | 조회할 학습실       | 우선순위가 가장 높은 학습실           |
| 기준 시각    | 이석을 조회할 기준 시각 | 현재 시각                     |
| 교시 그룹    | 이석을 조회할 교시 그룹 | 현재 시각에 해당하는 교시가 속해있는 교시그룹 |

각 부가 정보에 대한 상세한 설명은 기능 심화 > 데이터 를 참조하시기 바랍니다.

위 부가 정보들은 이석 확인 페이지 상단의 정보 표시줄에서 확인 및 변경할 수 있습니다.&#x20;

### 이석 확인 페이지

이석 확인 기능의 정보 표시줄은 아래와 같이 구성 되어있습니다.

![이석 확인 기능 정보 표시줄](<../.gitbook/assets/image (15).png>)

| 번호 | 설명                                                                                                                                                                                                              |
| -- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1  | 현재 선택된 학습실의 전체 이름을 나타냅니다.                                                                                                                                                                                       |
| 2  | 현재 정보를 표시하고 있는 기준 시각을 나타냅니다. 이 기준 시각은 학생의 학적, 기본 교시 그룹 및 이석 정보를 조회하는데에 사용됩니다.                                                                                                                                   |
| 3  | 선택 가능한 학습실 목록을 단축 이름을 사용하여 나타냅니다. 현재 선택된 학습실은 회색(선택됨)으로 표시됩니다. 우선순위가 높은 학습실은 표시줄에 나열되며, 그렇지 않은 학습실들은 부가 메뉴(우측 '선택' 메뉴 참고) 를 이용하여 선택 가능합니다.                                                                      |
| 4  | 기준 시각을 변경할 수 있는 시각 선택기입니다. '기준 시각 검색'을 클릭하면 기준 시각을 변경할 수 있는 팝업이 표시되며 돋보기 모양 아이콘을 클릭하여 기준 시각을 변경할 수 있습니다. 팝업을 통해 시각을 선택한 이후에도 키보드를 사용하여 상세 시각을 변경할 수 있습니다.                                                       |
| 5  | 기준 시각을 선택할 수 있는 팝업입니다. 날짜를 클릭하면 시간, 분을 차례로 선택할 수 있고 '지금' 버튼을 클릭하면 현재 시각을 선택할 수 있습니다. 5분 단위로만 시간 조정이 가능하며 시간의 상세 변경에 관한 사항은 4번 항목에 대한 설명을 참조하시기 바랍니다. 연도 및 월을 변경 하려면 현재 연도와 월이 표시된 부분('2021년 1월' 부분)을 클릭하면 됩니다.  |
| 6  | 선택 가능한 교시 그룹 목록을 단축 이름을 사용하여 나타냅니다. 클릭하여 교시 그룹을 변경할 수 있습니다.                                                                                                                                                     |

이석 확인 기능을 사용하면, 해당 `학습실` 학생들의 `기준 시각` 및 `교시 그룹`에 해당하는 최종 승인 상태의 이석들을 볼 수 있습니다. 가령, `주간 교시 그룹`에 해당하는 3\~7 교시의 최종 승인된 이석을 가진 학생의 자리에는 아래와 같이 표시됩니다.

![이석 확인 화면 예시 이미지](<../.gitbook/assets/image (3).png>)

같은 교시에 두 이석이 존재하는 경우, 종료되지 않았으며 `기준 시각`에 시작 시각이 가까운 이석이 먼저 표시됩니다. 야간 교시 그룹의 1교시가 19시 10분부터 20시 10분까지인 경우를 예로 들어보겠습니다. 19시 10분부터 19시 30분까지의 종류가 '이석'인(화면에 '이'라고 표시되는) 이석 1이, 19시 30분부터 20시 10분까지의 종류가 '컴퓨터'인(화면에 '컴'이라고 표시되는) 이석 2가 최종 승인 상태라면, 아래와 같은 원리에 의해 19시 30분 전에는 (이)로, 19시 30분과 19시 30분 후에는 (컴)으로 표시됩니다.

![같은 교시에 2개의 이석이 존재하는 경우 화면 표시 원리 설명도](<../.gitbook/assets/image (8).png>)

이석 확인 화면에서 표시 가능한 교시의 수는 정해져있습니다. 이는 관리자에 의해 변경될 수 있으며, 자세한 내용은 관리자 기능 > 전역설정 을 참조하시기 바랍니다.

교시 그룹에 속해있는 교시들의 수가 표시 가능한 교시의 수를 초과했을 때 교시 선택 슬라이더가 나타나게 됩니다. 이 슬라이더를 조종하면 화면에 표시되는 교시들을 변경할 수 있습니다.

![이석 확인 교시 슬라이더](<../.gitbook/assets/image (4).png>)

또한 해당 `학습실`의 자리배치도에 문제가 있어 학생의 정보를 표시할 수 없는 경우 아래와 같이 자리에 해당하는 칸의 배경 색상이 붉은색으로 변경됩니다. 이 경우 관리자에게 문의하여 정보 갱신을 요청하십시오.

![자리 배치도 오류](<../.gitbook/assets/image (5).png>)

좌석을 짧게 클릭하면 해당 좌석에 표시를 남길 수 있습니다. 자습 감독 시에 자리에 없는 학생을 표시하거나 이상이 있는 좌석을 표시하는 용도로 사용될 수 있습니다. 첫 클릭 시 좌석의 배경색이 바뀌며, 다시 클릭하면 원래대로 돌아옵니다.

![좌석 선택 기능 예시](<../.gitbook/assets/image (9).png>)

### 학생 상세 정보

학생의 좌석을 두 번 연속으로 클릭하면 해당 학생의 상세 정보와 최근 7일의 이석을 조회할 수 있습니다. 이석 승인 상태 변경 권한을 가진 사용자로 로그인이 되어있는 경우, "승인 여부" 란에 표시된 승인 상태 정보를 클릭하면 해당 이석의 승인 상태를 변경할 수 있습니다.

![학생 상세 정보 팝업 예시](<../.gitbook/assets/image (10).png>)
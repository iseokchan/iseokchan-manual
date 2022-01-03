---
description: 사이트에 전반적으로 적용되는 전역설정에 대해 안내합니다
---

# 전역설정

## 개요

이석찬의 관리자는 사이트에 대한 전반적인 사항을 전역설정을 통해 지정할 수 있습니다. 이 개념은 학생 및 교사를 추가하거나 학생의 좌석을 배정하는 것과는 다릅니다. 전역 설정을 다루기전에, 알고 가야할 것들이 있습니다. 아래 내용은 전역설정에 대해 이해하는 데 있어 도움을 줍니다.

### 구성

아래 문서는 다음과 같이 구성되어있습니다. 아래 예시를 참고하십시오.

> #### 변수 이름 | 변수 타입
>
> 변수 설명

조금 더 실질적인 예시는 아래와 같습니다.

> #### SCHOOL\_NAME | STRING
>
> 학교의 이름을 지정합니다.

위와 같은 경우 이석찬의 관리자 패널에서 SCHOOL\_NAME 값을 "한국고등학교" 라고 지정할 경우 사이트 내에서 사용되는 모든 학교 이름에 관한 값이 "한국고등학교"로 변경됩니다.

### 변수 타입

위의 구성 문서에서 변수 타입이 있습니다. 변수 타입은 해당 변수가 어떠한 값을 가져야 하는지 알려줍니다. 이에 관한 내용은 아래에 열거되어있습니다.&#x20;

`STRING : 문자열`\
`INT : 정수`\
`BOOL : 논리형(0 또는 1)`\
`ARRAY<타입> : 타입 값의 배열`\
`HTML : HTML 문서`\
`REGEX : 정규식`

{% hint style="warning" %}
이석찬 관리자 패널에서는 입력되는 값에 대해 별도의 제한을 두지 않습니다. 즉, 변수 타입이 달라도 값을 삽입할 수는 있으나 이는 사이트에 심각한 영향을 줄 수 있습니다. 심지어, 사이트가 구동되지 않을 수 있습니다. 더욱이, 일부 변수는 최솟값 또는 최댓값이 제한되거나 특정한 조건이 있는 경우가 있습니다. 따라서 변수를 삽입하는데에 있어 반드시 문서를 참조하시기 바랍니다.
{% endhint %}

## 전역설정

### 네이밍

#### SITE\_FULL\_NAME | STRING

사이트의 전체 이름입니다. 예를 들어 `이석찬::강원과고 통합 이석관리 플랫폼`을 사이트 전체 이름으로 활용할 수 있습니다.&#x20;

#### SITE\_SHORT\_NAME | STRING

사이트의 짧은 이름입니다. 대개 웹 브라우저 상단에 사이트 이름이 표시됩니다. 예를 들어 `이석찬`을 사이트 짧은 이름으로 사용할 수 있습니다.

#### MENU\_APPLY\_NAME | STRING

이석 신청 메뉴의 호칭입니다. 예를 들어 `이석 신청`을 이석 신청 메뉴의 호칭으로 사용할 수 있고, 이는 메인화면 메뉴 이름과 내비게이션 바, 해당 페이지의 제목으로 사용됩니다.

#### MENU\_CHECK\_NAME | STRING

이석 확인 메뉴의 호칭입니다. 예를 들어 `이석 확인`을 이석 확인 메뉴의 호칭으로 사용할 수 있고, 이는 메인화면 메뉴 이름과 내비게이션 바, 해당 페이지의 제목으로 사용됩니다.

#### MENU\_MANAGE\_NAME | STRING

이석 신청 메뉴의 호칭입니다. 예를 들어 `이석 관리`를 이석 관리 메뉴의 호칭으로 사용할 수 있고, 이는 메인화면 메뉴 이름과 내비게이션 바, 해당 페이지의 제목으로 사용됩니다.

#### ISEOK\_NAME | STRING

이석의 호칭입니다. `이석`,`자율학습` 등으로 사용할 수 있습니다.&#x20;

### 제한

#### MAXIMUM\_GRADE | INT

학생이 속할 수 있는 학년의 최댓값입니다.

#### MINIMUM\_GRADE | INT

학생이 속할 수 있는 학년의 최솟값입니다.

#### MAXIMUM\_CLASS | INT

학생이 속할 수 있는 반의 최댓값입니다.

#### MINIMUM\_CLASS | INT

학생이 속할 수 있는 반의 최솟값입니다.

#### MAXIMUM\_NUMBER | INT

학생이 속할 수 있는 번호의 최댓값입니다.

#### MINIMUM\_NUMBER | INT

학생이 속할 수 있는 번호의 최솟값입니다.

#### ISEOK\_APPROVE\_STEP | INT

이석 신청을 위해 거쳐야 할 단게입니다. 최솟값은 1, 최댓값은 5입니다.

### 리소스

#### SRC\_ICON\_MAIN | STRING

메인 아이콘의 경로입니다.

#### SRC\_ICON\_MENU\_APPLY | STRING

이석 신청 메뉴의 아이콘 경로입니다.

#### SRC\_ICON\_MENU\_CHECK | STRING

이석 확인 메뉴의 아이콘 경로입니다.

#### SRC\_ICON\_MENU\_MANAGE | STRING

이석 관리 메뉴의 아이콘 경로입니다.

#### SRC\_BACKGROUND\_IMAGE | ARRAY\<STRING>

메인화면 배경 경로입니다. 여러 개인 경우 랜덤으로 한 이미지가 출력됩니다.

### 코드

#### HTML\_TERMS\_OF\_SERVICE | HTML

사이트 이용약관 삽입될 HTML 코드입니다.

#### HTML\_PRIVACY\_POLICY | HTML

개인정보 처리 방침에 삽입될 HTML 코드입니다.

### 비트 플래그

#### FLAG\_TEACHER\_NICKNAME | INT

교사 이름을 출력하기 위한 방식을 지정합니다. 동명이인을 방지하기 위함입니다. 상세한 내용은 아래를 참고하십시오. 교사 닉네임은  표현식 `EXPR_TEACHER_NICKNAME`을 이용하여 출력된 값을 의미합니다.

```c
// 001 (1) : 교사 닉네임을 출력하지 않음 (FLAG_TEACHER_NICKNAME_NO)
// 010 (2) : 동명이인이 있는 경우에만 교사 닉네임을 출력함 (FLAG_TEACHER_NICKNAME_NAMESAKE)
// 100 (4) : 항상 교사 닉네임을 출력함 (FLAG_TEACHER_NICKNAME_ALWAYS)
```

### 표현식

#### EXPR\_TEACHER\_NICKNAME | STRING

교사 이름을 출력하는 표현식입니다. 동명이인 방지를 위함입니다. 사용할 수 있는 변수는 아래와 같습니다.

`{name} {nickname} {room_alias} {room_short_alias}`&#x20;

`{교사 이름} {교사 별명} {교사 사무실 이름} {교사 짧은 이름}`&#x20;

#### EXPR\_COMPUTER\_INFO\_{GRADE\_NUM} | STRING

**{GRADE\_NUM}** 학년의 컴퓨터 정보를 계산하는 수학식입니다. 사용할 수 있는 변수는 아래와 같습니다.

`{grade} {year} {month} {day} {hour} {minute} {second} {dayOfWeek} {dayOfYear} {weekOfMonth} {weekOfYear} {timestamp} {quarter} {MAXIMUM_GRADE} {MINIMUM_GRADE} {MAXIMUM_CLASS} {MINIMUM_CLASS} {MAXIMUM_NUMBER} {MINIMUM_NUMBER}`

`{학년} {연도} {달} {날짜(달 기준)} {시간} {분} {초} {요일(주 기준)} {날짜(연도 기준)} {주 수(달 기준)} {주 수(연도 기준)} {UNIX 타임스탬프} {분기} {MAXIMUM_GRADE 전역설정} {MINIMUM_GRADE 전역설정} {MAXIMUM_CLASS 전역설정} {MINIMUM_CLASS 전역설정} {MAXIMUM_NUMBER 전역설정} {MINIMUM_NUMBER 전역설정}`

### 보안

#### EXPR\_TEACHER\_NICKNAME | STRING

교사 이름을 출력하는 표현식입니다. 동명이인 방지를 위함입니다. 사용할 수 있는 변수는 아래와 같습니다.

`{name} {nickname} {room_alias} {room_short_alias}`

**API\_CORS\_DOMAIN | ARRAY\<STRING>**

이석찬은 독립적인 API 서버를 가지고 있습니다. 이 경우에 웹 브라우저에서 API 서버에 요청을 하면(예-이석신청) CORS(Cross-Origin Resource Sharing) 오류가 발생할 수 있습니다. 이 경우에 요청하는 클라이언트의 도메인을 추가하면 서버에서 도메인을 인식하여 CORS 관련 헤더를 보냅니다. 이 설정은 CSRF 설정과 무관합니다.

**ALLOW\_FROM\_ALL | BOOL**

이석찬에 대한 접속을 모든 호스트로부터 허용할 지 여부를 결정합니다. 이 값이 참이면 모든 호스트로부터 이석찬 접속이 가능해집니다.

{% hint style="warning" %}
이 값이 거짓일 경우 이석찬 메인 페이지 뿐만 아니라 API 서버에 대한 접근도 불가해집니다. 이 경우에는 API 서버에 접근하려는 호스트의 IP주소를 아래 ALLOW\_IP\_ADDRESS에 추가해야합니다.
{% endhint %}

**ALLOW\_IP\_ADDRESS | ARRAY\<REGEX>**

이석찬에 대한 접근을 허용하려는 호스트의 IP 주소를 정규식으로 나타낸 리스트입니다. 만약 IP 주소가 `100.22.33.1` 인 호스트의 접근을 허용하려면 `^100.22.33.1$` 을, IP 주소의 범위가 `100.22.33.1~100.22.33.99` 인 호스트의 접근을 허용하려면 `^100.22.33.([1-9]|[1-9]\d)$` 을 입력하면됩니다. IP 주소 범위를 정규식으로 바꾸는 방법은 아래 사이트를 참고하십시오.

{% embed url="https://www.analyticsmarket.com/freetools/ipregex/" %}

**DENY\_IP\_ADDRESS | ARRAY\<REGEX>**

이석찬에 대한 접근을 거부하려는 호스트의 IP 주소를 정규식으로 나타낸 리스트입니다. 만약 IP 주소가 `100.22.33.1` 인 호스트의 접근을 거부하려면 `^100.22.33.1$` 을, IP 주소의 범위가 `100.22.33.1~100.22.33.99` 인 호스트의 접근을 거부하려면 `^100.22.33.([1-9]|[1-9]\d)$` 을 입력하면됩니다. IP 주소 범위를 정규식으로 바꾸는 방법은 아래 사이트를 참고하십시오.

{% embed url="https://www.analyticsmarket.com/freetools/ipregex/" %}

{% hint style="warning" %}
접근 거부는 다른 그 어떤 조건에에 우선합니다. 따라서, ALLOW\_IP\_ADDRESS에 있는 IP이더라도 DENY\_IP\_ADDRESS에 있는 경우 접근이 제한됩니다. 더불어, 로그인이 된 상태여도 DENY\_IP\_ADDRESS에 있는 경우 접근이 제한됩니다.
{% endhint %}

### 권한

**PERMISSION\_APPLY | INTEGER**

이석 접근&#x20;


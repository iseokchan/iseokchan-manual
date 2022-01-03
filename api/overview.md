---
description: 본 페이지는 이석찬 API Document에 대한 개요를 담은 페이지입니다.
---

# 개요

### 구성

본 API 문서는 아래와 같은 형식으로 구성되어있습니다.

{% swagger baseUrl="API 루트 주소" path="API 경로" method="get" summary="API 이름" %}
{% swagger-description %}
API 상세 설명
{% endswagger-description %}

{% swagger-parameter in="path" name="경로 파라미터" type="string" %}
경로 파라미터 설명
{% endswagger-parameter %}

{% swagger-parameter in="header" name="헤더" type="string" %}
헤더 설명
{% endswagger-parameter %}

{% swagger-parameter in="query" name="쿼리 파라미터" type="string" %}
쿼리 파라미터 설명
{% endswagger-parameter %}

{% swagger-parameter in="body" name="폼 데이터" type="string" %}
폼 데이터 설명
{% endswagger-parameter %}

{% swagger-response status="200" description="HTTP 응답 코드 상세 설명" %}
```
반환 예
```
{% endswagger-response %}
{% endswagger %}

위 API에서 파라미터가 의미하는 바는 아래와 같습니다.

*   경로 파라미터

    /v1/iseok/:id 에서 _:id_ 와 같이 표기되며 경로에 직접적으로 포함되는 파라미터입니다.
*   헤더

    HTTP  요청 시에 포함 되어야 할 헤더입니다.
*   쿼리 파라미터

    /v1/iseok?id=1 에서 _id=1_ 과 같이 표기되며 GET 파라미터를 의미합니다.
*   _폼 데이터_

    요청 주소 상으로는 보이지 않는 POST 요청 시에 전송하여야할 파라미터를 의미합니다.

대부분의 API에서는 GET과 POST 파리미터(쿼리 파라미터와 폼 데이터)에 특별한 구분을 두지 않습니다. 그러나 그렇지 않은 경우도 있으므로 API 명세에 명시된 요청 방법을 준수하는 것을 권장합니다.

이석찬의 모든 API는 JSON 형식의 응답을 반환하며 그 예시는 아래와 같습니다.

{% tabs %}
{% tab title="성공 응답" %}
```
// 성공적인 요청에 대한 응답은 아래와 같이 상태코드와 결과값을 반환합니다.
{
    "status": 200,
    "results": [
        {
            "name": "홍길동"
        }
    ]
}
```
{% endtab %}

{% tab title="일반 실패 응답" %}
```
// 일반적인 실패에 대한 응답은 아래와 같이 상태코드와 메시지를 반환합니다.
{
    "status": 400,
    "error": 400,
    "messages": {
        "error": "sample error"
    }
}
```
{% endtab %}

{% tab title="Form 실패 응답" %}
```
// Form을 통해 호출된 API의 경우 아래와 같이 해당되는 항목에 대한 오류 메시지로 구성됩니다.
{
    "status": 400,
    "error": 400,
    "messages": {
        "username" : "username should be letters : [a-z][A-Z]",
        "password": "password should be less than 32 letters"
    }
}
```
{% endtab %}
{% endtabs %}

### CORS 문제

도메인이 다른 웹페이지에서, 이석찬의 API를 사용하기 위해서는 CORS 도메인 등록을 하여야합니다. CORS 도메인은 이석찬 관리자 패널에서 설정할 수 있습니다.

### 용어 정의

본 API 문서에서 자주 사용되는 용어의 정의입니다.

* 특정 : '**특정한 한**'의 줄임말입니다. 특정 이석이란 **하나**의 이석을 의미하며 다수의 이석을 의미하지 않습니다. 따라서, 특정 데이터를 받아오는 것은 특정한 **한** 데이터를 받아오는 것으로 해석될 수 있습니다.

### 주의사항

1.  시간 \


    이석찬의 시간 표기는 64bit UNIX 타임스탬프를 이용하고 있습니다. UNIX 타임스탬프란 1970년 1월 1일 00:00:00 UTC 로부터 경과된 초를 나타낸 것입니다. 그러나 저장공간의 한계로 1970년 1월 1일 이전 시각은 조회할 수 없으며 그 이후 100억년이 초과되는 시간 쿼리에 대해서는 제약이 발생할 수 있습니다. 더불어 이석찬 서비스가 구현되는 시스템은 64bit 기반이어야 하며, 그렇지 않은 경우 2038년 문제라고 알려진 오버플로우 문제가 발생할 여지가 있습니다.\
    \
    이석찬의 시각 비교는 **모두** 등호가 없는 연산입니다. 따라서 이 API 문서를 비롯한 이석찬 내의 모든 시간 비교에 대하여 이후와 초과, 이전과 미만은 동치이며 시간과 시간의 포함 비교에서 시작과 끝 경계점이 동일한 경우에는 포함 관계가 성립한다고 보지 않습니다.

{% hint style="warning" %}
본 주의사항에 명시된 내용을 지키지 않아 발생한 시스템 상의 오류 및 피해에 대한 책임은 본 시스템을 사용하는 사람에게 있습니다.
{% endhint %}

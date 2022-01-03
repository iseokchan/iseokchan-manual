---
description: 이석과 관계된 API입니다.
---

# Iseok

{% swagger baseUrl="https://api.iseokchan.com" path="/v1/iseok/:id" method="get" summary="이석 받아오기" %}
{% swagger-description %}
​특정 이석 혹은 여러 이석들에 대한 정보를 받아옵니다. 반환되는 정보는 아래와 같습니다. 

\




\




_이석 아이디, 이석 종류 아이디, 지도교사 아이디, 이석 장소, 이석 이유, 이석 시작 시각, 이석 종료 시각,  이석 생성 시각, 이석 수정 시각_
{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="integer" %}
이석 아이디입니다. 이석 아이디가 지정되어 있으면 한 이석만을 받아오고, 지정되어 있지 않다면 조건에 해당 하는 모든 이석을 받아옵니다.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="limit" type="integer" %}
조회할 이석의 수 입니다. 1 미만일 수 없습니다.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="start_time" type="integer" %}
이 값이 지정되면 이석 시작 시각의 UNIX 타임 스탬프가 이 값을 초과하는 이석을 받아옵니다.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="end_time" type="integer" %}
이 값이 지정되면 이석 종료 시각의 UNIX 타임 스탬프가 이 값 미만인 이석을 받아옵니다.
{% endswagger-parameter %}

{% swagger-response status="200" description="정상적으로 이석을 받아오는 경우입니다." %}
```
{
    "status": 200,
    "results": [
        {
            "id": "58",
            "type_id": "1",
            "teacher_id": "5",
            "location": "양현재 2실",
            "reason": "a",
            "start_time": "2020-05-03 13:20:00",
            "end_time": "2020-05-03 18:00:00",
            "created_at": "2020-05-03 14:32:45",
            "updated_at": null,
            "deleted_at": null
        }
    ]
}
```
{% endswagger-response %}

{% swagger-response status="404" description="이석 아이디 값에 해당되는 이석이 존재하지 않거나 조건에 부합하지 않는 경우입니다." %}
```
{
    "status": 404,
    "error": 404,
    "messages": {
        "error": "Not Found"
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://api.iseokchan.com" path="/v1/iseok/status/:id" method="get" summary="이석 상태 받아오기" %}
{% swagger-description %}
특정 이석 혹은 여러 이석의 이석 상태를 받아옵니다. 반환되는 이석 상태는 등록 시각 기준 내림차순으로 정렬되어있습니다. 반환되는 정보는 아래와 같습니다.

\




_이석 상태 아이디, 상태에 해당되는 이석 아이디, 상태를 지정학 교사 아이디, 부가 메시지, 등록 시각_
{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="integer" %}
조회할 특정 이석의 아이디를 지정합니다.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="target_time" type="integer" %}
특정 시각의 UNIX_TIMESTAMP로 이 시각 이후에 등록된 이석 상태만 받아옵니다.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="limit" type="string" %}
조회할 이석 상태의 수 입니다. 1 미만일 수 없습니다.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="iseok[]" type="array" %}
조회할 이석 아이디 목록을 지정합니다.
{% endswagger-parameter %}

{% swagger-response status="200" description="정상적으로 이석 상태를 받아온 경우입니다." %}
```
{
    "status": 200,
    "results": [
        {
            "id": "9",
            "iseok_id": "58",
            "teacher_id": null,
            "status": "292",
            "message": "b",
            "created_at": "2020-05-03 16:09:46",
            "deleted_at": null
        },
        {
            "id": "8",
            "iseok_id": "58",
            "teacher_id": "5",
            "status": "36",
            "message": "a",
            "created_at": "2020-05-03 14:33:57",
            "deleted_at": null
        }
    ]
}
```
{% endswagger-response %}

{% swagger-response status="400" description="특정 아이디 값 혹은 조회할 아이디 목록 둘 중 하나라도 지정되어있지 않은 경우입니다." %}
```
{
    "status": 400,
    "error": 400,
    "messages": {
        "error": "Bad Request"
    }
}
```
{% endswagger-response %}

{% swagger-response status="404" description="기준에 부합하는 이석 상태가 없는 경우입니다." %}
```
{
    "status": 404,
    "error": 404,
    "messages": {
        "error": "Not Found"
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://api.iseokchan.com" path="/v1/iseok/student/:id" method="get" summary="이석과 학생 같이 받아오기" %}
{% swagger-description %}
특정 이석 혹은 여러 이석의 정보를 참가하는 학생의 정보와 같이 받아옵니다. 반환되는 정보는 아래와 같습니다.

\




_이석 아이디, 이석 종류 아이디, 지도교사 아이디, 이석 장소, 이석 이유, 이석 시작 시각, 이석 종료 시각, 이석 생성 시각, 이석 수정 시각, 참여 학생 아이디 목록_
{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="integer" %}
이석 아이디입니다. 이석 아이디가 지정되어 있으면 한 이석만을 받아오고, 지정되어 있지 않다면 조건에 해당 하는 모든 이석을 받아옵니다.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="limit" type="integer" %}
조회할 이석의 수 입니다. 1 미만일 수 없습니다.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="start_time" type="integer" %}
이 값이 지정되면 이석 시작 시각의 UNIX 타임 스탬프가 이 값을 초과하는 이석을 받아옵니다.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="end_time" type="integer" %}
이 값이 지정되면 이석 종료 시각의 UNIX 타임 스탬프가 이 값 미만인 이석을 받아옵니다.
{% endswagger-parameter %}

{% swagger-response status="200" description="정상적으로 이석과 학생 정보를 같이 받아온 경우입니다." %}
```
{
    "status": 200,
    "results": [
        {
            "id": 58,
            "type_id": "1",
            "teacher_id": "5",
            "location": "양현재 2실",
            "reason": "a",
            "start_time": "2020-05-03 13:20:00",
            "end_time": "2020-05-03 18:00:00",
            "created_at": "2020-05-03 14:32:45",
            "updated_at": null,
            "deleted_at": null,
            "students": [
                {
                    "student_id": "37"
                },
                {
                    "student_id": "38"
                }
            ]
        }
    ]
}
```
{% endswagger-response %}

{% swagger-response status="404" description="이석 아이디 값에 해당되는 이석이 존재하지 않거나 조건에 부합하지 않는 경우입니다." %}
```
{
    "status": 404,
    "error": 404,
    "messages": {
        "error": "Not Found"
    }
}

```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://api.iseokchan.com" path="/v1/iseok/type" method="get" summary="이석 종류 받아오기" %}
{% swagger-description %}
이석 종류를 받아옵니다. 반환되는 정보는 아래와 같습니다.

\




_이석 종류 아이디, 이석 종류 이름, 이석 종류 단축 이름, 이석 종류 대표 색, 이석 신청 시 최소 시간, 이석 신청 시 최대 시간, 이석 신청 시 최소 학생 수, 이석 신청 시 최대 학생 수, 이석 가능 여부, 이석 신청 시 바로 승인될 단계 수, 기타 설정 플래그 값, 등록 시각, 수정 시각_
{% endswagger-description %}

{% swagger-parameter in="query" name="iseokable" type="boolean" %}
이석 종류의 이석 가능 여부입니다. 값이 없을 경우 true로 취급됩니다.
{% endswagger-parameter %}

{% swagger-response status="200" description="정상적으로 이석 종류를 받아온 경우입니다." %}
```
{
    "status": 200,
    "results": [
        {
            "id": "1",
            "name": "이석",
            "short_name": "이",
            "color": "4294967295",
            "minimum_seconds": null,
            "maximum_seconds": null,
            "maximum_students": null,
            "minimum_students": null,
            "iseokable": "1",
            "instant_iseok_step": "2",
            "flag": "127",
            "created_at": "2020-04-05 21:12:51",
            "updated_at": "2020-04-15 22:51:02",
            "deleted_at": null
        },
        {
            "id": "2",
            "name": "외출",
            "short_name": "출",
            "color": null,
            "minimum_seconds": null,
            "maximum_seconds": null,
            "maximum_students": null,
            "minimum_students": null,
            "iseokable": "1",
            "instant_iseok_step": "0",
            "flag": "127",
            "created_at": "2020-04-05 21:12:51",
            "updated_at": "2020-04-13 23:12:56",
            "deleted_at": null
        },
        {
            "id": "3",
            "name": "외박",
            "short_name": "박",
            "color": null,
            "minimum_seconds": null,
            "maximum_seconds": null,
            "maximum_students": null,
            "minimum_students": null,
            "iseokable": "1",
            "instant_iseok_step": "0",
            "flag": "191",
            "created_at": "2020-04-05 21:12:51",
            "updated_at": "2020-04-13 23:12:59",
            "deleted_at": null
        },
        {
            "id": "4",
            "name": "컴퓨터",
            "short_name": "컴",
            "color": null,
            "minimum_seconds": null,
            "maximum_seconds": null,
            "maximum_students": "1",
            "minimum_students": "1",
            "iseokable": "1",
            "instant_iseok_step": "2",
            "flag": "93",
            "created_at": "2020-04-05 21:12:51",
            "updated_at": "2020-04-15 23:52:59",
            "deleted_at": null
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://api.iseokchan.com" path="/v1/iseok/apply" method="post" summary="이석 신청하기" %}
{% swagger-description %}
이석을 신청합니다. 필수 파라미터를 제외한 타 파라미터들은 이석 종류에 따라 필수 여부가 달라질 수 있습니다. 이석 종류를 확인 후 전송을 추천합니다.
{% endswagger-description %}

{% swagger-parameter in="query" name="type" type="integer" %}
이석 종류의 id 값
{% endswagger-parameter %}

{% swagger-parameter in="body" name="students[]" type="array" %}
이석을 신청하는 학생들의 id 값 배열
{% endswagger-parameter %}

{% swagger-parameter in="body" name="teacher" type="integer" %}
지도교사 아이디 값
{% endswagger-parameter %}

{% swagger-parameter in="body" name="location" type="string" %}
이석 장소
{% endswagger-parameter %}

{% swagger-parameter in="body" name="start_time" type="integer" %}
이석 시작 시각의 UNIX 타임스탬프
{% endswagger-parameter %}

{% swagger-parameter in="body" name="end_time" type="integer" %}
이석 종료 시각의 UNIX 타임스탬프
{% endswagger-parameter %}

{% swagger-parameter in="body" name="reason" type="string" %}
이석 사유
{% endswagger-parameter %}

{% swagger-response status="201" description="이석 신청 성공 시 응답입니다." %}
```
{
    "status": 201,
    "results": null
}
```
{% endswagger-response %}

{% swagger-response status="400" description="파라미터 오류, 이석 금지 등의 사유로 이석 신청 실패 시 응답입니다." %}
```
{
    "status": 400,
    "error": 400,
    "messages": {
        "students": "이석이(가) 금지된 학생입니다 : 홍길동"
    }
}
```
{% endswagger-response %}

{% swagger-response status="409" description="학생/교사 일정 혹은 이미 신청된 이석으로 인해 이석 신청 실패 시 응답입니다." %}
```
{
    "status": 409,
    "error": 409,
    "messages": {
        "students": "홍길동 학생은 해당 시간에 이석이(가) 있습니다."
    }
}
```
{% endswagger-response %}
{% endswagger %}


---
description: 교시와 관계된 API입니다.
---

# Period

{% swagger baseUrl="https://api.iseokchan.com" path="/v1/period/group/:id" method="get" summary="교시 그룹 받아오기" %}
{% swagger-description %}
교시 그룹과 그 그룹에 해당하는 교시 목록을 받아옵니다. 반환되는 값은 아래와 같습니다.

\




\




_교시 그룹 아이디, 교시 그룹 별칭, 교시 그룹 짧은 별칭, 교시 그룹 시작 시각, 교시 그룹 종료 시각, 교시 그룹 대표 색, 교시 그룹 대표 아이콘,  교시 목록_

\




\


교시 목록은 아래와 같이 구성됩니다.

\




\




_교시 아이디, 해당하는 날짜, 교시 별칭, 교시 짧은 별칭, 교시 시작 시각, 교시 종료 시각, 공휴일 교시 여부_

\



{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="string" %}
조회할 교시 그룹의 아이디입니다.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="target_time" type="number" %}
특정 시각의 UNIX_TIMESTAMP로, 해당 시각을 기준으로 그 날의 교시 그룹을 받아옵니다.
{% endswagger-parameter %}

{% swagger-response status="200" description="성공적으로 교시 그룹을 받아온 경우입니다." %}
```
{
    "status": 200,
    "results": [
        {
            "period_group_id": "3",
            "period_group_alias": "오전 교시 그룹",
            "period_group_short_alias": "오전",
            "period_group_start_time": "08:20:00",
            "period_group_end_time": "12:20:00",
            "period_group_color": "4294967295",
            "period_group_icon": null,
            "periods": [
                {
                    "id": "66",
                    "day_of_week": "1",
                    "alias": "1교시",
                    "short_alias": "1",
                    "start_time": "09:00:00",
                    "end_time": "10:00:00",
                    "is_holiday": "0"
                },
                {
                    "id": "67",
                    "day_of_week": "1",
                    "alias": "2교시",
                    "short_alias": "2",
                    "start_time": "10:10:00",
                    "end_time": "11:10:00",
                    "is_holiday": "0"
                },
                {
                    "id": "68",
                    "day_of_week": "1",
                    "alias": "3교시",
                    "short_alias": "3",
                    "start_time": "11:20:00",
                    "end_time": "12:20:00",
                    "is_holiday": "0"
                }
            ]
        },
        {
            "period_group_id": "4",
            "period_group_alias": "오후 교시 그룹",
            "period_group_short_alias": "오후",
            "period_group_start_time": "13:10:00",
            "period_group_end_time": "18:00:00",
            "period_group_color": "4294937600",
            "period_group_icon": "sun",
            "periods": [
                {
                    "id": "69",
                    "day_of_week": "1",
                    "alias": "오후 1교시",
                    "short_alias": "1",
                    "start_time": "13:20:00",
                    "end_time": "14:20:00",
                    "is_holiday": "0"
                },
                {
                    "id": "70",
                    "day_of_week": "1",
                    "alias": "오후 2교시",
                    "short_alias": "2",
                    "start_time": "14:30:00",
                    "end_time": "15:30:00",
                    "is_holiday": "0"
                },
                {
                    "id": "71",
                    "day_of_week": "1",
                    "alias": "오후 3교시",
                    "short_alias": "3",
                    "start_time": "15:40:00",
                    "end_time": "16:50:00",
                    "is_holiday": "0"
                },
                {
                    "id": "72",
                    "day_of_week": "1",
                    "alias": "오후 4교시",
                    "short_alias": "4",
                    "start_time": "17:00:00",
                    "end_time": "18:00:00",
                    "is_holiday": "0"
                }
            ]
        },
        {
            "period_group_id": "2",
            "period_group_alias": "야간 교시 그룹",
            "period_group_short_alias": "야간",
            "period_group_start_time": "19:00:00",
            "period_group_end_time": "23:30:00",
            "period_group_color": "4286611584",
            "period_group_icon": "moon",
            "periods": [
                {
                    "id": "73",
                    "day_of_week": "1",
                    "alias": "야간 1교시",
                    "short_alias": "1",
                    "start_time": "19:00:00",
                    "end_time": "20:00:00",
                    "is_holiday": "0"
                },
                {
                    "id": "74",
                    "day_of_week": "1",
                    "alias": "야간 2교시",
                    "short_alias": "2",
                    "start_time": "20:10:00",
                    "end_time": "21:10:00",
                    "is_holiday": "0"
                },
                {
                    "id": "75",
                    "day_of_week": "1",
                    "alias": "야간 3교시",
                    "short_alias": "3",
                    "start_time": "21:20:00",
                    "end_time": "22:20:00",
                    "is_holiday": "0"
                }
            ]
        }
    ]
}
```
{% endswagger-response %}

{% swagger-response status="404" description="조건에 부합하는 교시 그룹을 찾을 수 없는 경우입니다." %}
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


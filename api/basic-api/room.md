---
description: 교실과 관련된 API 입니다.
---

# Room

{% swagger baseUrl="https://api.iseokchan.com" path="/v1/room/:id" method="get" summary="모든 교실 혹은 특정 교실 받아오기" %}
{% swagger-description %}
id 값이 없다면, 등록된 모든 교실을 받아옵니다.

\


id 값이 있다면, 특정 교실을 받아옵니다.
{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="number" %}
교실 id 값입니다. 지정되지 않으면 모든 교실을 가져옵니다.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="studyroom" type="boolean" %}
학습실 여부입니다. 지정되지 않으면 학습실 여부에 관계 없이 값을 가져옵니다.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="iseokable" type="boolean" %}
이석 가능 여부입니다. 지정되지 않으면 이석 가능 여부에 관계 없이 값을 가져옵니다.
{% endswagger-parameter %}

{% swagger-response status="200" description="교실 정보가 정상적으로 받아온 상태입니다." %}
```
{
    "status": 200,
    "results": [
        {
            "id": "1",
            "is_studyroom": "0",
            "alias": "사감실",
            "short_alias": "사감실",
            "iseokable": "1",
            "seatmap_id": null,
            "created_at": "2020-01-16 19:40:49",
            "updated_at": "2020-02-29 14:08:44",
            "deleted_at": null
        },
        {
            "id": "2",
            "is_studyroom": "0",
            "alias": "1-1반",
            "short_alias": "1-1반",
            "iseokable": "1",
            "seatmap_id": null,
            "created_at": "2020-01-16 19:40:49",
            "updated_at": "2020-01-26 22:30:18",
            "deleted_at": null
        },
        {
            "id": "3",
            "is_studyroom": "1",
            "alias": "양현재 1실",
            "short_alias": "1실",
            "iseokable": "1",
            "seatmap_id": "4",
            "created_at": "2020-01-16 19:40:49",
            "updated_at": "2020-02-29 19:22:54",
            "deleted_at": null
        },
        {
            "id": "6",
            "is_studyroom": "0",
            "alias": "연구부",
            "short_alias": null,
            "iseokable": "1",
            "seatmap_id": null,
            "created_at": "2020-02-28 19:07:02",
            "updated_at": "2020-02-28 19:44:22",
            "deleted_at": null
        }
    ]
}
```
{% endswagger-response %}

{% swagger-response status="404" description="조건에 해당하는 교실이 존재하지 않는 경우입니다." %}
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


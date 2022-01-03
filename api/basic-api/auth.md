---
description: 인증과 관련된 API 명세입니다.
---

# Auth

{% swagger baseUrl="https://api.iseokchan.com" path="/v1/auth/login" method="post" summary="Login" %}
{% swagger-description %}
로그인을 위한 API 입니다. 로그인 성공 시 JWT 토큰을 반환하며, 로그아웃 실패 시 404 Not Found를 반환합니다.
{% endswagger-description %}

{% swagger-parameter in="query" name="username" type="string" %}
Username
{% endswagger-parameter %}

{% swagger-parameter in="query" name="password" type="string" %}
User Password
{% endswagger-parameter %}

{% swagger-response status="200" description="When success fully logged in." %}
```javascript
// 302 Temporary Redirect to root
// JWT token will be offered to Cookie.
```
{% endswagger-response %}

{% swagger-response status="404" description="When login failed." %}
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

{% swagger baseUrl="https://api.iseokchan.com/" path="v1/auth/logout" method="get" summary="Logout" %}
{% swagger-description %}
로그아웃을 위한 API 입니다. 로그아웃 성공 시 200 OK를 반환하며, 로그아웃 실패 시 401 Unauthorized를 반환합니다. 
{% endswagger-description %}

{% swagger-response status="200" description="When successfully logged out." %}
```javascript
// no content
```
{% endswagger-response %}

{% swagger-response status="401" description="When logout failed." %}
```
{
    "status": 401,
    "error": 401,
    "messages": {
        "error": "Unauthorized"
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% hint style="warning" %}
Auth API는 인증 관련 API로 사용자의 민감한 정보에 접근합니다. 따라서 이석찬은 해당 API 사용 기록을 로그하며, 과도한 요청이 이루어지는 경우 일시적으로 요청이 차단될 수 있습니다.
{% endhint %}

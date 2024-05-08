# Getting Started

Welcome to the documentation for our API! This API provides endpoints for managing courses, chapters, lessons, user subscriptions, and user information retrieval.

## Authentication

All endpoints require authentication using Token Bearer. Users need to authenticate themselves to access the API.

## Base URL

The base URL for all API endpoints is: `https://ravab.ir/api`

## Course Endpoints

### Get All Courses

<mark style="color:green;">`GET`</mark> `/courses/all`

Retrieves all available courses.

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
    [
        {
          "id": 0,
          "title": "",
          "content": "",
          "img_url": "",
          "price": 0,
          "created_at": null,
          "updated_at": null,
          "is_premium": 1
        }
    ]
}
```
{% endtab %}
{% endtabs %}

### Find Course by ID

<mark style="color:green;">`POST`</mark> `/courses/find`

Finds a course by its ID.

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name | Type   | Description |
| ---- | ------ | ----------- |
| `id` | number | Course ID   |

**Response**

{% tabs %}
{% tab title="200" %}
<pre class="language-json"><code class="lang-json"><strong>{
</strong>    "id": 0,
    "title": "",
    "content": "",
    "img_url": "",
    "price": 0,
    "created_at": null,
    "updated_at": null,
    "is_premium": 1
}
</code></pre>
{% endtab %}
{% endtabs %}

### Get Chapters of a Course

<mark style="color:green;">`POST`</mark> `/courses/chapters`

Retrieves chapters of a specific course.

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name | Type   | Description |
| ---- | ------ | ----------- |
| `id` | number | Course ID   |

**Response**

{% tabs %}
{% tab title="200" %}
```json
[
    {
        "id": 0,
        "title": "",
        "course_id": 0,
        "created_at": null,
        "updated_at": null
    }
]
```
{% endtab %}

{% tab title="403" %}
```json
{
    "error": true,
    "message": "Access Denied."
}
```
{% endtab %}
{% endtabs %}

### Get Lessons of a Chapter

<mark style="color:green;">`POST`</mark> `/courses/lessons`

Retrieves lessons of a specific chapter.

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name | Type   | Description |
| ---- | ------ | ----------- |
| `id` | number | Chapter ID  |

**Response**

{% tabs %}
{% tab title="200" %}
```json
[
    {
        "id": 0,
        "title": "",
        "content": "",
        "chapter_id": 0,
        "created_at": null,
        "updated_at": null
    }
]
```
{% endtab %}

{% tab title="403" %}
```json
{
    "error": true,
    "message": "Access Denied."
}
```
{% endtab %}
{% endtabs %}

## Subscription Endpoints

### Get User Subscription Status

<mark style="color:green;">`GET`</mark> `/subscription/status`

Retrieves the subscription status of the authenticated user.

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Response**

{% tabs %}
{% tab title="200" %}
<pre class="language-json"><code class="lang-json"><strong>{
</strong>    "id": 0,
    "expire": "2024-12-15",
    "user_id": 1,
    "created_at": null,
    "updated_at": null
}
</code></pre>
{% endtab %}

{% tab title="201" %}
```json
{
    "error": true,
    "message": "No Subscription Registered."
}
```
{% endtab %}
{% endtabs %}

## User Endpoints

### Get User Information

<mark style="color:green;">`POST`</mark> `/user/get`

Retrieves information about the authenticated user.

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
    "id": 0,
    "name": "",
    "email": "",
    "email_verified_at": null,
    "current_team_id": null,
    "profile_photo_path": null,
    "created_at": null,
    "updated_at": null,
    "two_factor_confirmed_at": null,
    "profile_photo_url": ""
}
```
{% endtab %}
{% endtabs %}

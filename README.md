# 📅 일정 관리 API

일정(캘린더)을 관리할 수 있는 RESTful API입니다.  
일정을 생성, 조회, 수정, 삭제할 수 있습니다.

---

## 📌 API 명세서

### 📝 일정 관리 API

| 기능 | 메서드 | URL | 요청 바디 | 응답 (성공) | 응답 (실패) |
|------|--------|------------|------------|------------|------------|
| **일정 생성** | `POST` | `/calendar` | `{ "task": string, "username": string, "password": string }` | `201 Created` + `{ "id": Long, "title": string, "content": string }` + `Location: /calendar/{id}` | `400 Bad Request` (필수값 없음) |
| **일정 전체 조회** | `GET` | `/calendar` | 없음 | `200 OK` + `[ { "id": Long, "title": string, "content": string }, ... ]` (없으면 `[]`) | 없음 |
| **선택 일정 조회** | `GET` | `/calendar/{id}` | 없음 | `200 OK` + `{ "id": Long, "title": string, "content": string }` | `404 Not Found` (해당 ID 없음) |
| **선택 일정 수정** | `PATCH` | `/calendar/{id}` | `{ "task"?: string, "username"?: string, "password": string }` | `200 OK` + `{ "id": Long, "title": string, "content": string }` | `400 Bad Request` (잘못된 요청) <br> `404 Not Found` (해당 ID 없음) |
| **선택 일정 삭제** | `DELETE` | `/calendar/{id}` | `{ "password": string }`| `204 No Content` | `404 Not Found` (해당 ID 없음) |

---

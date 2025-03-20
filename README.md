# 📅 일정 관리 API

일정(캘린더)을 관리할 수 있는 RESTful API입니다.  
일정을 생성, 조회, 수정, 삭제할 수 있습니다.

---

## 📌 API 명세서

### 📝 일정 관리 API

| 기능 | 메서드 | URL | 요청 바디 | Request | 응답 (실패) |
|------|--------|------------|------------|------------|------------|
| **일정 생성** | `POST` | `/calendar` | `{ "task": string, "username": string, "password": string }` | `{ "task": string, "username": string, "password": string }` | `400 Bad Request` |
| **전체 일정 조회** | `GET` | `/calendar` | 없음 | `200 OK` + `[ { "id": Long, "task": string, "username": string, "createdtime": string, "updatedtime": string } ]` (없으면 `[]`) | 없음 |
| **선택 일정 조회** | `GET` | `/calendar/{id}` | 없음 | `200 OK` + `{ "id": Long, "task": string, "username": string, "createdtime": string, "updatedtime": string }` | `404 Not Found` |
| **선택 일정 수정** | `PATCH` | `/calendar/{id}` | `{"task": string,"username": string,"password": string}` | `200 OK` + `{ "id": Long, "task": string, "username": string, "createdtime": string, "updatedtime": string }` | `400 Bad Request` | 
| **선택 일정 삭제** | `DELETE` | `/calendar/{id}` | `{ "password": string }` | `200 OK` | `404 Not Found` |


# Course Catalog API

A small FastAPI backend for listing and looking up courses, with filtering, sorting, title search, and pagination.

## Run locally

```bash
python3 -m venv .venv
source .venv/bin/activate        # Windows PowerShell: .venv\Scripts\Activate.ps1
pip install -r requirements.txt
fastapi dev main.py
```

Open <http://127.0.0.1:8000/docs> for interactive API documentation.

## Requests to verify in `/docs`

- `GET /` — returns the API status message.
- `GET /courses` — returns six courses ordered by likes, highest first (`ai-integration` first).
- `GET /courses?is_elective=true` — returns the two elective courses.
- `GET /courses?is_elective=false` — returns the four required courses.
- `GET /courses?sort=title` — sorts courses alphabetically by title.
- `GET /courses?q=api` — finds titles containing “api”, ignoring letter case.
- `GET /courses?page=2&page_size=2` — returns `web-security` and `backend-fastapi`.
- `GET /courses/{course_id}` — returns a course by ID; an unknown ID returns HTTP 404.
- `GET /courses?page=0` or `GET /courses?page_size=101` — rejected with HTTP 422 by pagination validation.
# GetCourseApi

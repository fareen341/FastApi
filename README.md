# Installation
- pip3 install fastapi
- pip3 install uvicorn

# Running
- uvicorn file_name:app_name --reload(optional)
- uvicorn main:app --reload

# Swagger UI: 
- To check all apis listed and test it: 'http://127.0.0.1:8000/docs'
- To check the docs of api, like what type of parameter a field is required etc: 'http://127.0.0.1:8000/redoc'

# Query String
- Everything in FastAPI is required even querystring, if we dont provide it'll give errror.
- If we dont give the type by default it'll take str as type.
```python
from fastapi import FastAPI
app = FastAPI()

@app.get('/blog/')
def say(published: bool, limit: int = 9):
    return {'Data': {'Blogs': f'{limit} blog post and published is: {published}.'}}

op:
{
  "Data": {
    "Blogs": "10 blog post and published is: False."
  }
}
```

# Optional Parameter
- To make a field optional
```python
# to make sort_by optional
# url: http://127.0.0.1:8000/blog/?limit=10&published=false

from fastapi import FastAPI
from typing import Optional
app = FastAPI()

@app.get('/blog/')
def say(published: bool, sort_by: Optional[str] = None, limit: int = 9):
    return {'Data': {'Blogs': f'{type(limit)} blog post and published is: {published} and sort by: {sort_by}.'}}
```

# Api Structure
<pre>
my_project/
│
├── app/
│   ├── main.py
│   ├── schemas.py
│   ├── models.py
│   └── routers/
│       └── blog.py
</pre>


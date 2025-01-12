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

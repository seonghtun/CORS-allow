# Fastapi 의 CORS 허용 구현

## 확인 방법
1. Request 요청후 브라우저 우클릭
2. 검사 를 누름
3. 네트워크(Network) 항목에서 요청한 데이터에 대한 Header를 보면 Request 와 Response Header들에 정보가 어떤지 볼수있다.

`
from fastapi import FastAPI
from fastapi.middleware.cors import CORSMiddleware

app = FastAPI()

origins = [
    "*"
]

app.add_middleware(
    CORSMiddleware,
    allow_origins=origins,
    allow_credentials=True,
    allow_methods=["*"],
    allow_headers=["*"],
)
`

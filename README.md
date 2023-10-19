# Fastapi 의 CORS 허용 구현

## 확인 방법
1. Request 요청후 브라우저 우클릭
2. 검사 를 누름
3. 네트워크(Network) 항목에서 요청한 데이터에 대한 Header를 보면 Request 와 Response Header들에 정보가 어떤지 볼수있다.

## code
```
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

@app.get("/")
async def root():
    return {"message": "Hello World"}
```

설명  페이지 : https://hanamon.kr/%eb%84%a4%ed%8a%b8%ec%9b%8c%ed%81%ac-http-options-%eb%a9%94%ec%86%8c%eb%93%9c%eb%a5%bc-%ec%93%b0%eb%8a%94-%ec%9d%b4%ec%9c%a0%ec%99%80-cors%eb%9e%80/

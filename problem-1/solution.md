<!-- TODO -->
- 등록:
    - POST /fact/{품종}/id={number}
    - 이후 body에 넣고자 하는 정보를 넣는다. URI에 넣으면 길이가 너무 길어지고, data의 내용이 보호가 되지 않아 부적절하다 판단했다.
    - ex)
        ```
        {
            "author": "Ayoung Lee",
            "fact": "A cat’s nose pad is ridged with a unique pattern, just like the fingerprint of a human."
        }
        ```

- 수정:

1. PATCH 사용
    - PATCH /fact/{품종}/id={number}
    - 이후 body에 수정하고자 하는 정보만을 넣는다.
    - ex) id 1번의 author는 그대로 두고, fact만 변경하고 싶다면 다음과 같이 body를 쓰면 된다.
        ```
        {
            "fact": "Modified fact! Yaaaaay!"
        }
        ```

2. PUT 사용
    - 우리가 사용하는 대부분의 브라우저에서 PATCH를 지원하지 않으므로, PUT을 사용하는 방법도 추가한다.
    - PUT /fact/{품종}/id={number}
    - 이후 body에 수정하고자 하는 정보뿐만 아니라, 원래의 모든 정보도 넣어주어야 한다.
    - ex) PATCH 사용 예시와 동일하게, id 1번의 author는 그대로 두고, fact만 변경하고 싶다면 다음과 같이 body를 쓰면 된다.
        ```
        {
            "author": "Ayoung Lee",
            "fact": "Modified fact! Yaaaaay!"
        }
        ```


- 삭제
    - DELETE /fact/{품종}/id={number}



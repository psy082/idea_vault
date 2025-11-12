
fetch promise는 request에 대한 promise이지 response에 대한 promise가 아니다. 

따라서 request 상에서 문제가 발생하지 않았다면 reponse와 상관 없이 resolve가 호출된다.

fetch가 reject를 호출하는 상황은 request 자체가 실패하는 경우

- 잘못 구성된 요청(Incorrectly constructed request)
- 네트워크 오류(예: DNS 조회 실패, 도달할 수 없는 네트워크)
- 요청이 중단되었습니다.
등이다.

https://kettanaito.com/blog/why-fetch-promise-doesnt-reject-on-error-responses
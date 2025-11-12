
https://velog.io/@cnsrn1874/why-you-need-react-query

fetch 요청을 간단하지만 fetch 요청을 둘러싼 비동기 상태 관리는 어렵다.

react query가 개입하는 지점은 바로 이 지점이다.

```jsx
// cancellation

function Bookmarks({ category }) {
  const { isLoading, data, error } = useQuery({
    queryKey: ['bookmarks', category],
>   queryFn: ({ signal }) =>
>     fetch(`${endpoint}/${category}`, { signal }).then((res) => {
        if (!res.ok) {
          throw new Error('Failed to fetch')
        }
        return res.json()
      }),
  })

  // 데이터와 에러 상태에 따른 JSX 반환
}
```

`queryFn`에 들어가는 `signal`을 `fetch`에 넘기면 카테고리 변경 시 요청이 자동으로 중단됩니다. --> api 세부를 확인해볼 것


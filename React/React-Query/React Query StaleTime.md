
> 데이터가 만료되어 다시 가져와야 할 필요성이 있는지를 결정하는 데 사용한다.


데이터가 만료디어 다시 가져와야 하는 시간을 지정함, 즉 이 시간이 경과할 경우
React Query는 새로운 데이터를 다시 가져옴, `staleTime` 에 기본값은 0으로
이 경우는 항상 새로운 데이터를 가져오는 것 같다.

useQuery는 데이터를 가져왔을 때 캐시에 데이터를 저장한다. 이는 브라우저의 메모리 즉 RAM이며 따라서 새로고침을 했을 때 당연히 데이터도 날라간다. 하지만 React Query에서 세션, 로컬 스토리지를 이용해서 브라우저를 새로고침해도 캐시된 데이터를 유지할 수 있도록 API를 제공하고 있다.


staletime을 설정한다하더라도 invalidateQueries를 사용하게 될 경우 무효화된 쿼리를 다시 실행하고 API 호출을 하게 됨. [캐시를 무효화시키고, 다시 데이터를 가져와서 갱신함]

- `createWebStoragePersistor`
- `createInMemoryCache`

이 두개는 나중에 조사해보도록 하자.

## 실행하기

필수로 설치하기

```bash
npm install
npm install --save svelte-routing
```
실행하기

```bash
npm run dev
```

각 페이지를 수정할 경우 route가 불안정하여 App.svelte파일을 수정할 것

```bash
<Route path='/'>
    <Login/>  <!-- 이부분을 원하는 페이지로 바꾸기 (ex: <Home/> ) -->
</Route>
```

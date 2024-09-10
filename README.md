## 프로젝트 생성

`npx create-next-app@lastest`

### UI 설치

`npx shadcn-ui@lastest init`

### 프로젝트 실행

`npm run dev`

- localhost:3000

#### app 라우터

기본

- app폴더 이하에 폴더를 만들고, 그 폴더 내부에 page.tsx를 두고 내용을 넣는 형태
- app > example > page.tsx
- localhost:3000/example이 경로가 되고, page.tsx의 내용이 example 경로의 화면이 됨
  [] 동적라우팅
- app폴더 이하에 폴더를 만들고, 그 폴더 내부에 폴더이름이 대괄호 형태 폴더 안에 page.tsx를 두는 형태
- app > users > [id] > page.tsx
- localhost:3000/users/123

```js
const IdPage =  ({
  params,
 ｝: {
  params: { id： string }
}）=>｛
  return (
    <div>
      Id: {params. id}
    </div>
  );
}；

export default IdPage;
```

![image](https://github.com/user-attachments/assets/3eaf9899-8241-4259-8ac3-becadd6a3dc8)

() 경로 숨기는 방법

- app폴더 이하에 ()형태 폴더를 만들고, 그 안에 새로운 폴더를 두는 형태
- app > (test) > something : localhost:3000/something
- app > (test) > other : localhost:3000/other
- 즉, (test)경로는 숨겨짐

#### 경로 핸들러(내부 API)

- 경로 `app/users/route.ts`

```js
import { NextResponse } from "next/server";

export function GET() {
  return NextResponse.json({
    hello: "gayoung",
  });
}
```

![image](https://github.com/user-attachments/assets/c6b832c5-0f7c-4ba8-b508-9d1edae0544b)

## 가입인증

### clerk.com

- 가입/로그인 방법: 구글계정 혹은 깃허브 계정

```
npm install @clerk/nextjs
```

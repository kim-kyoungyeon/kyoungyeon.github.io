![](https://images.velog.io/images/ww3ysq/post/67efab94-a246-4bcc-b599-b75166cbc9ea/2022-03-03_1.43.13.png)

- teammeber

  - 2 back -end
  - 2 front -end

  ***

- leader = ๋ ์๋๋ค (back-end)๐ ~~๊ฐ๋งํจ~~

---

- ์ฃผ์  - ์์ ๊ณต์  ์ปค๋ฎค๋ํฐ -์คํฌํฐํ์ด (ํด๋ก ๊ฐ์ง๋ง ์๋๋ฏํ)์ ์ฌ ์ฝ๋ฉ.

---

- ํ์ฌ status

  - ์ฟ ํค์ ์ด์ ํด๋ผ์ด์ธํธ์์ ๋๋ฆฌ๋จ
  - ํด๋ผ์ด์ธํธ๊ฐ ์ฝ๋๋ฅผ ์์ ์ ์๋ฒ์ ํฌ๋์ด ๋๋ค๊ณ  ํจ?
  - dev log๋ฅผ ๋์ถฉ์ ์๋ฏ ํ๋ค. ์๋ง ๋๊ฐ์ ์ด์๋ก ์ธํด ๋๋ง ๋ค์ณ์ ธ์ ๊ทธ๋ฐ๋ฏ
  - post controller ์ ๋ฐฐํฌ๋ฅผ ์์ํ๋ค.

  ***

- ์์ฌ์ด์ 
  - ๊ธฐ๋ก์ ์ ๋ ์ํ๋ฉด ๊ธฐ์ต์ด ๊ฐ๋ฌผ๊ฐ๋ฌผํ๋ค.
    <br>
  - module ์ด์ ๋ฐ์ํ์ผ๋ ์ ๋๋ก ์ฒ๋ฆฌ๋ฅผ ๋ชปํ๋ฏ ํจ

# err1

```jsx
 node:events:368
      throw er; // Unhandled 'error' event
     ^
Error: listen EACCES: permission denied 0.0.0.0:80
    at Server.setupListenHandle [as _listen2] (node:net:1317:21)
    at listenInCluster (node:net:1382:12)
    at Server.listen (node:net:1469:7)
    at Function.listen (/home/k2y/sec3/im-sprint-practice-deploy/server/node_modules/express/lib/application.js:618:24)
    at Object.<anonymous> (/home/k2y/sec3/im-sprint-practice-deploy/server/app.js:138:5)
    at Module._compile (node:internal/modules/cjs/loader:1101:14)
    at Object.Module._extensions..js (node:internal/modules/cjs/loader:1153:10)
    at Module.load (node:internal/modules/cjs/loader:981:32)
    at Function.Module._load (node:internal/modules/cjs/loader:822:12)
    at Function.executeUserEntryPoint [as runMain] (node:internal/modules/run_main:81:12)
Emitted 'error' event on Server instance at:
    at emitErrorNT (node:net:1361:8)
    at processTicksAndRejections (node:internal/process/task_queues:83:21) {
  code: 'EACCES',
  errno: -13,
  syscall: 'listen',
  address: '0.0.0.0',
  port: 80
}
```

# solution

- ์ ๋ฌธ์ ๋ ๊ณ์ ์๋ ์ฝ๋๋ก ์์ ๋ฐฉํธ์ผ๋ก ์ฒ๋ฆฌํจ.
- ์ Ubuntu ์์ ๋ฐ๋ณตํด์ ์๊ธฐ๋์ง์ ๋ํ ํด๊ฒฐ์ฑ ํ์.

```
sudo lsof -i :8080
sudo kill -9 [PID]
```

# erro2

```jsx
/home/ubuntu/.pm2/logs/server-error.log last 15 lines:
0|server   |     syscall: 'connect',
0|server   |     address: '127.0.0.1',
0|server   |     port: 3306,
0|server   |     fatal: true
0|server   |   },
0|server   |   original: Error: connect ECONNREFUSED 127.0.0.1:3306
0|server   |       at TCPConnectWrap.afterConnect [as oncomplete] (node:net:1161:16) {
0|server   |     errno: -111,
0|server   |     code: 'ECONNREFUSED',
0|server   |     syscall: 'connect',
0|server   |     address: '127.0.0.1',
0|server   |     port: 3306,
0|server   |     fatal: true
0|server   |   }
0|server   | }

/home/ubuntu/.pm2/logs/app-out.log last 15 lines:
/home/ubuntu/.pm2/logs/app-error.log last 15 lines:
1|app      |     at listenInCluster (node:net:1382:12)
1|app      |     at Server.listen (node:net:1469:7)
1|app      |     at Function.listen (/home/ubuntu/im-sprint-practice-deploy/server/node_modules/express/lib/application.js:618:24)
1|app      |     at Object.<anonymous> (/home/ubuntu/im-sprint-practice-deploy/server/app.js:135:5)
1|app      |     at Module._compile (node:internal/modules/cjs/loader:1101:14)
1|app      |     at Object.Module._extensions..js (node:internal/modules/cjs/loader:1153:10)
1|app      |     at Module.load (node:internal/modules/cjs/loader:981:32)
1|app      |     at Function.Module._load (node:internal/modules/cjs/loader:822:12)
1|app      |     at Object.<anonymous> (/home/ubuntu/.nvm/versions/node/v16.13.0/lib/node_modules/pm2/lib/ProcessContainerFork.js:33:23) {
1|app      |   code: 'EACCES',
1|app      |   errno: -13,
1|app      |   syscall: 'listen',
1|app      |   address: '0.0.0.0',
1|app      |   port: 80
1|app      | }
```

# solution

- errno -111 ์ด๋ถ๋ถ์ ํ์ฌ ํ์์ค

# err 3

```
npx sequelize-cli db:seed:undo ๋ฅผ ์๋ ฅํด๋ ์๋ ฅํ๋ seed๊ฐ ๋ ์ฝ๋์์ ์ฌ๋ผ์ง์ง ์๊ณ  ๋ค์ ์ค๋ณต ์์ฑ๋๋ ๊ฒฝ์ฐ๊ฐ ๋ฐ์ํ๊ณค ํจ
```

# solution

- ์์ ์ฒ๋ฆฌ
- db ๋ฐ์ดํฐ๋ฅผ ์์ ์ ๋งค๋ฒ drop -> create- > migration์ ์งํํด์ผ ํ๋๋ฐ ์ด๋ถ๋ถ์ ๋ํ ํด๊ฒฐ์ฑ ํ์ํจ

0.  ๊ธฐ์กด ๋ฐ์ดํฐ๋ฒ ์ด์ค ์ญ์ ํ์๊ณ  ๋ค์ ๋ง๋ค์

```jsx
drop database
create database
npm run start
```

1.  env ํ์ผ ์์ฑํ ๋ค์ ์ฝ๋ ์๋ ฅ

```jsx
DATABASE_USERNAME = root;
DATABASE_PASSWORD = DATABASE_NAME = "MusicFlower";
ACCESS_SECRET = secret;
```

2.  Seed ๋ฐ์ ์ํด์ ๋ค์ ๋ช๋ น์ด ์๋ ฅ

```jsx
npx sequelize-cli db:seed:all
```

> ๋ญ๊ฐ ์ ๋๋ก ์๋  ๋
> ๋ฐ์ดํฐ๋ฒ ์ด์ค ์ญ์ ํ์๊ณ  ๋ค์ ๋ง๋์๋ ๊ฒ ๋์์ง๋.

# err4

```jsx
login:1 Access to XMLHttpRequest at 'http://ec2-3-35-27-251.ap-northeast-2.compute.amazonaws.com/login' from origin 'http://musicflowerclient.s3-website.ap-northeast-2.amazonaws.com' has been blocked by CORS policy: Response to preflight request doesn't pass access control check: No 'Access-Control-Allow-Origin' header is present on the requested resource.
```

- frontend ์์ ๋ฆฌํฌํธ -> aws์์cors์๋ฌ ์์ต๋๋ค

# solution 4

```jsx
app.use(
  cors({
    origin: [`${server}`, `${localhost}`],
    credentials: true,
    methods: ["GET", "POST", "PUT", "DELETE", "OPTIONS"],
  })
);
```

- ์ origin์์ `/` ์ด๋ ๊ฒ ๋์ด์๋ ๊ฒ์ `${server}`, `${localhost}`๋ก ์์ ํ๊ฒ์ผ๋ก ๊ธฐ์ตํจ.

---

- ๊ฐ์  ์ 

1.  `๊ธฐ๋ก์ ๋งค์ผ ํ์ <- ๊ณ์ ๋ถ๊ฐ๋ฅ`
2.  ~~๋ฐฑ์๋๊ฐ~~ `๋ด๊ฐ ์คํผ๋์ ํ์ `
3.  ์๋ฒ๋ ํด๋ผ์ด์ธํธ ์๋๋ฅผ ๋น๋ฑ๋น๋ฑํ๊ฒ ํด์ค์ผ ํ๋ค.
4.  DB์ ๋ํ ๊ณ ๋ฏผ์ ๋ค๊ฐ์ด ํด๊ฒฐํด์ผ ํ๋ค.

### โ errono ์ค๋ฅ ์ฒ๋ฆฌํ๊ธฐ!

---

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

  - ๋๋์ด aws ๋ฐฐํฌ!
  - Post ์์  ์์ฒญ ๋ฐ์ดํฐ ์ฒ๋ฆฌ controller ์์ฑ
  - ์์ ๋ฆฌ์คํธ ์๋ ์ ๋ฆฌ ๋ฐ ์์ ๋ฆฌ์คํธ ์์ฒญ์ ๋ฐ์ดํฐ controller ์์ฑ
  - ์๋ฒ ๋ฐฐํฌ ๊ด๋ จ ๊ณต๋ถ
  - ํด๋ผ์ด์ธํธ ๋ฐฐํฌ ํ์ดํ ์๋ํ

  ***

- ์์ฌ์ด์ 
  - ๊ธฐ๋ก์ ์ ๋ ์ํ๋ฉด ๊ธฐ์ต์ด ๊ฐ๋ฌผ๊ฐ๋ฌผํ๋ค.
    <br>
  - aws ์๋ฒ ๋ฐฐํฌ๋ฅผ ์ํด์  mysql์ ์ฐ๋ํด์ผํด์ sequelize ๋ชจ๋์ ๊น์์ผํ๋๋ฐ.. ๊ทธ๋์ผ ํ๋๋ฐ.. ๋ชปํ๋ค.
    <br>
  - ec2์์ ์ด์ํ๊ฒ module์ ์ผ์ผ์ด ๊น์์ผ ํ๋ ์ค๋ฅ๊ฐ ๋ฐ์!
    <br>
  - ํด๋น ์ค๋ฅ ์คํฌ๋ฆฐ์ท, ์ฝ๋๋ฅผ ์ ๋ถ๋ ๊ฐ๊ณ ์ค์ง ๋ชปํจ.

# err1

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

```jsx
ssh -i "MusicFlower.pem" ubuntu@ec2-3-39-11-114.ap-northeast-2.compute.amazonaws.com
ubuntu@ec2-3-39-11-114.ap-northeast-2.compute.amazonaws.com: Permission denied (publickey).
k2y@k2y-HP-ENVY-x360-Convertible-13-ar0xxx:~$ ssh -i "MusicFlower.pem" ubuntu@ec2-3-39-11-114.ap-northeast-2.compute.amazonaws.com
```

# err2

- ec2 ๊ธฐ๋ณธ์ค์ ์ ์ด๋ ค์. Inbound ๋ณด์ ์ค์  ๋ค ์๋ํ์ผ๋ ๊ณ์ ๋ฌดํ ๋ก๋ฉ๋ง..

# solution

- EC2 ๊ธฐ๋ณธ ์ค์ ์ด ์ด๋ ค์์ ํค๋งธ๋ค. ์๋ฒ์์ ๋์ฐ๋ ํฌํธ๊ฐ ์๋ํฌ์ธํธ ๋ค์ ๋ถ๋ ๊ฒ์ ๋ค๋ฆ๊ฒ ์๊ฒ ๋์ด์ ๊ณ ์์ ํ๋ค.

# err3

- ubuntu์ ๋ฌธ์ ์ธ๊ฑด์ง, ec2 ๋ฐฐํฌ๋ ๊ณ์ ๋์จ ์ค๋ฅ!

```jsx
 server is running
AccessDeniedError [SequelizeAccessDeniedError]: Access denied for user ''@'localhost' (using password: YES)
    at ConnectionManager.connect (/home/ubuntu/Music-Flower/server/node_modules/sequelize/lib/dialects/mysql/connection-manager.js:94:17)
    at processTicksAndRejections (node:internal/process/task_queues:96:5)
    at async ConnectionManager._connect (/home/ubuntu/Music-Flower/server/node_modules/sequelize/lib/dialects/abstract/connection-manager.js:216:24)
    at async /home/ubuntu/Music-Flower/server/node_modules/sequelize/lib/dialects/abstract/connection-manager.js:174:32
    at async ConnectionManager.getConnection (/home/ubuntu/Music-Flower/server/node_modules/sequelize/lib/dialects/abstract/connection-manager.js:197:7)
    at async /home/ubuntu/Music-Flower/server/node_modules/sequelize/lib/sequelize.js:303:26
    at async MySQLQueryInterface.createTable (/home/ubuntu/Music-Flower/server/node_modules/sequelize/lib/dialects/abstract/query-interface.js:94:12)
    at async Function.sync (/home/ubuntu/Music-Flower/server/node_modules/sequelize/lib/model.js:930:5)
    at async Sequelize.sync (/home/ubuntu/Music-Flower/server/node_modules/sequelize/lib/sequelize.js:377:9) {
  parent: Error: Access denied for user ''@'localhost' (using password: YES)
      at Packet.asError (/home/ubuntu/Music-Flower/server/node_modules/mysql2/lib/packets/packet.js:728:17)
      at ClientHandshake.execute (/home/ubuntu/Music-Flower/server/node_modules/mysql2/lib/commands/command.js:29:26)
      at Connection.handlePacket (/home/ubuntu/Music-Flower/server/node_modules/mysql2/lib/connection.js:456:32)
      at PacketParser.onPacket (/home/ubuntu/Music-Flower/server/node_modules/mysql2/lib/connection.js:85:12)
      at PacketParser.executeStart (/home/ubuntu/Music-Flower/server/node_modules/mysql2/lib/packet_parser.js:75:16)
      at Socket.<anonymous> (/home/ubuntu/Music-Flower/server/node_modules/mysql2/lib/connection.js:92:25)
      at Socket.emit (node:events:527:28)
      at addChunk (node:internal/streams/readable:324:12)
      at readableAddChunk (node:internal/streams/readable:297:9)
      at Socket.Readable.push (node:internal/streams/readable:234:10) {
    code: 'ER_ACCESS_DENIED_ERROR',
    errno: 1045,
    sqlState: '28000',
    sqlMessage: "Access denied for user ''@'localhost' (using password: YES)",
    sql: undefined
  },
  original: Error: Access denied for user ''@'localhost' (using password: YES)
      at Packet.asError (/home/ubuntu/Music-Flower/server/node_modules/mysql2/lib/packets/packet.js:728:17)
      at ClientHandshake.execute (/home/ubuntu/Music-Flower/server/node_modules/mysql2/lib/commands/command.js:29:26)
      at Connection.handlePacket (/home/ubuntu/Music-Flower/server/node_modules/mysql2/lib/connection.js:456:32)
      at PacketParser.onPacket (/home/ubuntu/Music-Flower/server/node_modules/mysql2/lib/connection.js:85:12)
      at PacketParser.executeStart (/home/ubuntu/Music-Flower/server/node_modules/mysql2/lib/packet_parser.js:75:16)
      at Socket.<anonymous> (/home/ubuntu/Music-Flower/server/node_modules/mysql2/lib/connection.js:92:25)
      at Socket.emit (node:events:527:28)
      at addChunk (node:internal/streams/readable:324:12)
      at readableAddChunk (node:internal/streams/readable:297:9)
      at Socket.Readable.push (node:internal/streams/readable:234:10) {
    code: 'ER_ACCESS_DENIED_ERROR',
    errno: 1045,
    sqlState: '28000',
    sqlMessage: "Access denied for user ''@'localhost' (using password: YES)",
    sql: undefined
  }
}
```

# solution

- ์ฃผ๋ง์ ๊ณต๋ถ๋ฅผ ํด๋ณด๋ ๊ณ์ํด์ ์๋ชป๋ ์ฌ์ฉ์์๊ฒ ๊ถํ์ ์ฃผ๊ณ ์์์

`$ sudo /usr/bin/mysql -u root -p`
์ ์ฝ๋๋ก ์๋ ฅํด์ ๋ณ๋์ ๊ณ์ ์ ๋ง๋ค๊ณ , ๊ถํ์ ์ฃผ๋ ๊ฒ ๊ฐ๋ค.

๋ค๋ง git clone ํ ๋ ํ์งํ ๋ฆฌ ์๋ฒ์์๋ npm run start ์ user/bin/mysql
์ด ์๋ ๋ค๋ฅธ mysql๋ก ์๋๋๋๋ฏ ํ๋ค.  
์ด์ ์ mysql2 ๋ชจ๋๋ ๊น๊ณ  ํด์ ์ด๋์ชฝ ๋ชจ๋์ด ์งํ๋๋์ง ๋ชจ๋ฅด๊ฒ ์ผ๋
๊ณ์ํด์
์๋ฌด๋ฆฌ ์๋ก์ด ๊ณ์ ์ ํ๊ณ  ์๋ก์ด ๊ถํ์ ์ค๋..
๊ณ์ํด์
` original: Error: Access denied for user ''@'localhost' (using password: YES) at Packet.asError (/home/ubuntu/Music-Flower/server/node_modules/mysql2/lib/packets/packet.js:728:17)`
์ด ์ค๋ฅ๊ฐ ๋์์์..

`sudo mysql -u root -p` ๋ก ๊ธฐ์กด root์๊ฒ ์ฌ๊ถํ์ ์ค์ ํ๋ ์ฑ๊ณตํจ!!!!!
์๋ง ๋ค๋ฅธ mysql์ ์๋ก์ด ๊ณ์ ๋ง ์๋ฉ ๋ง๋ค์ด์ ธ์๋ ๊ฒ์ผ๋ก ํ์ํจ

---

์ถ์ฒ

---

[EC2 MYSQL ์ค์น๋ฌธ์ 1](https://curryyou.tistory.com/434)
[EC2 MYSQL ์ค์น๋ฌธ์ 2](https://velog.io/@seungsang00/Ubuntu-%EC%9A%B0%ED%88%AC%EC%97%90-MySQL-%EC%84%A4%EC%B9%98%ED%95%98%EA%B8%B0)
[EC2 MYSQL ์ค์น๋ฌธ์ 3](https://curryyou.tistory.com/434)
[Ec2 mysql ๊ถํ]https://5sangs.tistory.com/214?category=966746
[Ec2 mysql ๊ถํ ]https://ssungkang.tistory.com/entry/React-axios-%EC%9D%98-withCredentials

---

- ๊ฐ์  ์ 

1.  `๊ธฐ๋ก์ ๋งค์ผ ํ์ <- ๊ณ์ ๋ถ๊ฐ๋ฅ`
2.  ~~๋ฐฑ์๋๊ฐ~~ `๋ด๊ฐ ์คํผ๋์ ํ์ `
3.  ํด๋ผ์ด์ธํธ ์๋ฒ ๋์ ํด๋ณด๊ธฐ (mysql, mysql2 ์ค์น๋ฌธ์ ๋ ์ ์ผ๋จ ์ ์ธ)

### โ ec2 ๊ณต๋ถํ๊ธฐ

---

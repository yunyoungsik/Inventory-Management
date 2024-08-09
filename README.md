# inventory management

[참고영상](https://youtu.be/ddKQ8sZo_v8?si=7Smg8bIzXgc6_JS4)

6:05:03까지 완료

## 설치
```
client
npm i @mui/x-data-grid @mui/material @emotion/react @emotion/styled lucide-react numeral recharts uuid axios
npm i -D @types/node @types/uuid @types/numeral
npm i -D tw-colors
npm i react-redux @reduxjs/toolkit dotenv
npm i redux-persist

server
npm i prisma @prisma/client
npx prisma init
npx tsc --init
npm i -D ts-node typescript @types/node
npx prisma generate
npx prisma migrate dev --name init
npm run seed
npm i express body-parser cors dotenv helmet morgan concurrently
npm i -D nodemon @types/cors @types/express @types/morgan
npm i rimraf
npm run dev
curl http://localhost:8000/dashboard

amazone Linux
sudo su -
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
. ~/.nvm/nvm.sh
nvm install node
node -v
npm -v

*github upload

sudo yum update -y
sudo yum install git -y
git --version
git clone [주소]
ls
cd [폴더명]
ls
cd server
npm i
npm run dev

*인스턴스 -> 보안 -> 인바운드 규칙 -> 80, 443, 22 포트 확인
echo "PORT=80" > .env
npm run dev

*인스턴스에서 퍼블릭 IPv4 주소 복사 후 http://[퍼블릭 주소]로 접속 후 amazone Linux 확인

npm i pm2 -g
sudo env PATH=$PATH:$(which node) $(which pm2) startup systemd -u $USER --hp $(eval echo ~$USER)
pm2 start ecosystem.config.js
pm2 status
pm2 monit
pm2 delete all

* 데이터베이스 생성 후

sudo su -
ls
cd [폴더명]/
cd server
nano .env -> DATABASE_URL="postgresql://postgres:[비밀번호]@[데이터베이스 엔드폰이트]:[데이터베이스 포트]/[데이터베이스이름]?schema=public"
*ctrl + o -> enter 저장, ctrl + x로 빠져나오기
pm2 status
pm2 delete all
npx prisma generate
npx prisma migrate dev --name init
npm run seed
pm2 start ecosystem.config.js
pm2 monit
```


```
배포

[index.ts]
/* server */
const port = Number(process.env.PORT) || 3001;
app.listen(port, "0.0.0.0", () => {
  console.log(`Server running on port ${port}`);
});

[ecosystem.config.js]
module.exports = {
  apps: [
    {
      name: 'inventory-management',
      script: 'npm',
      args: 'run dev',
      env: {
        NODE_ENV: 'development',
        ENV_VAR1: 'environment-variable',
      },
    },
  ],
};
```

```
[에러]
Amazone Linux에서 'npm run dev'로 실행을 할때 아래와 같은 오류가 발생
> server@1.0.0 dev
> npm run build && concurrently "npx tsc -w" "nodemon --exec ts-node src/index.ts"


> server@1.0.0 build
> rimraf dist && npx tsc

sh: line 1: rimraf: command not found

[해결방법]
npm install rimraf --save-dev를 입력하면 해결 됨
```
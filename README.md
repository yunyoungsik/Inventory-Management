# inventory management

[참고영상](https://youtu.be/ddKQ8sZo_v8?si=7Smg8bIzXgc6_JS4)

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
```
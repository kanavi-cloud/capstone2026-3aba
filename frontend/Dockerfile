# 1. 빌드 단계
FROM node:18 AS build
WORKDIR /app

# 컨텍스트 내의 package.json 복사
COPY package*.json ./
RUN npm install

# [수정된 부분] 점 두 개(..)가 아니라 현재 폴더 전체(.)를 복사해야 합니다.
COPY . .

RUN npm run build

# 2. 실행 단계
FROM nginx:stable-alpine
COPY --from=build /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
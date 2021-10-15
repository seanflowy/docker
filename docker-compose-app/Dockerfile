# 베이스 이미지를 명시해준다.
# <이미지 이름>:<태그> 형식으로 작성하며, 태그를 안붙이면 자동으로 가장 최신 것으로 다운로드 받는다.
# FROM baseImage
FROM node:10

WORKDIR /usr/src/app

# COPY <복사 할 파일 경로> <컨테이너 내에서 파일이 복사될 경로>
# 컨테이너 안에 package.json, server.js를 넣어주어야 한다.
COPY package.json ./

# 추가적으로 필요한 파일들을 다운로드 받는다.
# 도커 이미지가 생성되기 전에 수행해야 할 쉘 명령어
# RUN command
RUN npm install

# 매번 빌드 시마다 종속성을 다 다시 다운로드 받지 않게 하기 위해 종속성 부분만 COPY를 별도로 분리
COPY ./ ./

# 컨테이너 시작 시 실행 될 명령어를 명시해준다.
# CMD ["executable"]
CMD ["node", "server.js"]
FROM node:lts-alpine

WORKDIR /safira
RUN apk add git && \
    git clone https://github.com/rafante/safiralab_app 

WORKDIR /safira/safiralab_app

RUN yarn

CMD yarn start

EXPOSE 3000
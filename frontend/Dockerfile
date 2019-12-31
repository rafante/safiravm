FROM node:lts-alpine

WORKDIR /safira
RUN apk add git && \
    git clone https://github.com/rafante/safiralab_app

WORKDIR /safira/safiralab_app

RUN yarn global add serve && \
    yarn && \
    yarn build

CMD serve -s build

EXPOSE 5000
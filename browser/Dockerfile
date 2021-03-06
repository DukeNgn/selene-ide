ARG NODE_VERSION=12.18.3
FROM node:${NODE_VERSION}-alpine

RUN apk add --no-cache make pkgconfig gcc g++ python libx11-dev libxkbfile-dev

WORKDIR /home/theia
ADD package.json ./package.json
ADD selene-preload.html .
ADD scripts/ scripts
ARG GITHUB_TOKEN
ARG NODE_OPTIONS="--max_old_space_size=12040"

RUN yarn --pure-lockfile && \
    yarn prepare
RUN yarn --production
RUN yarn autoclean --init && \
    echo *.ts >> .yarnclean && \
    echo *.ts.map >> .yarnclean && \
    echo *.spec.* >> .yarnclean && \
    yarn autoclean --force && \
    yarn cache clean

FROM node:${NODE_VERSION}-alpine

RUN addgroup theia && \
    adduser -G theia -s /bin/sh -D theia;
RUN chmod g+rw /home && \
    mkdir -p /home/project && \
    chown -R theia:theia /home/theia && \
    chown -R theia:theia /home/project;
RUN apk add --no-cache git openssh bash
ENV HOME /home/theia
WORKDIR /home/theia
COPY --from=0 --chown=theia:theia /home/theia /home/theia
EXPOSE 3000
ENV SHELL=/bin/bash \
    THEIA_DEFAULT_PLUGINS=local-dir:/home/theia/plugins
ENV USE_LOCAL_GIT true
USER theia
ENTRYPOINT [ "node", "/home/theia/src-gen/backend/main.js", "/home/project", "--hostname=0.0.0.0" ]

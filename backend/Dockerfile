FROM node:20.15.0-alpine3.20
EXPOSE 8080
ENV  DB_HOST=mysql
RUN  addgroup -S expense && adduser -S expense -G expense \
     && mkdir /opt/server \
     && chown expense:expense -R /opt/server
# if we have multiple commands to run we can use the above format it will reduce the layers
#RUN mkdir /opt/server
#RUN chown expense:expense -R /opt/server
WORKDIR /opt/server
COPY package.json .
COPY *.js .
RUN npm install
USER expense
CMD [ "node", "index.js" ]



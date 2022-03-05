FROM node AS build
RUN       useradd -m -d /app roboshop
USER      roboshop
WORKDIR   /app
ADD       package.json .
RUN       npm install


# Run build
FROM node 
RUN       useradd -m -d /app roboshop
USER      roboshop
WORKDIR   /app
COPY --from=build /app/node_modules /app/node_modules
ADD       server.js .
CMD       ["node","server.js"]
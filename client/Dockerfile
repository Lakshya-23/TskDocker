FROM node:20-alpine

WORKDIR app/

COPY package*.json .

RUN npm install

COPY . .

# VITE_API_URL passed from docker-compose at build time
# (For local dev, Vite uses .env automatically)
# if using cloud (Aws Ec2 they have their own secret env)so comment out below line and add .env in dockerignore file    
ARG VITE_API_URL
ENV VITE_API_URL=$VITE_API_URL


RUN npm run build

EXPOSE 5173

CMD ["npm","run","preview"]

#CMD ["npm","run","preview","--","--host"]
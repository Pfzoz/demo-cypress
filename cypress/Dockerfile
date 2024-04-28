FROM node

ENV NO_UPDATE_NOTIFIER=1

EXPOSE 3000
EXPOSE 5000

WORKDIR /app

ADD . .
RUN npm install --silent --loglevel=error

RUN useradd -ms /bin/bash cypressuser

WORKDIR /e2e

RUN chown -R cypressuser:cypressuser /e2e

USER cypressuser

COPY package*.json ./


CMD ["npm", "run", "exec"]

FROM node:alpine As development

WORKDIR /Users/brian/Documents/programming/docker/airbnb

COPY package.json ./
COPY yarn.lock ./
COPY tsconfig.json tsconfig.json
COPY nest-cli.json nest-cli.json

# RUN npm i -g yarn
RUN yarn

COPY apps/payments apps/payments
COPY libs libs

RUN cd apps/payments && yarn

RUN yarn build payments

FROM node:alpine As production

ARG NODE_ENV=production
ENV NODE_ENV=${NODE_ENV}

WORKDIR /Users/brian/Documents/programming/docker/airbnb

COPY package.json ./
COPY yarn.lock ./

# RUN npm i -g yarn
RUN yarn --prod

COPY --from=development /Users/brian/Documents/programming/docker/airbnb/dist ./dist

CMD [ "node", "dist/apps/payments/main" ]
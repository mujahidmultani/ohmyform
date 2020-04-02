FROM node:10 AS builder
MAINTAINER MySurvay <admin@ohmyform.com>

WORKDIR /opt/app

# just copy everhing
COPY . .

RUN yarn install --frozen-lockfile
RUN yarn build

FROM nginx

COPY --from=builder /opt/app/dist /var/share/nginx/html

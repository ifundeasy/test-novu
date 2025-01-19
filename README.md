# test-novu

## Prerequisites
* Novu server: v2.0.0
* Novu client: latest

## Installation

### Docker

Step-1: start novu parties
```sh
cd base
docker compose up -d
```

Step-2: start novu services
```sh
cd novu
docker compose up -d
```

### Kubernetes

Step-1: start novu parties
```sh
cd base
docker compose up -d
```

Step-2: start novu services
```sh
cd novu

kubectl apply -f ./worker
kubectl apply -f ./ws
kubectl apply -f ./api
kubectl apply -f ./web
```

## Local studio

Step-3: start novu studio
```sh
npx novu@latest dev -d http://localhost:4200 -o http://localhost:4000
```
> But this doesn't work, idk :D

Open Novu local studio on http://localhost:2022, pick secret-key on page show, Then continue to Step-4

Step-4: on your app (as novu client), start develop notification
```sh
rm -rf my-novu-app
# This is example project from novu (as novu client)
# $SECRET_KEY can be found on your local studio (http://localhost:2022)
npx novu@latest init -s $SECRET_KEY -a http://localhost:3000

cd my-novu-app
npm run dev
```
> But this doesn't work, idk :D

Example
```sh
rm -rf my-novu-app
npx novu@latest init -s 4cc01e0cf6ac44dc8db104a3a37903bd -a http://localhost:3000
cd my-novu-app
npm run dev
```
> But this doesn't work, idk :D
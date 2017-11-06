# Angular 5 Universal Progressive Web App - starter
This repo is boilerplate of Angular Universal (serverside rendering) applications.
It is running as a **(PWA) progressive web app** with the whole goodness of it (pushes, content caching)!
It is prepared to be easily deployed on serverless environment (like AWS Lambda).

This is a great starting point for **microservices application**! Because of support for external modules, you can split your application into separate projects and combine them together when deploying!

## Live demo
[Angular Universal PWA on AWS Lambda + API Gateway](https://www.angular-universal-pwa.maciejtreder.com)


## What's inside?
* PWA (thanks to service worker application content is cached for offline working, it can be also installed as native app on Android devices and Google Chrome)
* Push notifications:
    * Vapid webpush (Chrome and Firefox) - Using [aws-sns-webpush](https://github.com/maciejtreder/aws-sns-webpush) as back-end
    * Safari push - Using [aws-sns-webpush](https://github.com/maciejtreder/aws-sns-webpush) as back-end
* External modules (You can split your application into multiple projects and lazy-load them, [read more here](https://github.com/maciejtreder/angular-external-module))
* Angular Material
* [ng-http-sw-proxy (all requests done offline, are synced when app comes back online)](https://github.com/maciejtreder/ng-http-sw-proxy)
* Unit tests
* e2e tests - in progress

### Used frameworks/technologies
* Webpack
* UglifyJS
* OptimizeJS
* DllPlugin (super fast reloading in development mode)
* Sass loader
* Serverless framework


## Get Started
```sh
git clone https://github.com/maciejtreder/angular-universal-pwa.git
cd angular-universal-serverless
npm install
npm start
```
* Development mode (autoreload + unit tests): ```npm start```
* Development mode (autoreload only): ```npm run build:dev```
* Unit tests: ```npm run test```


## Production mode
Includes AoT
```sh
cp -r node_modules/ng-http-sw-proxy/service-worker .
npm run build:prod
npm run server
```

## Deploy on AWS Lambda
```sh
cp -r node_modules/ng-http-sw-proxy/service-worker .
npm run build:deploy
```


##### Other info
Built on top of [ng-universal-demo](https://github.com/FrozenPandaz/ng-universal-demo)

# Spring Boot, Vue3 and Bootstrap-vue-3 Hello World Example on Heroku

## Development

- Run the Spring Boot application which will run on port 8080
- Run the Vue application in (/src/frontend) by "npm run serve"  which will run on port 3000
- All calls to `/api/**` are proxied to 8080 thanks to `vue.config.js`

## Packaging

When you run `mvn clean package` the frontend Vue application will build in the `dist` directory.
The Maven plugin `maven-resources-plugin` will copy the contents of the build directory into `/target/static/classes`

## Deploying on Heroku
#### Details:https://devcenter.heroku.com/articles/deploying-executable-jar-files

>heroku deploy:jar  .\target\springboot-vuejs-example-0.0.1-SNAPSHOT.jar --app vuejs-springboot

https://vuejs-springboot.herokuapp.com

#### Logs
>heroku logs --tail --app vuejs-springboot

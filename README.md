An example project with Vue3, Spring Boot, bootstrap-vue-3 on Heroku

You can test the application https://vuejs-springboot.herokuapp.com Note that it is only running on a
free dyno, so it may take some time before it responds.

## Development

- Run the Spring Boot application which will run on port 8080
- Run the Vue application in (/src/frontend) by "npm run serve"  which will run on port 3000
- All calls to `/api/**` are proxied to 8080 thanks to `vue.config.js`

## Packaging

When you run `mvn clean package` the frontend Vue application will build in the `dist` directory.
The Maven plugin `maven-resources-plugin` will copy the contents of the build directory into `/target/static/classes`

## Deploying to Heroku

```bash
heroku deploy:jar  .\target\springboot-vue3-heroku-0.0.1-SNAPSHOT.jar --app vuejs-springboot
```
#### Details:https://devcenter.heroku.com/articles/deploying-executable-jar-files
#### Logs
```bash
>heroku logs --tail --app vuejs-springboot
```
# Pro-MERN-Stack-IssueTracker-UI-Deploy

### Deploy UI
* /server/uiserver.js: Change in Name of PORT Environment Variable
* /sample.env: Change in Name of PORT Environment Variable
* /package.json: Changes for Specifying engine, postinstall, and post-build

### command
* $ heroku create tracker-ui-$GITHUB_USER
* $ heroku config:set \
UI_API_ENDPOINT=https://tracker-api-$GITHUB_USER.herokuapp.com/graphql \
UI_AUTH_ENDPOINT=https://tracker-api-$GITHUB_USER.herokuapp.com/auth \
GOOGLE_CLIENT_ID=$GOOGLE_CLIENT_ID
* $ git push heroku main

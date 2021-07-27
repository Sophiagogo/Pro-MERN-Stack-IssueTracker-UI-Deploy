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
* $ git push heroku main (note: if we change sth in package.json, need to run push again)
* heroku open
* heroku logs to troubleshoot.

### Proxy Mode
*  Signing in at this point will not work because of the new domain being used and due to CORS and cookie considerations, then we need to set up proxy mode.
*  heroku config:set \
UI_API_ENDPOINT=https://tracker-ui-$GITHUB_USER.herokuapp.com/graphql \
UI_AUTH_ENDPOINT=https://tracker-ui-$GITHUB_USER.herokuapp.com/auth \
UI_SERVER_API_ENDPOINT=https://tracker-api-$GITHUB_USER.herokuapp.com/graphql \
API_PROXY_TARGET=https://tracker-api-$GITHUB_USER.herokuapp.com
* /uiserver.js: Change Origin When Proxying Requests

### skip non-proxy deployment
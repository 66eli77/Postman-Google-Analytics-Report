# Postman-Google-Analytics-Report

<a href="https://i.imgur.com/kIVcm08.png" target="_blank"><img src="https://i.imgur.com/kIVcm08.png"></a>

This collection calls Google Analytics Reporting API to query the report and post to Slack.

### Workflow:

<a href="https://i.imgur.com/LHSsq9G.png" target="_blank"><img src="https://i.imgur.com/LHSsq9G.png"></a>

### Notes:

* You need to set up a project with [Google APIs console](https://console.developers.google.com/apis/credentials). And under `Credentials`, follow this workflow: click `Create credentials` ==> choose `OAuth client ID` ==> select `Web application` -> fill <your name> -> fill <your redirect url> with `https://www.getpostman.com/oauth2/callback` ==> click `Create`
	1. save the `Client ID` and `Client secret` in a safe place.

<a href="https://i.imgur.com/fiPAJk7.png" target="_blank"><img src="https://i.imgur.com/fiPAJk7.png"></a>

* Go to this collection in Postman, under the `Auth` tag, follow this workflow: choose `OAuth 2.0` from the Tpye dropdown list ==> click `Get New Access Token` ==> fill `Auth URL` with `https://accounts.google.com/o/oauth2/v2/auth?access_type=offline` -> fill `Access Token URL` with `https://www.googleapis.com/oauth2/v4/token` -> fill `Client ID` with the client ID you got above -> fill `Client Secret` with the client secret you got above -> fill `Scope(Optional)` with `https://www.googleapis.com/auth/analytics.readonly` -> select `Authorization Code` from the dropdown list -> check `Request access token locally` -> click `Request Token`
	1. Save the `refresh_token` in a safe place (**Important !**)
	2. Save the `access_token` and use it in the next couple minutes.

<a href="https://i.imgur.com/6g45Zor.png" target="_blank"><img src="https://i.imgur.com/6g45Zor.png"></a>

* If you forgot to save the `refresh_token` for the first time you send the request, you won't be able to get the `refresh_token` again. Here's what you need to do: go to [Google Sign-in & security](https://www.google.com/settings/u/1/security) ==> scroll down to `Connected apps & sites` and click `MANAGE APPS` ==> click on your project ==> click `REMOVE` ==> click `Request Token` in Postman again

<a href="https://i.imgur.com/wL86flT.png" target="_blank"><img src="https://i.imgur.com/wL86flT.png"></a>
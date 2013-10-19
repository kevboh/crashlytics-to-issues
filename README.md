crashlytics-to-issues
=====================

Small, heroku-compatible node app to listen for Crashlytics web hooks and create corresponding Github issues.

## Using it on Heroku

1. Fork the repo.
2. Clone locally.
3. Run `heroku create` in your local repo to create a heroku app and add the heroku remote. See [this](https://devcenter.heroku.com/articles/nodejs) for more info.
4. Add your environment vars. See below.

## Environment vars

The app uses environment variables to authenticate to Github, choose the repo for issues, and assign the issue to a user. These variables are:

* USER: The user to authenticate as and assign issues to. Right now this is always the same user since I'm a one-person shop, but feel free to send pull requests allowing differentiation.
* PASS: Password for USER. Right now the app uses basic auth. Feel free to send pull requests for OAuth2 (sense a pattern here?).
* ORGANIZATION: The repo's organization or your github username
* REPO: The repo to file issues on.

To set environment vars (called "config vars") in Heroku, do:

    heroku config:set USER=[your user]
    heroku config:set PASS=[user's pass]
    heroku config:set ORGANIZATION=[the repo's organization]
    heroku config:set REPO=[the repo]

## Configuring the Crashlytics Web Hook

To add a web hook to your app in Crashlytics, select the settings (gears) next to your app name, select Integrations, and add the URL to your running app as a Web Hook.

## Disclaimer

I've never written anything in node before! Be kind in your pull requests :)

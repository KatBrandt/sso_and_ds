# Kat Brandt's Tech Challenge

This example application demonstrates the integration of [WorkOS SSO](https://workos.com/docs/reference/sso) and [DirectorySync](https://workos.com/docs/reference/directory-sync). 

Base Example Code from [ruby-example-applications/ruby-sso-example](https://github.com/workos/ruby-example-applications/tree/main/ruby-sso-example)

## Running this app locally

### Clone and Install

1. Clone the repo:

```sh
git clone git@github.com:KatBrandt/workos_tech_challenge.git
```

2. Navigate into directory and install dependencies:

```sh
cd workos_tech_challenge
bundle install
```

### Configure your environment

You will need to set the following secrets:

```sh
WORKOS_API_KEY
WORKOS_CLIENT_ID
WORKOS_ORGANIZATION_ID
DIRECTORY_ID
```
Please contact me, to get these secrets so you can run this app locally. 

3. Run `cp .env.example .env` and add the appropriate secrets to the .env file.


### Run the app and log in using SSO

```sh
ruby app.rb
```

Head to `http://localhost:4567` and click Sign In to authenticate!

However, until you have those secrets setup, you won't be able to authenticate. 

You can click on `Directory` to see the list of users currently in the Directory. (Or head to `http://localhost:4567/users`).

## Demo

Here's a demonstration of the application in action, showing successful login to "New Shiny App" via Okta as well as displaying the list of users in the Directory.



https://github.com/user-attachments/assets/638003ec-5215-4a81-83b9-f0bbd112dd1e






# Kat Brandt's Tech Challenge

This example application demonstrates the integration of WorkOS SSO and DirectorySync. 

Base Example Code from [ruby-example-applications/ruby-sso-example](https://github.com/workos/ruby-example-applications/tree/main/ruby-sso-example)

## Clone and Install

1. Clone the repo:

```sh
git clone git@github.com:KatBrandt/workos_tech_challenge.git
```

2. Navigate into directory and install dependencies:

```sh
cd workos_tech_challenge
bundle install
```

## Configure your environment

You will need the following secrets set:

```sh
WORKOS_API_KEY
WORKOS_CLIENT_ID
WORKOS_ORGANIZATION_ID
DIRECTORY_ID
```

1. Run `cp .env.example .env` and add the appropriate secrets.


## Run the app and log in using SSO

```sh
ruby app.rb
```

Head to `http://localhost:4567` and click Sign In to authenticate!

However, until you have those secrets setup, you won't be able to authenticate. 

You can click on `Directory` to see the list of users currently in the Directory. (Or head to `http://localhost:4567/users`).

## Demo

Here's a demonstration of the application in action:

<video width="800" controls>
  <source src="videos/app-demo.mov" type="video/mov">
  Your browser does not support the video tag.
</video>




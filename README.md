# Meteor Vue Enterprise Starter

[![CircleCI](https://circleci.com/gh/ejfrancis/Meteor-Vue-Modular-App-Starter/tree/master.svg?style=svg)](https://circleci.com/gh/ejfrancis/Meteor-Vue-Modular-App-Starter/tree/master)

An opinionated starter kit application utilizing the following libraries/frameworks, with an emphasis on code modularity:

* Meteor 1.6
* Vue 2
* vuex 2
* vue-router 2
* vuex-router-sync
* vuex-alt
* vue-meteor-tracker
* iView UI toolkit
* vue-media

The following development tools are used:

* Jest - unit tests
* Chimp - e2e tests
* semistandard - code linting
* meteor-husky - git hooks
* CircleCI - continuous integration

*Note:* This starter kit is geared towards enterprise software. If you're looking to put together a quick prototype, this may be overkill.

![sign in desktop](https://user-images.githubusercontent.com/3171352/29747188-784f80da-8aa5-11e7-876c-95ebf08e7278.png)
![sign in mobile](https://user-images.githubusercontent.com/3171352/29747190-85748d6e-8aa5-11e7-85d7-8900bf85de1f.png)
![home page](https://user-images.githubusercontent.com/3171352/29747193-8e6863aa-8aa5-11e7-980b-bd519062baae.png)
# Usage

First, clone this repo 

```
git clone https://github.com/ejfrancis/Meteor-Vue-Enterprise-Starter
```

Then enter the new directory where it was cloned into, and install dependencies:

```
cd Meteor-Vue-Enterprise-Starter
meteor npm install
```

Now to run the application:

```
meteor npm start
``` 

# Mimic Production
To run the app with a production bundle and using the production settings located at `config/config.production.json`, run:

```
meteor npm run start:mimic-prod
```

# UI Framework Components
The [iView UI framework](https://www.iviewui.com) is used for reusable, uniform components for things like form inputs, buttons, and a responsive grid layout. See the documentation of iView for more information on the components available.

# Application Config
You can provide application config/settings values in the `config/` directory, which will be made available via `Meteor.settings` in your code. You'll see two files:

* `config/config.development.json`: local config, used when `meteor npm start` is run
* `config/config.production.json`: production config, use this for production values. ([see the Meteor guide](https://docs.meteor.com/environment-variables.html#METEOR-SETTINGS))

# Testing

## Unit Tests
See the [Unit Tests documentation](/docs/unit-tests.md).

## E2E Tests
See the [E2E Tests documentation](/docs/e2e-tests.md).

# Code Linting
Code linting is done with [semistandard](https://www.npmjs.com/package/semistandard), which is a pre-configured eslint that works out of the box with an opinionated ruleset. Run code linting with this command:
```
meteor npm run lint
```

To automatically fix linting errors, run:
```
meteor npm run lint:fix
```

# Routing
Routing is done on the client with VueRouter. The router configuration is located at [src/imports/modules/router/client/lib/router.js](/src/imports/modules/router/client/lib/router.js).

The router configuration includes an example of lazy-loading your route components, to avoid them being included in your initial client JavaScript bundle.

# Client State Management with Vuex
See the [Vuex State Management documentation](/docs/vuex-client-state-management.md).


# Application Structure
The directory structure is built in a way to make things predictable and enforce code modularity and organization per feature/domain by splitting the code into "Application Modules".

See the [Application Structure documentation](/docs/application-structure.md).

# Continuous Integration
A CircleCI configuration for running code linting, unit tests, and e2e tests against a local app server is located in [`.circle/config.yml`](/.circleci/config.yml). If the build is taking too long, you can split the unit tests and code linting into one job, and e2e tests in another job with a CircleCI Workflow.

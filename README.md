# AmplifyApp

## Description
The AmplifyApp is a basic notes app for creating and saving notes with a title, description, and optional image. The app uses [AWS Amplify](https://github.com/aws-amplify) libraries to leverage Amazon Cognito to authenticate and manage users. Users are required to login or create a user profile prior to saving any notes in the app.

## Purpose
The purpose of this application was for [@AntonioJacksonII](https://github.com/AntonioJacksonII) to build a React application using AWS Amplify, following the [Build a Full-Stack React Application](https://aws.amazon.com/getting-started/hands-on/build-react-app-amplify-graphql/) AWS tutorial. Tasks completed include:
* Building and hosting a single-page React application on AWS
* Adding authentication
* Adding a GraphQL API and database
* Updating the application to store images

## Installation and Usage
To use the application, run the following commands in your Terminal:
1. Clone this repository with `git clone git@github.com:AntonioJacksonII/amplifyapp.git`
1. Run `npm install` to install all of the dependencies
1. Run `npm start` to start the development server. If your browser window does not automatically open, navigate to `http://localhost:3000/`. You will be prompted to create an account or login to an existing account.
1. After you have created an account and successfully logged in, you can enter a note name, note description, and upload an optional image to associate with the note.
1. After a note has been created, you can delete the note by clicking the `Delete note` button below the image description or associated image.

## Known Issues
The completed application can only run locally and is not currently deployed to AWS Amplify due to the following `JSONValidationError` encountered during the build process:
```
                                 # Executing command: amplifyPush --simple
2020-12-07T04:00:12.409Z [INFO]: File project: data should NOT have additional properties: 'graphqltransformer'
2020-12-07T04:00:12.410Z [INFO]: JSONValidationError: File project: data should NOT have additional properties: 'graphqltransformer'
                                 at validator (/root/.nvm/versions/node/v12.19.0/lib/node_modules/@aws-amplify/cli/node_modules/amplify-cli-core/lib/feature-flags/featureFlags.js:136:27)
                                 at featureFlagsValidator (/root/.nvm/versions/node/v12.19.0/lib/node_modules/@aws-amplify/cli/node_modules/amplify-cli-core/lib/feature-flags/featureFlags.js:140:17)
                                 at FeatureFlags.validateFlags (/root/.nvm/versions/node/v12.19.0/lib/node_modules/@aws-amplify/cli/node_modules/amplify-cli-core/lib/feature-flags/featureFlags.js:146:17)
                                 at FeatureFlags.loadValues (/root/.nvm/versions/node/v12.19.0/lib/node_modules/@aws-amplify/cli/node_modules/amplify-cli-core/lib/feature-flags/featureFlags.js:204:18)
                                 at async Function.FeatureFlags.initialize (/root/.nvm/versions/node/v12.19.0/lib/node_modules/@aws-amplify/cli/node_modules/amplify-cli-core/lib/feature-flags/featureFlags.js:267:5)
                                 at async Object.run (/root/.nvm/versions/node/v12.19.0/lib/node_modules/@aws-amplify/cli/lib/index.js:73:9)
2020-12-07T04:00:12.418Z [ERROR]: !!! Build failed
```
This error appears to be caused by the @aws-amplify validator that is triggered by the `amplifyPush --simple` command. This code is hosted by AWS Amplify, so an [issue](https://github.com/aws-amplify/amplify-console/issues/1345) was opened with them for additional details about resolving this error.
<img src="https://github.com/withvenny/venny-apps-photos-reactnative/blob/master/venny-io-apps-cover-Lookio.png">

# Lookio from Venny

Lookio is a photo sharing app from Venny. We believe that enabling users to capture their special moments is a cornerstone of modern digital experiences.

Projects that use React Native to tell the story of humanity. Here we'll capture how humans interact with each other using technology.

Using React Native and the Venny I/O APIs we'll explore...

Chatio is a messaging app from Venny.	We believe that enabling users to share ideas with each other is a cornerstone of modern digital experiences.

Crowdio is a social media app from Venny.	We believe that enabling users to share their special moments is a cornerstone of modern digital experiences.

Dealio is a buying app from Venny.	We believe that enabling users to make secure purchases is a cornerstone of modern digital experiences.

## SecondThought
We're creating a simple app to allow iOS &amp; Android users that allows the starting and stopping of audio recording while famous quotes loop in the background.

Users should be able to:
* press record which would begin recording audio to their device
* as well as upload a final audio file to our AWS S3 bucket. 

https://github.com/electron/electron/blob/master/README.md
https://github.com/angular/angular.js/blob/master/README.md
https://github.com/huextrat/TheGorgeousLogin/blob/master/README.md
https://github.com/serverless/serverless/blob/master/README.md

_PLEASE NOTE: It is important that this app be developed with React Native because we want to deploy to our student group for testing on either iOS or Android devices._

|User Action|View|Priority|
|-|-|-|
|User register|<img src="https://github.com/reactnatively/react-secondthought/blob/master/secondthought-register.png" width="150">|Medium|
|User login|<img src="https://github.com/reactnatively/react-secondthought/blob/master/secondthought-login.png" width="150">|Medium|
|User not recording|<img src="https://github.com/reactnatively/react-secondthought/blob/master/secondthought-home-notrecording.png" width="150">|Critical|
|User currently recording|<img src="https://github.com/reactnatively/react-secondthought/blob/master/secondthought-home-recording.png" width="150">|Critical|
|Audio Files List|<img src="https://github.com/reactnatively/react-secondthought/blob/master/secondthought-files.png" width="150">|Critical|
|Audio File|<img src="https://github.com/reactnatively/react-secondthought/blob/master/secondthought-file.png" width="150">|Critical|

## React Natively API
* URL: http://api.reactnatively.venny.co/v1/
* endpoint: /quotes

Explore the API a bit more via [Postman collection](https://documenter.getpostman.com/view/2396336/RWToQdmz).

|Key|Value (Example)|Description|
|-|-|-|
|token|NWU1MWQ4NzIwOTY0OGNjMTNkZWI1MjNiMjA1ZA==|Token required for access to the API|
|text|If you are not willing to risk the usual you will have to settle for the ordinary.|Quote  (1111 Characters|
|lines|_SVG_|Any SVG paths (1111 Characters)|
|image|directory/subdirectory/image.file|Image file associated with the quote (255 Characters)|
|audio|directory/subdirectory/audio.file|Audio file originated with the quote (255 Characters)|
|longitude|32.7820148|Longitude of user when post occurs|
|latitude|-96.8003555|Latitude of user when post occurs|
|altitude|150|Altitude of user when post occurs|
|author|83838383|User ID of the user authoring object|
|audience|33333333|User ID of the user who is audience to this object|

## Other requirements and key considerations

This is 1 of 4 React Natively mini projects that are meant to be stand alone apps that run on both iOS and Android. They may also be submitted to their respective mobile app stores - in some form - in the near future.

- iOS (Device preference: iPhone 6 and above)
- Android (OS: Latest OS or next the latest)
- React Native (v0.56+)
- React Native Navigation
- DO NOT USE Realm

What's expected is 4 separate, independent code bundles that successfully build Android and iOS binaries. All dependencies must be clearly identified.

# Conference App in a Box

This is the React Native CLI version. To view the Expo version, click [here](https://github.com/dabit3/conference-app-in-a-box/tree/expo).

> This repo goes along with my Dev.to post titled ["Introducing Conference App in a Box"](https://dev.to/dabit3/introducing-conference-app-in-a-box-kgj)

For a full walkthrough of this project and how to deploy and theme it, check out [this video](https://www.youtube.com/watch?v=9ysiXDdmc9c).

#### Deploy a full stack & cross-platform mobile app for your next event in minutes.

🛠 Built with React Native, GraphQL, AWS Amplify, & AWS AppSync

> Follow me on [Twitter at @dabit3](https://twitter.com/dabit3) to keep up with my future projects as well as updates and new features added to this one! If you need any help launching this app, please reach out to me I'd be happy to help.

### Features

⚡️ Real-time chat   
👾 Themeable & customizable   
👮‍♂️ Authentication & Profile view   
🔥 Serverless back end   
🚀 GraphQL   
💻 Deploy back end in minutes   

![](./src/assets/confapps1.jpg)
![](./src/assets/confapps2.jpg)
![](./src/assets/confapps3.jpg)

## Deploy the back end and run the app

1. Clone the repo & install the dependencies

```sh
~ git clone https://github.com/dabit3/conference-app-in-a-box.git

~ cd conference-app-in-a-box

~ npm install
```

2. Initialize and deploy the Amplify project

```sh
~ amplify init

? Enter a name for the environment: dev (or whatever you would like to call this env)
? Choose your default editor: <YOUR_EDITOR_OF_CHOICE>
? Do you want to use an AWS profile? Y

~ amplify push

? Are you sure you want to continue? Y
? Do you want to generate code for your newly created GraphQL API? N

> We already have the GraphQL code generated for this project, so generating it here is not necessary.
```

3. Start the app

```sh
~ react-native run-ios

# or

~ react-native run-android
```

## To populate the database with your conference speakers

1. Sign up in the app after following the previous steps

2. Open the AppSync console:

```sh
~ amplify console api
```

3. Click on __Queries__ to open the GraphiQL Editor. When prompted to "Login with User Pools", you can login with your new username and use the `aws_user_pools_web_client_id` located in __aws-exports.js__ for the ClientId.

4. Create a new talk with the following GraphQL mutation:

```graphql
mutation createTalk {
  createTalk(input: {
    name: "Performance In React Native",
    summary: "In this talk, we will look at the various tips and tricks for taking full advantage of React Native and using the performance attributes of the new architecture.",
    speakerName: "Ram Narasimhan",
    speakerBio: "Software Engineer at Facebook",
    time: "9:00 AM - 9:30 AM",
    timeStamp: "1573491600",
    date: "November 10",
    location: "Armory",
    speakerAvatar: "https://pbs.twimg.com/profile_images/875450414161772544/UjefWmmL_400x400.jpg"
  }) {
    id name speakerBio speakerName speakerAvatar location date time timeStamp
  }
}
```

5. Query for all talks with the following GraphQL query:

```graphql
query listTalks {
  listTalks {
    items {
      name
      summary
      speakerName
      speakerBio
      time
      timeStamp
      date
      location
      speakerAvatar
    }
  }
}
```

6. Update a talk with the following GraphQL mutation:

```graphql
mutation updateTalk {
  updateTalk(input: {
    id: "<TALK_ID>"
    name: "Performance in React Native & GraphQL"
  }) {
    id name
  }
}
```

7. Delete a talk with the following GraphQL mutation:

```graphql
mutation deleteTalk {
  deleteTalk(input: {
    id: "<TALK_ID>"
  }) {
    id
  }
}
```

## To customize with your theme and logo

1. Open __src/theme.js__ and replace the _highlight_ & _primary_ colors.

2. Replace __src/assets/logo.jpg__ with your logo.

## To customize the GraphQL schema

This schema can be edited. If your event needs additional fields, you can update the backend by doing the following:

1. Update the schema (located at __amplify/backend/api/rnconfinabox/schema.graphql__).

2. Redeploy the back end:

```sh
~ amplify push
```

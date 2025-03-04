# Salesforce Canvas Demo
0. Article Reference: https://www.codescience.com/blog/2021/mastering-salesforce-canvas-apps/

1. Click the button below to deploy this project to Salesforce

<a href="https://githubsfdeploy.herokuapp.com?owner=CodeScience&repo=canvas-demo&ref=main">
  <img alt="Deploy to Salesforce"
       src="https://raw.githubusercontent.com/afawcett/githubsfdeploy/master/deploy.png">
</a>

2. Deploy one of these canvas app samples to Heroku
  - [NodeJS Heroku Canvas App Sample](https://github.com/CodeScience/nodejs-canvas-app-sample)
  - [Java Spring Boot Canvas App Sample](https://github.com/CodeScience/java-heroku-canvas-demo)

3. Update the 3 connected apps with the domain of your recently deployed Heroku app. Go to Setup > App Manager > edit.
  - Replace the `https://cs-nodejs-canvas-demo.herokuapp.com` with your Heroku app domain.
  - Take note of the Consumer Key and Consumer Secret as you will need to update your Heroku app with the following environment variables:

* canvas_demo_signed_request: SIGNED_REQUEST_CONSUMER_SECRET
* canvas_demo_oauth_uaf: OAUTH_UAF_CONSUMER_KEY
* canvas_demo_oauth_wsf: OAUTH_WSF_CONSUMER_KEY, OAUTH_WSF_CONSUMER_SECRET and OAUTH_WSF_CALLBACK_URL

5. Navigate to your Salesforce org and create a Contact record. Copy the Contact Id from the URL and navigate to the canvas apps by using the following URL pattern. For example:

`https://<mydomain>--c.visualforce.com/apex/CanvasDemoWithSignedRequest?id=0030R00001K9dxbQAB`

`https://<mydomain>--c.visualforce.com/apex/CanvasDemoWithOAuthUAF?id=0030R00001K9dxbQAB`

`https://<mydomain>--c.visualforce.com/apex/CanvasDemoWithOAuthWSF?id=0030R00001K9dxbQAB`

Note: if you are using SFDX to login into Salesforce, you will get an "invalid session" error in your canvas apps. Make sure you login via UI (e.g. https://test.salesforce.com or https://login.salesforce.com)

6. A custom Canvas Lifecycle Handler has been added to support 2 additional canvas locations: 
* A "stand alone" Visualforce Realty App available at https://<mydomain>--c.visualforce.com/apex/RealtyApp
* A "stand alone" Aura Component Realty App available at https://<mydomain>.lightning.force.com/lightning/cmp/c__RealtyApp
* A "QR code component" available in the Contact Record Page
* A "Redirect Example" Aura Component is available at https://<mydomain>.lightning.force.com/lightning/cmp/c__redirectExample

Note that the latest support for these locations is only available in the NodeJS Sample App. So, only use the Java Sample App for basic demos.

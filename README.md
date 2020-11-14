# Ecommercer Backend 
## Template preparation 
### create the project 
```
 sls create --template aws-nodejs-typescript
```
### install dependencies 
```
npm install
```
### install serverless plugins (not used in this project)
```
npm i -D serverless-iam-roles-per-function serverless-create-global-dynamodb-table serverless-offline serverless-prune-plugin
```
### install aws-sdk and aws-lambda 
```
 npm i aws-sdk aws-lambda.
 ```
### Lambda Powertools
One thing I really struggled with when I stepped into the world of serverless was observability and traceability. Debugging across service boundaries and even infrastructure within boundaries (Lambda > SQS > Lambda > Kinesis > Lambda > DynamoDB, etc.) was a pain. Thankfully I came across a great set of powertools for Lambda that are a must-have in any service.

I just import all of these and let webpack tree shaking worry about getting rid of what I’m not using.

```
 npm i @dazn/lambda-powertools-cloudwatchevents-client @dazn/lambda-powertools-correlation-ids @dazn/lambda-powertools-logger @dazn/lambda-powertools-pattern-basic @dazn/lambda-powertools-lambda-client @dazn/lambda-powertools-sns-client @dazn/lambda-powertools-sqs-client @dazn/lambda-powertools-dynamodb-client @dazn/lambda-powertools-kinesis-client
 ```

### linting
The next important thing I can’t live without in a codebase is linting. ESLint is one of the biggest crutches I use everyday. Let’s configure it to work with TypeScript and the Serverless Framework. We’ll need the following dev dependencies.

```
 npm i -D eslint eslint-config-airbnb-base typescript-eslint eslint-plugin-import eslint-import-resolver-alias eslint-plugin-module-resolver @typescript-eslint/eslint-plugin @typescript-eslint/parser
 ```

### Testing 

I’ll write tests for every service so it makes sense to configure a test runner in our base template. I personally like Jest, so we’ll set that up.

Once again, we’ll need to fill the the black hole of our node_modules with some npm dev dependencies.

```
 npm i -D jest babel-jest @babel/core @babel/preset-env @babel/preset-typescript
```




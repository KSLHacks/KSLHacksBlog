---
title: "MeteorJS and Vulcan.js using Cosmos DB"
date: 2017-09-12
thumbnailImagePosition: left
thumbnailImage: /img/posts/5_thumbnail.png
coverImage: /img/posts/5_coverimage.png
coverMeta: in
coverSize: partial
coverHeight: 40
categories:
- tech
- front-end
tags:
- Javascript
- MeteorJS
- Vulcan.js
- Azure
- CosmosDB
- MongoDB

draft:          true
comments:       true
showTags:       true
showPagination: true
showSocial:     true
showDate:       true
---

Hooking up our MeteorJS app to use a MongoDB on Azure using CosmosDB!

<!--more-->
<!--
Notes:
ThumbnailImage dimensions: 700px x 700px
CoverImage dimensions: 1800px x 450px
-->

I haven't seen any guides or instructions to set up a MeteorJS app using a MongoDB backend hosted with Cosmos DB on Azure.. so I thought I would do that now just in case anyone else would like to try it out. Azure Cosmos DB is Microsoft's globally distributed database service which allows you to elastically scale up across multiple databases across multiple regions anywhere in the world. If you haven't checked out [Cosmos DB](https://docs.microsoft.com/en-us/azure/cosmos-db/introduction) yet, I highly encourage you to do so!

## Generic Node.js
Microsoft Azure docs currently have a walkthrough tutorial of: [Build a Node.js web application using Azure Cosmos DB](https://docs.microsoft.com/en-us/azure/cosmos-db/documentdb-nodejs-application).. but nothing specific to Meteor's application environment variable for setting the collection string.

## Setting up MeteorJS on Cosmos DB
### Step 1:
Create an Azure Cosmos DB service in the [Azure Portal](https://portal.azure.com) and be sure to select 'Mongo' under the API drop down options

![Create a Cosmos DB Azure Service](/img/posts/create-cosmosdb1.png)

![Create a Cosmos DB Azure Service Select Mongo API](/img/posts/create-cosmosdb2.png)

### Step 2:
Retrieve the CONNECTION STRING by navigating to the Cosmos DB service that was just created, and select 'Connection String' in the blade menu. We want the entire string copied including `?ssl=true`, this is important!

![Create a Cosmos DB Azure Service Select Mongo API](/img/posts/create-cosmosdb3.png)

### Step 4:
Navigate to local MongoJS application directory

### Step 5:
change connection string variable..

### Step 6:
Run...

## Running Vulcan.js (MeteorJS, React and GraphQL) on Cosmos DB
Follow steps to set up MeteorJS backend on Cosmos DB
Navigate to local Vulcan.js application directory
change connection string variable
Run...

Vulcan.js running on MeteorJS backend on Cosmos DB..

3t MongoChef tool to confirm
Can also check Cosmos DB and view data present
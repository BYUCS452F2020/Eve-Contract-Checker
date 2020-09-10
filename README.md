# Eve-Contract-Checker
Eve online is a MMO Game that has several API endpoints to retrieve game data. This program will use these API's to collect data about Bulk-Item contracts. This data will be used to find contracts from many different in-game regions and compare them to the cost of the individual items at two in-game trade-hubs. 

The goal of this program is to find bulk-item in-game contracts that are profitable to buy.

## Team
I have one person already signed up. I could consider having a third member if they wanted to join. 

## Relational Database
The project will use PostgreSQL with 4 tables to start (Items, ItemPrices, Regions, Contracts). Unless we decide more/less is needed

## NoSQL Database
We will also use a NoSQL document database; TBD

## Business
This will begin as an open source project for free use for whomever wants to use it for the Eve-Online Game

## Legal
We will have to obtain an open source license for our project to determine under which conditions our software can be used or modified.

## Technical
### Technologies being used
* Angular 9 Framework for the front-end
* Typescript for the front-end
* Java Backend 
* JAva Spark Server will probably be what we use for the backend framework
* Postgres for the SQL Database
* The no-sql Portion of this is completely optional. Google Firestore is an option, or DynamoDb, TBD

### major steps for this project
* Design and create the database tables and schemas (relational & NoSQL)
* Design and build a backend API to handle business logic of comparing and prioritizing contracts. This includes accounting for Taxes, Sell prices of individual items, Cost to buy all items in bulk
* Build a simple web client for a user to view the contract infomration and the amount of profit available. 

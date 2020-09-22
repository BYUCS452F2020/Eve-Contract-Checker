Region (id, name)
- Primary Key: id
 
- Name Explanation: This table holds all of the possible region ids and names
- Entity Type: Game-Region
- Relation to other Tables: It is referenced in the contract table. It will be used to make the information held in the contract table more readable
- Column name explanation:
  - id (integer)– The in-game unique integer id given to each region
  - name(String) – The in-game unique String name given to each region
---
Item (id, name)
- Primary Key: id
 
- Name Explanation: This tables holds all possible ingame items name and id
- Entity Type: Game-Item
- Relation to other Tables:
- Column name explanation:
  - Id (integer)– The in-game unique integer id given to each item
  - name (String)- The in-game unique String name given to each item
--- 
ItemPrice (id, jitaSellAmount, amarrSellAmount, jitaBuyAmount, amarrBuyAmount timestampOfLastUpdate) 
- Primary Key: id
- Foreign key id references the Item table
 
- Name Explanation: This table stores the price of each item in separate regions
- Entity Type: Game-Item Price
- Relation to other Tables:
- Column name explanation:
- Id (integer)– The in-game unique item integer id given to each item
  - jitaSellAmount (integer) – The individual sell value of this item in the jita trade hub based on Eve-praisal API call
  - amarrSellAmount (integer)- The individual sell value of this item in the amarr trade hub based on Eve-praisal API call
  - jitaBuyAmount(integer) - The individual buy value of this item in the jita tradehub based on Eve-praisal API call
  - amarrBuyAmount (integer)- The individual buy value of this item in the amarr tradehub based on Eve-praisal API call
  - timestampOfLastUpdate (integer)– The integer that represents the Timestamp of the last update to the item’s price
--- 
Contract(contractId, contractBuyPrice, regionId, jitaTotalSellAmount, amarrTotalSellAmount, jitaTotalBuyAmount, amarrTotalBuyAmount, timestampOfLastUpdate)
- Primary Key: contractId
- Foreign Key regionId references the Region table
 
- Name Explanation:  This table holds the basic data needed to model a contract
- Entity Type: Ingame-Contract
- Relation to other Tables:  This table holds the basic data needed to see if a contract will be profitable or not. Other tables' information is used to calculate the information stored within this table.
- Column name explanation:
  - contractId (integer)- The in-game unique contract id given to each contract
  - contractBuyPrice (integer)– The price to buy the contract set by the seller
  - regionId – The unique in-game integer id of the region where the contract is being sold
  - jitaTotalSellAmount (integer) – The total sell value of all items within the contract given by the eve-praisal api in the jita trade hub
  - amarrTotalSellAmount (integer)– The total sell value of all items within the contract given by the eve-praisal api in the amarr trade hub
  - jitaTotalBuyAmount (integer)– The total buy value of all items within the contract given by the eve-praisal api in the jita trade hub
  - amarrTotalBuyAmount (integer)– The total buy value of all items within the contract given by the eve-praisal api in the amarr trade hub
  - timestampOfLastUpdate (integer) – The timestamp of the last time the information in the contract were updated
---
ContractItems (contractId, itemId, quantity)
- Composite Primary Key : contractId + itemId
- Foreign Key contractId references the Contract table
- Foreign Key itemId references the ItemPrice table
 
- Name Explanation: This table holds the data about the items in each contract
- Entity Type: List-of-Items
- Relation to other Tables: This table stores which items and how many of those items are stored within each contract
- Column name explanation:
  - contractId (integer)– The unique in-game given integer id of the contract
  - itemId (integer) –  The unique in-game given integer id of the item
  - quantity  (integer)- The number of items of type itemID within the contract with the primary key of contractId

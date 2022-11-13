# Omni Take Home Interview

### Goal

Given this NFT collection on Goerli, use the [OpenSea Stream API](https://docs.opensea.io/reference/stream-api-overview) to write a program that listens to listing creations, listing cancellations and sales to calculate the floor price in ETH for the collection.

The output of the program should be a continuous log of price changes that includes the timestamp, the old floor price, the new floor price, and the reason for the change

```
$ <command> 
[11-11-2022 1:10:55PM] 1 ETH -> 1.1 ETH (New listing created)
[11-11-2022 1:10:58PM] 1.1 ETH -> 1.5 ETH (Previous floor listing cancelled)
[11-11-2022 1:11:05PM] 1.5 ETH -> 1.0 ETH (Previous floor listing sold)
```

### Instructions
1. Please fork this repository into your Github as a private repository and invite me (davidlee1435)
2. Commit your changes to your fork
3. Include instructions on how to initialize the repository, install any dependencies, and run the program.

### More information

**About NFTs**
An NFT collection is a smart contract that issues a finite number of tokens, each of which can be listed to sell for a fixed price. The floor listing is the lowest-priced listing that is available for purchase at time t, and the floor price of a collection is the price of such listing. Note that cancelled or previously sold listings do not affect the floor price of a collection at time T.

A listing is available for sale if:
1. The `is_private` is false
2. The `listing_type` is not null and not `dutch`
3. The listing's expiration time has not passed

**About the OpenSea Stream API**
The OpenSea Stream API is a Websocket-based API that emits events (including listing creations, listing cancellations, and sales) to listeners of the stream. You can read more about it [here](https://docs.opensea.io/reference/stream-api-overview). Note: you don't need an API key to use the Stream on testnet.

Here are some helpful things to note about the schema of events that are sent to listeners:

- The `base_price` is an integer with 18 points of precision (referred to commonly as a wad). A value of 1.5 ETH is therefore represented as 1.5e18

You are free to use any languages/technologies/frameworks that you would like to achieve this task. OpenSea does have a [Javascript client](https://github.com/ProjectOpenSea/stream-js) that you are free to use as well.

**Due Date**
The due date for this project is 1 week from when you were invited to the repo, but it should not take more than 8 hours of your time. After the due date, we will review the code and schedule a 30 minute chat to walk through your design decisions, tradeoffs, and how you would scale this.

If you have any questions, please do not hesitate to ask!

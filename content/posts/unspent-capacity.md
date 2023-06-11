---
author: Bitlevi
date: 2023-06-11
draft: false
Title: What is the unspent capacity in Whirlpool?
---
If you happen to follow [**Samourai Wallet**](https://twitter.com/SamouraiWallet) or [**TDevD**](https://twitter.com/SamouraiDev) on Twitter, you may have noticed their posts about "Unspent Capacity" and wondered what it meant. You may have also been curious as to why the Samourai Wallet cypherpunks seem so thrilled when this number increases (I certainly was).

![Alt Text](/static/images/unspent-capacity.png)

## Understanding Bitcoin Transactions

Bitcoin transactions are different from traditional bank transfers. They are based on a unique model known as Unspent Transaction Outputs, or UTXOs. Think of UTXOs as individual banknotes or coins: if you were to pay someone a certain amount, you wouldn't tear up a banknote to do so. Instead, you'd hand over the whole banknote and receive change. Similarly, when you send bitcoins, you assign your UTXO to a new address. The recipient gets one or more UTXOs that amount to the sum you wanted to send, and you get the "change" as a new UTXO.

It is important to be mindful of your privacy when conducting transactions. Understanding UTXO management is a crucial aspect that all network users should be familiar with. Samourai Wallet put together an excellent [**video series**](https://www.youtube.com/playlist?list=PLIBmWVGQhizLrPjpFMN5bQdbOZRxCQXUg) about the subject. 

## Enter Whirlpool

Whirlpool is a privacy-focused feature offered by Samourai Wallet. It is a CoinJoin implementation, which allows multiple users to combine their transactions into one large transaction with many inputs and outputs. By doing so, it obscures the trail of individual transactions, providing a higher degree of privacy and anonymity to its users. Whirlpool improves the **forward** anonymity of the users, past transactions are set in stone on the public ledger.

If you want to learn more about how to CoinJoin, QnA has a guide [**here**](https://bitcoiner.guide/whirlpool/).

## Unspent Capacity in Whirlpool

Within the context of Whirlpool, the term 'Unspent Capacity' refers to the total value of UTXOs that have already gone through the Whirlpool process. These UTXOs have been mixed, making them "identical-looking" and difficult to trace back to their original sender. 

When you hear "there are X BTC worth of identical-looking UTXOs," it means this amount of Bitcoin has been through the Whirlpool process and now exists in the form of these indistinguishable UTXOs. 

As Unspent Capacity increases, it means more transactions have been mixed and are in the form of these identical-looking UTXOs. This increase in Unspent Capacity improves privacy as it expands the pool of mixed transactions that any one transaction could potentially be a part of. The larger the crowd, the harder it is to isolate individual transactions, thereby enhancing privacy for all Whirlpool users.

## The Role of Unspent Capacity

While the 'Unspent Capacity' refers to UTXOs that have already been through the Whirlpool process, it doesn't imply that these UTXOs are waiting to be mixed with new ones. They've been mixed and are free to be spent as the owners see fit. However, owners could decide to keep these UTXOs unspent for further CoinJoin operations or future spending, which would further enhance their transactions and privacy. 

## Estimating Unspent Capacity

One may wonder how the Samourai Wallet can determine the amount of Bitcoin in the Unspent Capacity. The calculation hinges on the observation of outputs from Whirlpool's CoinJoin transactions.

Here's a simplified overview of the CoinJoin process:

1. Several users provide one or more UTXOs as inputs. These UTXOs can hold any value.
2. The transaction creates numerous outputs of fixed denominations. Each of these outputs, now new UTXOs, appear identical, making it nearly impossible to discern which input they originated from.
3. Any remaining bitcoin is returned to the users as 'change'. These 'change UTXOs' are separate from the main outputs and could potentially be traced back to the original inputs.

As the coordinator of these transactions, the Whirlpool service is privy to the transaction details. **It sees how many fixed-denomination outputs have been created and which haven't been spent yet, by observing them on the blockchain**. By summing the value of these 'identical looking' UTXOs, it can calculate the Unspent Capacity.

However, it's essential to note that this doesn't mean Samourai Wallet has any special ability to trace transactions or breach user privacy. All of this information is publicly available on the blockchain; Samourai merely interprets it to estimate the Unspent Capacity. The Unspent Capacity only includes the mixed outputs; it doesn't count the change UTXOs, which aren't part of the anonymity set.

This estimation can be calculated for the entire Whirlpool service or segregated by pool size, i.e., the fixed output denomination. When we talk about Unspent Capacity being 'split across different pool sizes,' we refer to the varying fixed denominations used in Whirlpool CoinJoin transactions. 

## Conclusion

Whirlpool's approach to privacy is designed to enhance the anonymity of Bitcoin transactions, making it an essential tool for anyone serious about maintaining their privacy in the Bitcoin space. By enhancing privacy, the service is contributing to the ongoing evolution and maturation of Bitcoin as a truly decentralized and private peer-to-peer electronic cash system.
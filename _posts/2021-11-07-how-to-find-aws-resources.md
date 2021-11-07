---
title:  "How to find previously created resources in AWS"
date:   2021-11-07 18:30:00 -0300
categories: blog
---
### How to find previously created resources in AWS

It probably happens a lot to some of you: you get to work on a previously created AWS account and you don't have any information about the resources created in it, or which region(s) they've been created in. You start to guess a bunch of common services on a bunch of regions.

At some point you find one service being used in one region or another, but you're never 100% sure if these are all the services created in that account, or if there's something else configured/created somewhere that you haven't looked at.

Turns out, there's at least 2 ways to find these services, one of them only applies if you have access to the billing information of that account. By going into [Billing](https://console.aws.amazon.com/billing/home?region=us-west-2), and then "Bills", you are able to browse all used services per month, even the ones that are under the free tier, they all display region information, so it's a very handy way to find all of them.

If, on the other hand, your account doesn't have access to that, I've just discovered another easy way to find these hidden services. Basically, there's a service called "[Resource Groups & Tag Editor](https://us-east-2.console.aws.amazon.com/resource-groups/home?region=us-east-2)" that helps you add tags to multiple services at the same time, but also allows you to search for services in your account throughout all regions.

To access this, you have to navigate to "Tag Editor" menu, here you'll find a "Find resources to tag" section, where you can define the regions and the resources types to look for, defining "All regions" and "All supported resource types" allows you to search your entire account for any services that have been created.

Depending on how many services you have created in the account, it may take a while to process, one account that I was working with the other day had 250 services created and it took around 5 minutes to find them all. Having worked on dozens of accounts in the past few years, I can't count how many times this would've saved me a considerable amount of time trying to figure out where the heck the application resources had been created, so I hope that this article helps someone else in the same boat.

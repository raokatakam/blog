---
title: "The Ultimate Guide to Serverless Announcements @ AWS re:Invent 2017"
description: "Your go-to resource for all Serverless announcements at AWS re:Invent."
date: 2017-11-27
layout: Post
thumbnail: 'https://s3-us-west-2.amazonaws.com/assets.blog.serverless.com/awsreinvent.jpg'
authors:
  - AlexDeBrie
---

**Last Updated:** 11/29/17 @ 8:47AM PST

It's that time of the year, the Christmas-comes-early for cloud developers. Are you ready for [AWS re:Invent](https://reinvent.awsevents.com/)?

This is where [AWS Lambda was introduced in 2014](https://www.youtube.com/watch?v=9eHoyUVo-yg), and we're expecting more huge announcements in the serverless realm this year. AWS has gone all-in on serverless, and we can't wait to see the improvements they're making.

This post is _the_ place to understand what is announced and why it affects you, the intrepid Serverless developer. We'll be updating throughout the week with all of the latest announcements.

If you're attending re:Invent, be sure to [check out the Serverless guide to re:Invent 2017](https://serverless.com/blog/serverless-guide-aws-reinvent-2017/).

# Overview:

### re:Invent announcements (newest to oldest):

- [AWS Fargate](#aws-fargate)
- [AWS EKS (Kubernetes-as-a-service)](#aws-eks)
- [AWS AppSync](#aws-appsync)
- [Weighted aliases for Lambda](#weighted-alises-for-lambda)
- [AWS CodeDeploy incremental deployment](#aws-codedeploy-incremental-deployment)
- [Canary management for API Gateway](#canary-management-for-api-gateway)
- [Serverless Aurora coming soon](#serverless-aurora-coming-soon)

### Pre-re:Invent announcements:

- [Lambda@Edge Improvements](#lambda-at-edge-improvements)
- [SNS Message Filtering](#sns-message-filtering)
- [API Gateway Access Logs](#api-gateway-access-logs)

# Announcements:

# AWS Fargate

**What:** Run your containers directly without a cluster. Just pay for your compute resources.

**Why this matters:** This drastically lowers the barrier for running containers. You don't need to set up and maintain a cluster for deploying your containers. It's not serverless -- you're still paying for resources even when they're not actively serving requests -- but it does have some of the similar benefits of serverless architectures.

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">No longer any need to manage servers and clusters for your containers - AWS Fargate - Run ECS and EKS without managing servers <a href="https://twitter.com/hashtag/reInvent?src=hash&amp;ref_src=twsrc%5Etfw">#reInvent</a> <a href="https://t.co/oPsXdvrSAL">https://t.co/oPsXdvrSAL</a> <a href="https://t.co/lZnS558CXV">pic.twitter.com/lZnS558CXV</a></p>&mdash; AWS re:Invent (@AWSreInvent) <a href="https://twitter.com/AWSreInvent/status/935910336212844544?ref_src=twsrc%5Etfw">November 29, 2017</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

# AWS EKS

**What:** Managed Kubernetes on AWS.

**Why this matters:** AWS will run your Kubernetes for you. It's not a serverless solution by any means, but many companies are interested in containers over straight serverless. For running functions-as-a-service on Kubernetes, check out the [Kubeless integration with the Serverless Framework](https://serverless.com/blog/serverless-and-kubernetes-via-kubeless/). 

# [AWS AppSync](https://aws.amazon.com/blogs/aws/introducing-amazon-appsync/)

**What:** A platform for building data-rich apps with offline functionality.

**Why this matters:** This is an interesting, ambitious offering from AWS. Basically, it lets you set up a managed GraphQL endpoint over a variety of data sources. This endpoint can proxy to DynamoDB, ElasticSearch, or your custom Lambda functions. Further, it provides some nice functionality to keep your device synced when moving between online and offline modes. 

I'd compare this to an AWS version of Firebase or Realm with the ability to have multiple different backing data sources. That's pretty powerful. One of the drawbacks to Firebase stems from the limitations of its data model. This offering sidesteps those issues.

The product page is live at [https://aws.amazon.com/appsync/](https://aws.amazon.com/appsync) and you can find docs [here](https://docs.aws.amazon.com/appsync/latest/devguide/welcome.html).

<p><blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">We’re launching 🚀 AWS AppSync as a new service for preview later today! Here are some of its features! <a href="https://twitter.com/apatel72001?ref_src=twsrc%5Etfw">@apatel72001</a> <a href="https://twitter.com/hashtag/reInvent?src=hash&amp;ref_src=twsrc%5Etfw">#reInvent</a> <a href="https://t.co/fG9thG6sAa">pic.twitter.com/fG9thG6sAa</a></p>&mdash; AWS re:Invent (@AWSreInvent) <a href="https://twitter.com/AWSreInvent/status/935573868260896768?ref_src=twsrc%5Etfw">November 28, 2017</a></blockquote></p>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

*credit: [AWSreInvent](https://twitter.com/AWSreInvent) main account.

# [Weighted aliases for Lambda](https://aws.amazon.com/about-aws/whats-new/2017/11/aws-lambda-supports-traffic-shifting-and-phased-deployments-with-aws-codedeploy/)

**What:** This will let you send some percentage of traffic to one version of a Lambda, the rest to another version. This is GA today, try it out!

**Why this matters:** This will make it easier to confidently push new changes to production.  When you push new versions, you can shift a small percentage of users to the new version and monitor for errors, performance metrics, etc. If you're happy with the results, you can gradually ramp up traffic so that all users see the new version. 

# [AWS CodeDeploy incremental deployment](https://aws.amazon.com/about-aws/whats-new/2017/11/aws-lambda-supports-traffic-shifting-and-phased-deployments-with-aws-codedeploy/)

**What:** CodeDeploy support for incremental deployment of serverless applications. This is GA today, try it out!

**Why this matters:** This update fits well with the addition of [weighted aliases for Lambda](#weighted-aliases-for-lambda). In your CodeDeploy configuration, you can use phased rollouts of your applications. [For example](http://docs.aws.amazon.com/codedeploy/latest/userguide/deployment-configurations-create.html), you could have CodeDeploy make a deploy to 25% of your production traffic at first, then roll it out to the remaining 75% 45 minutes later. If you discover problems during that 45 minutes, you can rollback the deploy to limit problems to your users.

<p><blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">New features coming to lambda <a href="https://twitter.com/hashtag/breaking?src=hash&amp;ref_src=twsrc%5Etfw">#breaking</a> <a href="https://twitter.com/hashtag/serverless?src=hash&amp;ref_src=twsrc%5Etfw">#serverless</a> <a href="https://twitter.com/hashtag/reinvent?src=hash&amp;ref_src=twsrc%5Etfw">#reinvent</a> .cc <a href="https://twitter.com/Ninnir?ref_src=twsrc%5Etfw">@Ninnir</a> <a href="https://t.co/bNjL0I78ZU">pic.twitter.com/bNjL0I78ZU</a></p>&mdash; Julien Stanojevic (@GenuineM7) <a href="https://twitter.com/GenuineM7/status/935596271020130304?ref_src=twsrc%5Etfw">November 28, 2017</a></blockquote></p>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

*credit: [@GenuineM7](https://twitter.com/GenuineM7)

# [Canary management for API Gateway](https://aws.amazon.com/about-aws/whats-new/2017/11/amazon-api-gateway-supports-canary-release-deployments/)

**What:** This will allow you to send some percentage of API Gateway traffic to one source and the rest to another. This is GA today, try it out!

**Why this matters:** Same benefits as the [weighted aliases for Lambda](#weighted-aliases-for-lambda) above -- more fine-grained rollouts of new code to production. This change is at the API Gateway level, rather than for an individual Lambda function. [Canary deployments](https://martinfowler.com/bliki/CanaryRelease.html) are a way to safely roll out new changes to customers.

# [Serverless Aurora coming soon](https://twitter.com/sandy_carter/status/935550646995927040)

**What:** Aurora is AWS's relational database in the cloud. It's cheaper and faster than MySQL or PostgreSQL databases.

**Why this matters:** If done right, this is a dream come true. The data layer is an unsolved problem in the Serverless realm. If you want to use a traditional relational database, you're configuring a lot of network rules and VPC configuration -- just what you want to avoid with serverless architectures. You can avoid this pain by using DynamoDB, but the limited query patterns & hidden foot-guns can cause problems down the road.

Serverless Aurora could change all of that—a relational database that's accessible over HTTP, doesn't require complicated networking configuration, and uses IAM for authentication? Count me in.

<p><blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Serverless and micro-services are where it’s at!! <a href="https://twitter.com/hashtag/reinvent?src=hash&amp;ref_src=twsrc%5Etfw">#reinvent</a> <a href="https://twitter.com/hashtag/cloud?src=hash&amp;ref_src=twsrc%5Etfw">#cloud</a> <a href="https://twitter.com/hashtag/soa?src=hash&amp;ref_src=twsrc%5Etfw">#soa</a> <a href="https://twitter.com/hashtag/Microservices?src=hash&amp;ref_src=twsrc%5Etfw">#Microservices</a> <a href="https://t.co/pSyCUK4ENZ">pic.twitter.com/pSyCUK4ENZ</a></p>&mdash; sandy carter (@sandy_carter) <a href="https://twitter.com/sandy_carter/status/935550646995927040?ref_src=twsrc%5Etfw">November 28, 2017</a></blockquote></p>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

*credit: [@sandy_carter](https://twitter.com/sandy_carter) for the tweet about this news

# [Lambda at Edge Improvements](https://aws.amazon.com/about-aws/whats-new/2017/11/lambda-at-edge-now-supports-content-based-dynamic-origin-selection-network-calls-from-viewer-events-and-advanced-response-generation/)

**What:** Lambda@Edge increased memory limits, maximum package size, and function durations. It also allows for dynamic origin selection based on content and the ability to make remote calls in viewer-facing requests.

**Why this matters:** This is a big one. Previously, Lambda@Edge functions allowed you to run limited logic at the edge, such as rewriting headers or redirecting unauthenticated users to a login page. However, the functionality was limited, particularly if you wanted to integrate with other services in your architecture.

Now, you can run entire applications at the edge. You can make remote calls to your other services to get dynamic content. You can route requests to different origins based on the request path, making it easier to slowly [migrate to Serverless architectures using the strangler pattern](https://medium.com/@rmmeans/serverless-strangler-pattern-on-aws-31c88191268d). This is a huge deal. It's mind-blowing that this came out _before_ re:Invent—they must have some other amazing announcements in store.

# [SNS Message Filtering](https://aws.amazon.com/about-aws/whats-new/2017/11/amazon-simple-notification-service-sns-introduces-message-filtering/)

**What:** SNS Subscriptions can add a filter policy where they only receive certain messages rather than all messages published to a topic.

**Why this matters:** This announcement may be underrated, but it makes it much easier to build pub/sub architectures. Previously, you might make a "fat" topic with all messages published to it and required annoying filtering logic within your Lambda functions that subscribed to a topic. This would result in wasted Lambda invocations to SNS messages that your function didn't care about. Alternatively, you could create multiple, smaller topics with specific messages types, but that required the complexity of multiple subscriptions for different Lambdas.

With this new filter policy, you can use the fat topic pattern while only invoking your function for messages it cares about. This could be based on an `event_type` (e.g., I care about `order_placed` but not `order_shipped`) or other attributes (if a new User is created, trigger me when the `user_type` is `admin`). This can simplify your Lambda logic and lower your costs.

# [API Gateway Access Logs](https://aws.amazon.com/about-aws/whats-new/2017/11/amazon-api-gateway-supports-access-logging/)

**What:** You can now enable detailed access logs from API Gateway, just like you could do with Apache, Nginx, or HAProxy.

**Why this matters:** This enables granular analytics on your web requests. You can feed these into your analytics systems or dump them into S3 to analyze with [Athena](https://aws.amazon.com/athena/).

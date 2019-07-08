---
# Page settings
layout: default
keywords:
comments: false

# Hero section
title: How to Publish a Streaming Service
description: Learn how to wrap your streaming AI service and make it available worldwide through SingularityNET

# extralink box
extralink:
    title: All Docs
    title_url: '/docs'
    external_url: false
    description: Find an overview of our full documentation here.

# Developer Newsletter
dev_news: true

# Micro navigation
micro_nav: true

# Page navigation
page_nav:
    prev:
        content: Back to tutorials
        url: '/tutorials'
    next:
        content: View all docs
        url: '/docs'
---

> This tutorial will guide you through the steps required to have a streaming service registered onto the SingularityNET. It assumes you have successfully installed all of SingularityNET components. To do that, refer to previous tutorials or simply run a docker container from the [Dockerfile](./Dockerfile) provided. If you choose to run a Docker container, make sure to expose a port so that SNET Daemon can communicate with the blockchain.

SingularityNET is an open-source protocol and collection of smart contracts for a decentralized market of coordinated AI services. Within this framework, anyone can add an AI/machine learning service to SingularityNET for use by the network and receive network payment tokens in exchange.

As an AI/machine learning service developer, you can expose your service to the SingularityNET by running an instance of SNET Daemon alongside it. The Daemon interacts with the blockchain to facilitate authorization and payment for services and acts as a pass-through for making API calls to the service.  

This tutorial will guide you through integrating streaming services that receive their input from SNET Daemon.

The main steps of this tutorial are:

1. [Write the code for your service](#step-1-writing-the-code-for-your-service) taking and returning well-defined stream data; 
2. [Publish it as an SNET service](#step-2-publishing-the-service-onto-singularitynet):
    1. [Specify the service model (protobuf file)](#step-21-specifying-the-service-model)
    2. [Create the service metadata](#step-22-create-the-service-metadata)
    3. [Publish the service under your organization](#step-23-publish-the-service-under-your-organization)
    4. [Running SNET Daemon](#step-24-running-snet-daemon)    
3. [Call the service](#step-3-calling-your-service).


## Step 1) Writing the code for your service

For this tutorial we'll write an example streaming service in [Go](https://www.golang.org/) but this approach can be applied to other programming languages as well.

To keep the directory structure of the services and follow the standard file paths, we'll create the following directories: 

```sh
mkdir -p streaming-service/service/service_spec && \
cd streaming-service/service
```

Inside the service folder, create a file for the main code of your service (in our case, `server.go`). For demonstration purposes, we'll create a very simple service. 

To test this code locally, run `./service/server.go` and in other tab `./service/client.go` 


## Step 2) Publishing the service onto SingularityNET

### Step 2.1) Specifying the service model

### Step 2.2) Create the service metadata

### Step 2.3) Publish the service under your organization

### Step 2.4) Running SNET Daemon

To run your service, you simply need to run an instance of SNET Daemon at the specified endpoint. It will listen to client calls at the blockchain and execute your service at the specified path using the client parameters. SNET Daemon takes a configuration file that specifies which network it should listen to (e.g. Kovan Testnet), where to redirect calls to, etc. (refer to [SNET Daemon's Github Repository](https://github.com/singnet/snet-daemon) for the complete list of parameters).

You're now able to keep an instance of SNET Daemon running at your service directory to keep it available: 

```sh
snetd serve .
```

## Step 3) Calling your service

That's it! You should now have a working process-type service published onto SingularityNET!

## Overview
TheApronNetworkis a decentralized infrastructure based on the Web 3.0ecosystem, in which tens of thousands of service providers provide node services to businesses and individuals, whiletheApronNetworkalso supports smart contracts that allow flexible extension of functionality through contracts, not limited to low-level chain development. This document will tell you what contracts are available in Apron and how to deploy them.

Contract Repo: [https://github.com/Apron-Network/apron-contracts](https://github.com/Apron-Network/apron-contracts)   
Contract Repo: [https://github.com/Apron-Network/apron-node](https://github.com/Apron-Network/apron-node)   

The demo contains apron node, apron gateway and contracts. The Apron Node is built with Substrate Framework with contracts and OCW enable. The Apron Gateway is buit with Golang, provides dedicated functions for the Apron Network to collect the usage of each service and put the statistics data on chain.

![](./demo-img/Demo-Structure.jpeg)

## Docker

You can use built image. We also provide docker file to build docker image from scratch and docker compose file to run the demo.

### Use Built Image

#### Download Docker Image
Please download the latest from here:

`https://drive.google.com/drive/folders/1W9X3BAYs9mU2VuBsnPd2axxRtPkXS9co?usp=sharing`

#### Load Docker Image

```
docker load < apron-node-2021xxxx.tar.gz
```

#### Download docker-compose Configuration 

`https://github.com/Apron-Network/apron-node/blob/master/scripts/docker-compose.yml`

#### Start Apron

```
docker-compose up -d
```

#### Connect Apron Node
Polkadot JS Apps is integrated into Docker image. Access the frontend from here http://localhost:3001/.

**OR**

You can clone the Apron Node repo by run `git clone https://github.com/Apron-Network/apron-node.git`.

And switch to the `script` folder.
```
cd apron-node/script
docker-compose up -d
```

### Docker Image from scratch

#### Build Docker Image
You can build docker image directly.
```
cd apron-node/script
docker build -t apron-node .
```

#### Start Apron
```
docker-compose up -d
```

#### Connect Apron Node
Polkadot JS Apps is integrated into Docker image. Access the frontend from here http://localhost:3001/.


## Contract
### Services Market

The Services Market is responsible for the registration of the Apron node Services. All Services are registered in the service marketplace, which records service names, logos, service providers, service warranties, service prices, and declarations. For display services, and then for business or personal search services, asking prices,and other scenarios.

### Services Statistic

Billing and Statistics is a core function for all service providers and consumers, and Services Statistics records the availability and usage of Services over a period of time, this includes information about the service provider, user key, price plan used, usage, cost, and so on.

### Deployment Contract

After you upload the contract, you can instantiate the contract on the chain. In substrate, you need to perform the contract’s initialization function, usually new or the default function.

## Use Contract

### Services Market Module

The Services Market is the Apron that registers the node service, provides the service registration and the query, the following figure is the registration of a new node service.

![](./demo-img/image-5.png)

All registered services can be queried through listService.

![](./demo-img/image-7.png)


### Services Statistics Module

Services Statistics records the availability and usage of a service over a period of time, and can submit the service usage provided by the service provider to a peer-to-peer contract. Note that only the service registrant using the same account can submit the service usage.

![](./demo-img/image-6.png)




---
title: Retrieve the current POP IP list for Azure CDN| Microsoft Docs
description: Learn how to get POP servers by using the REST API. POP servers make requests to origin servers associated with Azure Content Delivery Network endpoints.
services: cdn
documentationcenter: ''
author: duongau
manager: danielgi
editor: ''

ms.assetid: 
ms.service: azure-cdn
ms.workload: tbd
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 07/06/2021
ms.author: duau
ms.custom: 

---
# Retrieve the current POP IP list for Azure CDN

## Retrieve the current Verizon POP IP list for Azure CDN

You can use the REST API to retrieve the set of IPs for Verizon’s point of presence (POP) servers. These POP servers  make requests to origin servers that are associated with Azure Content Delivery Network (CDN) endpoints on a Verizon profile (**Azure CDN Standard from Verizon** or **Azure CDN Premium from Verizon**). Note that this set of IPs is different from the IPs that a client would see when making requests to the POPs. 

For the syntax of the REST API operation for retrieving the POP list, see [Edge Nodes - List](/rest/api/cdn/edge-nodes/list).

## Retrieve the current Microsoft POP IP list for Azure CDN

To lock down your application to accept traffic only from Azure CDN from Microsoft, you will need to set up IP ACLs for your backend. You may also restrict the set of accepted values for the header 'X-Forwarded-Host' sent by Azure CDN from Microsoft. These steps are detailed out as below:

Configure IP ACLing for your backends to accept traffic from Azure CDN from Microsoft's backend IP address space and Azure's infrastructure services only. 

Use the AzureFrontDoor.Backend [service tag](../virtual-network/service-tags-overview.md) with Azure CDN from Microsoft to configure Microsoft's backend IP ranges. For a complete list, see [IP Ranges and Service tags](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for Microsoft services.

## Typical use case

For security purposes, you can use this IP list to enforce that requests to your origin server are made only from a valid Verizon POP. For example, if someone discovered the hostname or IP address for a CDN endpoint's origin server, one could make requests directly to the origin server, therefore bypassing the scaling and security capabilities provided by Azure CDN. By setting the IPs in the returned list as the only allowed IPs on an origin server, this scenario can be prevented. To ensure that you have the latest POP list, retrieve it at least once a day. 

## Next steps

For information about the REST API, see [Azure CDN REST API](/rest/api/cdn/).

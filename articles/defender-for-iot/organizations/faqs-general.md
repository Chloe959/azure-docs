---
title: General FAQs - Microsoft Defender for IoT
description: Find answers to the most frequently asked questions about Microsoft Defender for IoT features and service.
ms.topic: conceptual
ms.date: 07/07/2022
---

# Microsoft Defender for IoT frequently asked questions

This article provides a list of frequently asked questions and answers about Defender for IoT.

## What is Azure's unique value proposition for IoT security?

Defender for IoT enables enterprises to extend their existing cyber security view to their entire IoT solution. Azure provides an end to end view of your business solution, enabling you to take business-related actions and decisions based on your enterprise security posture and collected data. Combined security using Azure IoT, Azure IoT Edge, and Microsoft Defender for Cloud enable you to create the solution you want with the security you need.

## How does Defender for IoT compare to the competition?

Microsoft Defender for IoT delivers comprehensive security across all your IoT/OT devices. For **end-user organizations**, Microsoft Defender for IoT offers agentless, network-layer security that is rapidly deployed, works with diverse proprietary OT equipment and legacy Windows systems, and interoperates with Microsoft Sentinel and other SOC tools. It can be deployed on-premises or in Azure-connected environments. For **IoT device builders**, Microsoft Defender for IoT offers lightweight agents to embed device-layer security into new IoT/OT initiatives.

## Do I have to be an Azure customer?

No, for the agentless version of Microsoft Defender for IoT, you do not need to be an Azure customer. However, if you want to send alerts to Microsoft Sentinel; provision network sensors and monitor their health from the cloud; and benefit from automatic software and threat intelligence updates, you will need to connect the sensor to Azure and Defender for IoT. For more information, see [Sensor connection methods](architecture-connections.md).

For the agent-based version of Microsoft Defender for IoT, you must be an Azure customer.

## What happens when the internet connection stops working?

The sensors and agents continue to run and store data as long as the device is running. Data is stored in the security message cache according to size configuration. When the device regains connectivity, security messages resume sending.

## Next steps

To learn more about how to get started with Defender for IoT, see the following articles:

- Read the Defender for IoT [overview](overview.md)
- [Get started with Defender for IoT](getting-started.md)
- [OT Networks frequently asked questions](faqs-ot.md)
- [Enterprise IoT networks frequently asked questions](faqs-eiot.md)
---
title: Connect Commerce Data to Adobe Experience Platform
description: Learn how to connect your Commerce data to the Adobe Experience Platform.
exl-id: 87898283-545c-4324-b1ab-eec5e26a303a
---
# Connect Commerce data to Adobe Experience Platform {#connectaep}

Before you connect your Adobe Commerce data to the Adobe Experience Platform, you must sign in to your Adobe account in the [Commerce Services Connector](../landing/saas.md#organizationid). After you sign in and select your organization ID, you can then specify the scope and datastream ID on the **Experience Platform Connector** page in the Admin.

![Experience Platform connector configuration](assets/epc-config.png)

1. In the Admin, go to **System** > Services > **Experience Platform Connector**.

1. In the **Scope** drop-down, select the context, or “scope” of the store view.

   The IMS Org ID is global. Only one IMS Org ID can be associated per Adobe Commerce instance.

1. In the **IMS Org ID** field, you see the ID associated with your Adobe Experience Platform account, as configured in the [Commerce Services Connector](../landing/saas.md#organizationid).

1. In the **Datastream ID** field, paste the ID of the datastream you [created](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) in Adobe Experience Platform.

## Relationship of Datastream ID and your Commerce Instance Storeview

The Datastream ID enables event forwarding from Adobe Experience Platform to other Adobe DX products and can be associated to a specific store view within your specific Adobe Commerce instance. You can also associate multiple store views to the same Datastream ID. It depends on what makes the most sense for your business. [Learn more](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=en#event-forwarding-settings) about event forwarding.

## Field descriptions

| Field | Description |
|--- |--- |
| Scope | Specific store view where you want the configuration settings to apply. |
| IMS Org (Global)| ID that belongs to the organization that purchased the Adobe DX product. This ID links your Adobe Commerce instance to Adobe Experience Platform. |
| Datastream ID (Store view) | ID that allows data to flow from Adobe Experience Platform to other Adobe DX products. This ID can be associated to a specific storeView within your specific Adobe Commerce instance. |

With the Experience Platform connector extension installed, the link between Adobe Commerce and Adobe Experience Platform created, and the Datastream ID specified, Commerce data begins to flow to the Adobe Experience Platform edge and to other Adobe DX products.

## Commerce data at the edge

When Commerce data is sent to the Adobe Experience Platform edge, you can build reports like the following:

![Commerce Data in Adobe Experience Manager](assets/aem-data-1.png)
_Commerce Data in Adobe Experience Manager_

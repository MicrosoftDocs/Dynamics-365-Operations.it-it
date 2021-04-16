---
title: Panoramica dei canali
description: Questo argomento fornisce una panoramica dei canali di Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 7f5d527dd14d24c06aef874de0088bb07c49849b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800545"
---
# <a name="channels-overview"></a>Panoramica dei canali


[!include [banner](includes/banner.md)]

Questo argomento fornisce una panoramica dei canali di Microsoft Dynamics 365 Commerce. Sono riportate informazioni sulle attività da completare prima e dopo la configurazione di ciascun canale.

## <a name="types-of-channels"></a>Tipi di canali

Dynamics 365 Commerce supporta tre diversi tipi di canali: vendita al dettaglio, servizio clienti e online.

### <a name="retail-channels"></a>Canali di vendita al dettaglio

I canali di vendita al dettaglio rappresentano i punti vendita fisici. Ogni punto vendita può disporre dei propri registratori di cassa POS, conti ricavi/spese e personale. 

### <a name="call-center-channels"></a>Canale servizio clienti

I canali servizio clienti rappresentano la gestione degli ordini e dei clienti del servizio clienti.

### <a name="online-channels"></a>Canale online

I canali online rappresentano i punti vendita di e-commerce online. Dopo la creazione di un canale online, è necessario creare un sito utilizzando lo strumento Creazione di siti Web di Microsoft Dynamics 365 Commerce o un'altra soluzione di e-commerce di terze parti.

## <a name="channel-setup-basics"></a>Nozioni di base sull'impostazione dei canali

L'impostazione dei canali viene eseguita nello strumento Commerce. Ogni canale può avere i propri metodi di pagamento, gruppi di prezzi, gerarchie di prodotti, assortimenti e set di prodotti. Dopo aver creato un canale, assegnare i prodotti che il canale deve presentare e vendere. Ogni tipo di canale ha un set univoco di funzionalità che potrebbero dover essere configurate. Ad esempio, un canale di vendita al dettaglio necessita di registratori di cassa, clienti e dipendenti assegnati. Una volta creato un nuovo canale, deve essere assegnato a una gerarchia organizzativa.

## <a name="channel-setup-prerequisites"></a>Prerequisiti di impostazione dei canali

Prima di poter impostare un canale, è necessario completare alcune attività preliminari in base al tipo di canale. Per ulteriori informazioni, vedere [Prerequisiti di impostazione dei canali](channels-prerequisites.md).

## <a name="set-up-a-channel"></a>Impostare un canale

Dopo aver completato le attività preliminari, per ulteriori istruzioni sull'impostazione, utilizzare i seguenti collegamenti.

- [Impostare un canale di vendita al dettaglio](channel-setup-retail.md)
- [Impostare un canale servizio clienti](channel-setup-callcenter.md)
- [Impostare un canale online](channel-setup-online.md)

<!--
## Post-channel configuration

After you create a channel, you may need to complete some of the below tasks:

- [Add channel to an organizational hierarchy](add-channel-org-hierarchy.md)
- Set up fulfillment groups. (LINK TBD)
- Configure the POS registers for the store. (LINK TBD)
- Assign product assortments to the store. (LINK TBD)
- Process assortments to generate the list of products that are included in the assortment and to make the products available in the retail store. (LINK TBD)
- Send data such as number sequences, hardware profiles, and POS screen layouts to the Retail POS registers.(LINK TBD)
- Publish the retail store to send store data to Retail POS. (LINK TBD)
- Run the jobs to send the store data to Retail POS. (LINK TBD)
-->

## <a name="additional-resources"></a>Risorse aggiuntive

[Prerequisiti di impostazione dei canali](channels-prerequisites.md)

[Impostare un canale di vendita al dettaglio](channel-setup-retail.md)
    
[Impostare un canale online](channel-setup-online.md)

[Impostare un canale servizio clienti](channel-setup-callcenter.md)

[Impostare gerarchie organizzative](channels-org-hierarchies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
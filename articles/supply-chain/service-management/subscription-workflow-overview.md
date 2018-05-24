---
title: Informazioni generali sul flusso di lavoro delle sottoscrizioni
description: In questo argomento viene fornita una panoramica del flusso di lavoro delle sottoscrizioni.
author: YuyuScheller
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMASubscriptionGroup, SMASubscriptionCreateDialog
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: b4872c0753b54bdddf2c7778a13819726eea4a90
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---


# <a name="subscription-workflow-overview"></a>Informazioni generali sul flusso di lavoro delle sottoscrizioni 

[!include [banner](../includes/banner.md)]


Si supponga di essere l'amministratore delle sottoscrizioni di una società elettrica che offre sottoscrizioni per la manutenzione di linee elettriche. Un cliente si rivolge alla società per richiedere una sottoscrizione annuale.

## <a name="setting-up-subscriptions"></a>Impostazione di sottoscrizioni

Per impostare una sottoscrizione, è innanzitutto necessario creare un gruppo di sottoscrizioni per il nuovo contratto di assistenza o verificare l'esistenza di tale gruppo. Se il gruppo di sottoscrizioni è disponibile, è necessario impostarlo in modo che sia possibile eseguire una fatturazione annuale al cliente e accumulare i ricavi da vendite ogni mese dell'anno. Per ulteriori informazioni su come impostare sottoscrizioni, vedere [Impostare gruppi di sottoscrizioni](set-up-subscription-groups.md).

Dopo la creazione del gruppo è possibile creare la sottoscrizione. Per ulteriori informazioni sulla creazione di sottoscrizioni di assistenza, vedere [Creare sottoscrizioni dell'assistenza da un gruppo di sottoscrizioni](create-service-subscriptions-from-subscription-group.md).

## <a name="create-and-modify-subscription-transactions"></a>Creare e modificare transazioni di sottoscrizione

Dopo l'impostazione della sottoscrizione, si crea una transazione di commissione di sottoscrizione per il primo periodo di fatturazione, ovvero un anno. Le transazioni sono di tipo **Normale**. È pertanto unicamente possibile creare transazioni di sottoscrizione in cui la data iniziale e la data finale corrispondano a periodi creati in precedenza nel modulo **Tipi di periodo**. Per ulteriori informazioni sulle transazioni di commissione, vedere [Creare transazioni di commissione di sottoscrizione](create-subscription-fee-transactions.md).

Dopo aver impostato la sottoscrizione per il cliente, si ricorda di aver concordato uno sconto del 10% su tutti i prezzi di listino relativi ai servizi. È pertanto necessario ridurre il prezzo della commissione appena creata.

Più tardi si riceve una telefonata dal contatto del cliente in cui viene comunicato che il cliente desidera ancora il contratto di assistenza per la manutenzione delle linee elettriche, ma ha pianificato l'introduzione di una nuova linea elettrica nel corso dell'anno. La copertura del contratto di assistenza è quindi necessaria solo fino a ottobre 2013. Per ridurre il numero di mesi della sottoscrizione del cliente, creare una nuova transazione di commissione di sottoscrizione di tipo **Giorni riduzione**. Per ulteriori informazioni sulla riduzione dei giorni, vedere [Ridurre i giorni delle commissioni di sottoscrizione](reduce-the-days-on-subscription-fees.md).

## <a name="invoice-and-accrue-subscription-transactions"></a>Fatturare e accumulare le transazioni di sottoscrizione

L'impostazione della sottoscrizione è completata ed è possibile fatturare la sottoscrizione al cliente. Per ulteriori informazioni sulla fatturazione delle sottoscrizioni, vedere [Fatturare transazioni di sottoscrizione](invoice-subscription-transactions.md).

Due giorni dopo, il cliente richiede la fatturazione in dollari statunitensi, anziché in euro. È pertanto necessario creare una nota di accredito e una nuova transazione di sottoscrizione nella valuta corretta. Per ulteriori informazioni sull'accredito di transazioni di sottoscrizione, vedere [Accreditare transazioni di sottoscrizione](credit-subscription-transactions.md).

Alla fine di ogni mese, è possibile accumulare i ricavi mensili provenienti dalla sottoscrizione del cliente nel conto profitti e perdite e nei conti WIP. Per ulteriori informazioni sull'accumulo di ricavi per le sottoscrizioni, vedere [Accumulare ricavi sottoscrizioni](accrue-subscription-revenue.md).

  




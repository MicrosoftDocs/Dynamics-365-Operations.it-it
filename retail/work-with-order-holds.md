---
title: Sospensioni ordine
description: In questo argomento vengono descritte le sospensioni degli ordini tramite l&quot;utilizzo di Vendita al dettaglio e commercio in Dynamics AX.
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 1cb18e3275b8dcdf0a61531ee056995f6e8fbc8d
ms.lasthandoff: 03/31/2017


---

# <a name="order-holds"></a>Sospensioni ordine

[!include[banner](includes/banner.md)]


In questo argomento vengono descritte le sospensioni degli ordini tramite l'utilizzo di Vendita al dettaglio e commercio in Dynamics AX.

Un ordine può essere sospeso per diversi motivi. Ad esempio, è possibile sospendere un ordine fino a che non può essere verificato un indirizzo cliente o un metodo di pagamento o fino a che un responsabile non può verificare il limite di credito del cliente. Durante il processo di vendita, ci sono volte in cui è necessario sospendere un ordine cliente. Ad esempio, un ordine cliente potrebbe essere sospeso a causa di problemi di pagamento di un cliente, per il sospetto di una frode o perché un responsabile deve esaminare l'ordine. Quando un ordine cliente viene sospeso, a tale ordine viene assegnato un codice sospensione ordine per indicare il motivo della sospensione. I codici sospensione degli ordini cliente vengono configurati in **Vendite e marketing** &gt; **Impostazione** &gt; **Ordini cliente** &gt; **Codici sospensione ordine**. Un ordine cliente può sospeso manualmente al momento della creazione dell'ordine o in un secondo momento. Inoltre, un ordine può essere sospeso automaticamente, in base a regole sulla frode. Mentre un ordine cliente è in attesa, potrebbe essere necessario aggiornarlo con ulteriori informazioni. Oppure è possibile che si desideri eseguire il Check-out dell'ordine cliente mentre si continua a compilarlo. È possibile eseguire il check-out di un ordine cliente, eseguirne di nuovo il check-in e, quando necessario, sovrascrivere il check-out di un altro utente utilizzando il workbench di sospensione dell'ordine (**Vendita al dettaglio e commercio** &gt; **Clienti** &gt; **Sospensioni ordine**). Quando un ordine è pronto per essere completato, è necessario rimuovere la sospensione prima di poter completare il processo di ordine.





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
ms.search.scope: AX 7.0.0, Operations, Core
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

In questo argomento vengono descritte le sospensioni degli ordini tramite l'utilizzo di Vendita al dettaglio e commercio in Dynamics AX.

Un ordine può essere sospeso per diversi motivi. Ad esempio, è possibile sospendere un ordine fino a che non può essere verificato un indirizzo cliente o un metodo di pagamento o fino a che un responsabile non può verificare il limite di credito del cliente. Durante il processo di vendita, ci sono volte in cui è necessario sospendere un ordine cliente. Ad esempio, un ordine cliente potrebbe essere sospeso a causa di problemi di pagamento di un cliente, per il sospetto di una frode o perché un responsabile deve esaminare l'ordine. Quando un ordine cliente viene sospeso, a tale ordine viene assegnato un codice sospensione ordine per indicare il motivo della sospensione. I codici delle sospensioni dell'ordine cliente vengono configurati ** Vendite e marketing ** &gt; ** all'impostazione ** &gt; ** ordini cliente ** &gt; ** l'ordine sono archiviati i codici **. Un ordine cliente può sospeso manualmente al momento della creazione dell'ordine o in un secondo momento. Inoltre, un ordine può essere sospeso automaticamente, in base a regole sulla frode. Mentre un ordine cliente è in attesa, potrebbe essere necessario aggiornarlo con ulteriori informazioni. Oppure è possibile che si desideri eseguire il Check-out dell'ordine cliente mentre si continua a compilarlo. È possibile verificare un ordine cliente, lo controllate indietro in e persino da sovrascrivere l'estrazione di un altro utente utilizzando la propria postazione di lavoro delle sospensioni di ordine (** al dettaglio e il commercio ** &gt; ** clienti ** &gt; ** l'ordine ricopre **). Quando un ordine è pronto per essere completato, è necessario rimuovere la sospensione prima di poter completare il processo di ordine.



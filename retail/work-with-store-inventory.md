---
title: Gestione Store Inventory
description: "In questo articolo viene descritto i tipi di documenti che è possibile utilizzare per gestire le scorte."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: fbe9945799f1e65ed6ad624a3df270fa4eb72b88
ms.lasthandoff: 03/31/2017


---

# <a name="manage-store-inventory"></a>Gestione Store Inventory

In questo articolo viene descritto i tipi di documenti che è possibile utilizzare per gestire le scorte.

È possibile utilizzare i seguenti tipi di documenti per la gestione dell'inventario dell'organizzazione.

## <a name="purchase-orders"></a>Ordine fornitore
Gli ordini fornitore vengono creati nella sede centrale. Se un magazzino al dettaglio viene incluso nell'intestazione dell'ordine fornitore, l'ordine può essere ricevuto presso il punto vendita utilizzando il POS moderno (MPOS) o del POS cloud in Microsoft Dynamics 365 per le operazioni al dettaglio. Una volta immesse, è possibile salvare in locale le quantità ricevute all'interno del punto vendita per ulteriori modifiche. In alternativa, i quantitativi possono essere impegnati e inviati alla sede principale. Nella sede principale, le quantità ricevute al punto vendita vengono visualizzati in Dynamics 365 per le operazioni, in ** Ricevi ora ** il campo nell'ordine fornitore.

## <a name="transfer-orders"></a>Ordini di trasferimento
Un ordine di trasferimento può specificare che un particolare punto vendita è un percorso da cui possono essere spediti gli articoli. In questo caso, l'ordine di trasferimento viene visualizzato nella memoria la richiesta di prelievo in MPOS o in Retail POS su cloud. Una volta che i quantitativi richiesti sono stati prelevati, vengono impegnati e inviati alla sede principale. Nella sede principale, le quantità selezionate al punto vendita vengono visualizzati in Dynamics 365 per le operazioni, in ** spedire ora ** il campo nell'ordine di trasferimento. Un ordine di trasferimento può specificare che un particolare punto vendita è un percorso da cui possono essere spediti gli articoli. In questo caso, l'ordine di trasferimento viene visualizzato nella richiesta come punto di ricevimento in MPOS o in Retail POS su cloud. Una volta immesse, è possibile salvare in locale le quantità ricevute all'interno del punto vendita per ulteriori modifiche. In alternativa, i quantitativi possono essere impegnati e inviati alla sede principale. Nella sede principale, le quantità ricevute al punto vendita vengono visualizzati in Dynamics 365 per le operazioni, in ** Ricevi ora ** il campo nell'ordine di trasferimento.

## <a name="stock-counts"></a>Conteggi scorte
I conteggi scorte possono essere pianificati o non pianificati. I conteggi di scorte programmate sono avviati presso la sede principale, la quale specifica gli articoli da conteggiare. La sede principale crea un documento conteggio che può essere ricevuto presso il punto vendita, dove le quantità disponibili di scorte effettive immesse in MPOS o si appannano il POS. I Conteggi scorte non programmati vengono avviati a un punto vendita e le quantità disponibile di scorte effettive vengono aggiornate in MPOS o si appannano il POS. A differenza dei conteggi scorte pianificati, i conteggi scorte non pianificati non dispongono di un elenco predefinito di elementi. Al termine di un conteggio scorte di entrambi i tipi, questo viene impegnato e inviato alla sede principale. Presso la sede centrale, il conteggio viene convalidato e registrato.





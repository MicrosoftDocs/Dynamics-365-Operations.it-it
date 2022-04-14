---
title: Messaggi d'azione
description: Un messaggio di azione è un suggerimento generato dal sistema per modificare un ordine pianificato o stabilizzato.
author: t-benebo
ms.date: 10/14/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, MCRSalesOrderMessages, MCRSalesTableDetailedStatus, TAMItemVendRebateGroup, TAMVendRebate, TAMVendRebateAgreementLineInfoPart, TAMVendRebateGroup, TAMVendRebateTable, TAMVendRebateTrans, ReqTransActionListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19411
ms.assetid: 52b46d93-7d02-46b5-aad1-9fd08206bf9d
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2acba2ba12f933c085de15eadbf4d433944c2cf3
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469452"
---
# <a name="action-messages"></a>Messaggi d'azione

[!include [banner](../includes/banner.md)]

Un messaggio di azione è un suggerimento generato dal sistema per modificare un ordine pianificato o stabilizzato.

## <a name="introduction"></a>Introduzione

I messaggi di azione sono generati dal calcolo della pianificazione generale in seguito alle richieste modificate. Ad esempio, la data di spedizione o la quantità possono essere state modificate in un ordine cliente per il quale è già stato creato un ordine acquisto per soddisfare la richiesta. In questo caso, uno o più messaggi di azione sono generati dal calcolo di pianificazione generale per aggiornare l'ordine acquisto. È quindi possibile decidere se effettuare le modifiche suggerite.

La modalità di calcolo dei messaggi d'azione può essere configurata per un gruppo di copertura collegato a un articolo.

## <a name="select-action-messages"></a>Selezione dei messaggi d'azione

Nella pagina **Gruppi di copertura**, è possibile selezionare i messaggi di azione che si desidera vengano generati dal sistema e i gruppi di copertura o gli articoli a cui i messaggi si riferiscono. È possibile selezionare i seguenti messaggi di azione.

| Messaggio             | Descrizione                                                                                                                                                                                                                                              |
|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Anticipa**         | Se si seleziona il messaggio, il sistema genera messaggi di azione, quando necessario, per spostare gli ordini a una data precedente. Nel campo **Margine di avanzamento** è inoltre possibile specificare il numero massimo di giorni tra l'entrata e l'uscita senza azioni di anticipo. |
| **Posticipa**        | Se si seleziona il messaggio, il sistema genera messaggi di azione, quando necessario, per spostare gli ordini a una data successiva. Nel campo **Margine di posticipo** è inoltre possibile specificare il numero massimo di giorni tra l'entrata e l'uscita senza azioni di posticipo.       |
| **Svaluta**        | Se si seleziona questo messaggio, gli ordini di produzione, gli ordini fornitore e altre transazioni in entrata devono essere diminuiti per impedire livelli di scorte in eccesso.                                                                                                   |
| **Aumento**        | Se si seleziona questo messaggio, gli ordini di produzione, gli ordini fornitore e altre transazioni in entrata devono essere aumentati per impedire livelli di scorte in difetto.                                                                                                    |
| **Azioni derivate** | Se si seleziona il messaggio, vengono creati i messaggi di azione per i requisiti derivati, ad esempio, azioni per gli ordini componenti che soddisfano la produzione.                                                                                                   |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
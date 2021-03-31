---
title: Risolvere i problemi dei flussi di lavoro di approvvigionamento
description: Questo argomento descrive come risolvere i problemi che potrebbero verificarsi mentre lavori con i flussi di lavoro di approvvigionamento.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: d5d688c5769a62580e48908117d0562b26eab10a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222827"
---
# <a name="troubleshoot-procurement-and-sourcing-workflows"></a>Risolvere i problemi dei flussi di lavoro di approvvigionamento

Questo argomento descrive come risolvere i problemi che potrebbero verificarsi mentre lavori con i flussi di lavoro di approvvigionamento.

## <a name="error-when-re-submitting-a-purchase-order-to-the-workflow-after-a-change-changes-to-purchase-order-x-are-allowed-only-in-a-draft-state-when-change-management-is-activated"></a>Errore durante il reinvio di un ordine fornitore al flusso di lavoro dopo una modifica: "Le modifiche all'ordine fornitore X sono consentite solo in stato Bozza quando è attivata la gestione delle modifiche"

Questo problema si verifica solo se l'ordine fornitore era in uno stato *Confermato* prima di richiedere le modifiche. Se richiedi modifiche mentre l'ordine fornitore è in uno stato *Approvato*, il flusso di lavoro può essere elaborato correttamente.

### <a name="error-description"></a>Descrizione errore

Il seguente errore si verifica nel flusso di lavoro quando un ordine fornitore viene nuovamente inviato dopo una modifica:

> Interrotto (errore): Eccezione X++: le modifiche all'ordine fornitore PO0000569 sono consentite solo nello stato Bozza quando la gestione delle modifiche è attivata su<br>
SysWorkflowParticipantProvider-resolve<br>
SysWorkflowParticipantProvider-resolveParticipants<br>
SysWorkflowServiceProvider-resolveParticipant<br>
SysWorkflowQueue-resume

### <a name="issue-resolution"></a>Risoluzione dei problemi

Questo problema può verificarsi a causa di incoerenze nelle distribuzioni degli ordini fornitore.

Per sbloccare questo problema e reimpostare l'ordine fornitore su uno stato *Bozza*, vai a **Approvvigionamento \>Attività periodiche \> Pulisci \> Reimpostazione distribuzione ordine fornitore**. Per ulteriori informazioni, vedi il seguente post del blog: [Risolvere gli errori di distribuzione dell'ordine fornitore in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

Il problema verrà risolto tramite [questo articolo della Knowledge Base (KB) di Microsoft](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138).

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a>Una o più distribuzioni contabili è distribuita eccessivamente o sottodistribuita.

Questo problema può verificarsi a causa di incoerenze nelle distribuzioni degli ordini fornitore.

Per sbloccare questo problema e reimpostare l'ordine fornitore su uno stato *Bozza*, vai a **Approvvigionamento \>Attività periodiche \> Pulisci \> Reimpostazione distribuzione ordine fornitore**. Per ulteriori informazioni, vedi il seguente post del blog: [Risolvere gli errori di distribuzione dell'ordine fornitore in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="if-a-delivery-remainder-is-canceled-on-a-purchase-order-where-change-management-is-turned-on-the-purchase-order-goes-to-a-confirmed-state"></a>Se una rimanenza di consegna viene annullata su un ordine fornitore in cui è attivata la gestione delle modifiche, l'ordine fornitore passa allo stato Confermato.

### <a name="issue-description"></a>Descrizione del problema

Per un ordine fornitore soggetto a gestione delle modifiche, se l'unica modifica richiesta è l'annullamento di una rimanenza di consegna su una o più righe, l'ordine fornitore passerà direttamente sullo stato *Confermato* quando è approvato e non verrà creato alcun giornale di registrazione.

### <a name="issue-resolution"></a>Risoluzione dei problemi

L'annullamento di una rimanenza di consegna non influisce sul contenuto del giornale di registrazione delle conferme. Questa funzionalità deve essere utilizzata quando la riga è stata ricevuta parzialmente e la qualità rimanente deve essere annullata nel passaggio di processo dopo che l'ordine fornitore è stato confermato con il fornitore.

Se ciò si riflette sulla conferma dell'ordine fornitore, la quantità deve essere rettificata nella riga dell'ordine fornitore in modo che venga richiesta la conferma. In alternativa, se non è stato ricevuto nulla sulla riga, la quantità può essere rimossa. In questo caso, sarà richiesta la riconferma.

## <a name="canceled-purchase-orders-appear-in-the-draft-list-in-the-purchase-order-preparation-workspace"></a>Gli ordini fornitore annullati vengono visualizzati nell'elenco delle bozze nell'area di lavoro Preparazione ordini fornitore.

### <a name="issue-description"></a>Descrizione del problema

Dopo aver annullato gli ordini fornitore che erano nello stato *Confermato*, gli ordini fornitore annullati vengono ancora visualizzati nell'elenco delle bozze di ordini fornitore nell'area di lavoro **Preparazione ordine fornitore**.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Questo problema si verifica solo per gli ordini fornitore soggetti a gestione delle modifiche. Si verifica perché l'annullamento è considerato una modifica che deve essere approvata. L'approvazione può essere eseguita automaticamente dal sistema. Pertanto, il processo consiste nell'inviare l'ordine fornitore annullato al flusso di lavoro di approvazione in modo che possa passare allo stato *Approvato*. A quel punto, l'ordine fornitore non verrà più visualizzato nell'elenco delle bozze di ordini fornitore nell'area di lavoro **Preparazione ordine fornitore**.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
---
title: Errore durante il reinvio di un ordine fornitore a un flusso di lavoro dopo una modifica
description: Errore durante il reinvio di un ordine fornitore a un flusso di lavoro dopo una modifica
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4b8465d198c440f27a4b3cc4268445e0aa450f5b
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476815"
---
# <a name="error-on-resubmitting-a-purchase-order-to-a-workflow-after-a-change"></a>Errore durante il reinvio di un ordine fornitore a un flusso di lavoro dopo una modifica


## <a name="symptoms"></a>Sintomi

Il seguente errore si verifica nel flusso di lavoro quando un ordine fornitore viene nuovamente inviato dopo una modifica:

> Interrotto (errore): Eccezione X++: le modifiche all'ordine fornitore PO0000569 sono consentite solo nello stato Bozza quando la gestione delle modifiche è attivata su<br>
SysWorkflowParticipantProvider-resolve<br>
SysWorkflowParticipantProvider-resolveParticipants<br>
SysWorkflowServiceProvider-resolveParticipant<br>
SysWorkflowQueue-resume

Questo problema si verifica solo se l'ordine fornitore era in uno stato *Confermato* prima di richiedere le modifiche. Se richiedi modifiche mentre l'ordine fornitore è in uno stato *Approvato*, il flusso di lavoro può essere elaborato correttamente.

## <a name="resolution"></a>Risoluzione

Questo problema può verificarsi a causa di incoerenze nelle distribuzioni degli ordini fornitore.

Per sbloccare questo problema e reimpostare l'ordine fornitore su uno stato *Bozza*, vai a **Approvvigionamento \>Attività periodiche \> Pulisci \> Reimpostazione distribuzione ordine fornitore**. Per ulteriori informazioni, vedi il seguente post del blog: [Risolvere gli errori di distribuzione dell'ordine fornitore in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

Il problema verrà risolto tramite [questo articolo della Knowledge Base (KB) di Microsoft](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138).

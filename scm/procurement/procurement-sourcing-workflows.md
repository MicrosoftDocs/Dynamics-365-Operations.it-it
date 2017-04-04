---
title: Flussi di lavoro di approvvigionamento
description: "In alcune organizzazioni le richieste di acquisto e gli ordini fornitore devono essere approvati da un utente diverso dalla persona che ha immesso la transazione. Per impostare un processo di approvazione, è possibile creare un flusso di lavoro."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 27c211e6ded17e085559add916c28a48c40e5b8e
ms.lasthandoff: 03/31/2017


---

# <a name="procurement-and-sourcing-workflows"></a>Flussi di lavoro di approvvigionamento

In alcune organizzazioni le richieste di acquisto e gli ordini fornitore devono essere approvati da un utente diverso dalla persona che ha immesso la transazione. Per impostare un processo di approvazione, è possibile creare un flusso di lavoro.

Un flusso di lavoro rappresenta un processo aziendale. Definisce il modo in cui un documento attraversa il sistema e stabilisce chi deve completare un'attività o approvare un documento. Di seguito sono descritti i vantaggi derivanti dall'utilizzo di un sistema basato su flusso di lavoro all'interno dell'organizzazione:
-   **Processi coerenti**: è possibile definire il processo di approvazione per documenti specifici, ad esempio richieste di acquisto e note spese. L'utilizzo del sistema flusso di lavoro consente di garantire che i documenti vengano elaborati e approvati in modo efficiente e coerente.
-   **Visibilità dei processi**: è possibile tenere traccia delle metriche relative a stato, storico e prestazioni di una specifica istanza di flusso di lavoro. In questo modo è possibile stabilire se il flusso di lavoro necessita di modifiche allo scopo di migliorarne l'efficienza.
-   ** La elenco di lavoro ** - utenti possono visualizzare un elenco di lavoro per verificare le attività e i processi di approvazione del flusso in tutti i flussi di lavoro che partecipano in. Questo campo è disponibile nelle pagine di elementi di lavoro.

## <a name="the-types-of-workflows-that-you-can-create"></a> Tipi di flussi di lavoro che è possibile creare
Per Approvvigionamento sono disponibili i tipi di flusso di lavoro indicati di seguito.

|                                  |                                                               |
|----------------------------------|---------------------------------------------------------------|
| **Tipo**                         | **Utilizzare questo tipo per:**                                          |
| Verifica richiesta di acquisto      | Creare flussi di lavoro di revisione per richieste di acquisto.            |
| Verifica righe di richiesta di acquisto | Creare flussi di lavoro di revisione per righe richieste di acquisto.       |
| Flusso di lavoro ordine fornitore          | Creare flussi di lavoro di revisione e approvazione per ordini fornitore.     |
| Flusso di lavoro riga ordine fornitore     | Creare flussi di lavoro di revisione e approvazione per righe ordine fornitore. |

## <a name="creating-a-workflow"></a>Creazione di un flusso di lavoro
Per creare un flusso di lavoro, passare ai flussi di lavoro del modulo Approvvigionamento di impostazione di approvvigionamento e creare un nuovo flusso di lavoro selezionando il tipo di flusso di lavoro da creare.  

Nella canvas del flusso di lavoro è possibile trascinare elementi del flusso di lavoro nel designer e collegare gli elementi a un flusso. Gli elementi del flusso di lavoro devono essere configurati. Per gli elementi del flusso di lavoro e l'approvazione è possibile configurare il partecipante che deve eseguire l'operazione.
Tipi di partecipanti
----------------------

È possibile assegnare un passaggio di approvazione ai gruppi di partecipanti indicati di seguito.

| Gruppo utenti    | Descrizione                                                               |
|---------------|---------------------------------------------------------------------------|
| Partecipante   | Assegnare il passaggio di approvazione ai membri di un gruppo o ruolo.                   |
| Gerarchia     | Assegnare il passaggio di approvazione agli utenti di una gerarchia organizzativa specifica. |
| Utente del flusso di lavoro | Assegnare il passaggio di approvazione agli utenti del flusso di lavoro.                       |
| Coda         | Assegnare il passaggio di approvazione a una coda di elementi di lavoro.                            |
| Utente          | Assegnare il passaggio relativo all'approvazione a utenti specifici.                               |



<a name="see-also"></a>Vedere anche
--------

[Definizione di flussi di lavoro di processi aziendali per le richieste di acquisto](https://mbs.microsoft.com/customersource/Global/AX/learning/documentation/white-papers/Defining_business_process_workflows_for_purchase_requisitions)

[Purchase requisition workflow](purchase-requisitions-workflow.md)



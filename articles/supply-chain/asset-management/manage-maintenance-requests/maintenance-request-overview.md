---
title: Richieste di intervento di manutenzione
description: In questo argomento viene fornita una panoramica sulla gestione delle richieste di intervento di manutenzione in Gestione cespiti
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetRequestTable, EntAssetRequestWorkspace, EntAssetRequestActivePart, EntAssetRequestWorkOrderActive, EntAssetRequestType, EntAssetRequestTableCreateWO, EntAssetRequestTableLookup, EntAssetRequestTableActivePart, EntAssetMobileRequestDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3c72a16b8f3865129ad737c511e50eb34c9f2e91
ms.sourcegitcommit: 51cad1ce3ed44ebf7eb9bdf553ee2df4c1f03135
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "6015880"
---
# <a name="maintenance-requests"></a>Richieste di intervento di manutenzione

[!include [banner](../../includes/banner.md)]

Le richieste di intervento di manutenzione sono note o le dichiarazioni create per informare un responsabile o un responsabile della pianificazione che un cespite può richiedere un processo di riparazione o manutenzione, ma senza creare un ordine di lavoro. Se il contenuto di una richiesta di intervento di manutenzione viene considerato valido, un ordine di lavoro può quindi essere creato in base alla richiesta di intervento di manutenzione.

Le richieste di intervento di manutenzione possono essere create per qualsiasi cespite in Gestione cespiti. Diversi tipi di richieste di intervento di manutenzione possono essere creati, a seconda di come la società utilizza le richieste di intervento di manutenzione. Di seguito sono riportati alcuni esempi.

- Richieste di intervento di manutenzione
- Note
- Correzioni o miglioramenti
- Investimenti
- Riparazione in deposito (questo tipo viene utilizzato quando si ricevono i cespiti da un'altra ubicazione in modo da poter effettuare un processo di riparazione o di manutenzione e quindi restituire il cespite dopo che il processo è completato.)

## <a name="view-maintenance-requests"></a>Visualizza richieste di intervento di manutenzione

Per visualizzare le richieste di intervento di manutenzione, selezionare **Gestione cespiti** \> **Comune** \> **Richieste di intervento di manutenzione** \>, **Tutte le richieste di intervento di manutenzione**, **Richieste di intervento di manutenzione attive** o **Richieste di intervento di manutenzione delle unità funzionali personali**. Ogni pagina elenco vengono visualizzate alcune informazioni correlate a una richiesta di intervento di manutenzione.

![Visualizza richieste di intervento di manutenzione](media/01-manage-maintenance-requests.png)

> [!NOTE]
> Usare la pagina elenco **Richieste di intervento di manutenzione delle unità funzionali personali** per visualizzare un elenco di richieste di intervento di manutenzione contenenti le unità funzionali a cui si è correlati come lavoratori o i cespiti installati nelle unità funzionali a cui si è correlati come lavoratore. Per informazioni su come impostare le unità funzionali per gli addetti alla manutenzione, vedere [Addetti alla manutenzione e gruppi di lavoratori](../setup-for-objects/workers-and-worker-groups.md).
> 
> Sebbene le informazioni su un conto cliente siano disponibili in Gestione assistenza cespiti (manutenzione esterna), non sono disponibili in Gestione cespiti (manutenzione interna).

Per aprire la visualizzazione dettagli di un record, nella pagina elenco **Tutte le richieste di intervento di manutenzione**, in visualizzazione griglia, selezionare un collegamento nella colonna **Richiesta di intervento di manutenzione**.

![Visualizzare i dettagli della richiesta di intervento di manutenzione](media/02-manage-maintenance-requests.png)

I pulsanti del riquadro azioni sono organizzati in schede. Nella tabella seguente vengono brevemente descritte i pulsanti correlati a Gestione cespiti.

| Nome del pulsante                      | Descrizione |
|----------------------------------|-------------|
| Modifica                             | Modifica la richiesta di intervento di manutenzione selezionata |
| Nuove                              | Crea una nuova richiesta di intervento di manutenzione. |
| Eliminazione                           | Elimina la richiesta di intervento di manutenzione selezionata. |
| Pool di ordini di lavoro                  | Collega la richiesta di intervento di manutenzione a un pool di ordini di lavoro. |
| Ordine di lavoro                       | Crea un ordine di lavoro basato sulla richiesta di intervento di manutenzione selezionata. |
| Errore del cespite                      | Fare clic su **Errori del cespite**, in cui è possibile creare una registrazione dei problemi per la richiesta di intervento di manutenzione selezionata. |
| Ordini di lavoro                      | Consente di visualizzare un elenco di tutti gli ordini di lavoro collegati alla richiesta di intervento di manutenzione selezionata. |
| Aggiorna stato della richiesta di intervento di manutenzione | Aggiorna lo stato della richiesta di intervento di manutenzione. |
| Registro dello stato del ciclo di vita              | Visualizza un registro contenente gli stati del ciclo di vita della richiesta di Aggiorna stato della richiesta di intervento di manutenzione selezionata. |
| Dettagli richieste di intervento di manutenzione      | Consente di stampare un report contenente i dettagli della richiesta di intervento di manutenzione selezionata. |
| Invia cespite in prestito                  | Seleziona un cespite di prestito che deve essere una sostituzione temporanea per il cespite selezionato nella richiesta di intervento di manutenzione selezionata. |
| Restituisci cespite in prestito                | Registra il cespite in prestito come restituito. |



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
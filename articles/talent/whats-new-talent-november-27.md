---
title: Novità o modifiche in Dynamics 365 for Talent Core HR (27 novembre 2018)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 11/27/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-27
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6bd049bfe4639136276ab2f14e6310e45d1254f2
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "304955"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-november-27-2018"></a>Novità o modifiche in Dynamics 365 for Talent Core HR (27 novembre 2018)

[!include [banner](includes/banner.md)]

**Build 8.1.2064**

Questo argomento descrive le funzionalità nuove o modificate di Core HR.


## <a name="changes"></a>Modifiche

### <a name="unable-to-create-a-note-in-case-management"></a>Impossibile creare una nota in Gestione casi

È stata effettuata una modifica per un problema che si verificava durante il tentativo di modificare o creare una nota nel registro casi di Gestione casi.

### <a name="misspelled-word-on-the-analytics-tab-in-the-compensation-workspace"></a>Parola errata nella scheda Analisi dell'area di lavoro di retribuzione 

È stata effettuata una modifica per correggere l'errore in "Origine etnica" nel grafico dell'analisi di retribuzione dell'area di lavoro di retribuzione.

### <a name="employee-self-service-workspace-not-displaying-when-a-user-isnt-assigned-to-a-worker"></a>Area di lavoro Dipendente self-service non visualizzata quando un utente non viene assegnato a un lavoratore 

È stata effettuata una modifica in relazione alla selezione dell'area di lavoro **Dipendente self-service** come pagina iniziale nella configurazione di un utente non assegnato a un lavoratore. In questa situazione, viene visualizzato il dashboard predefinito.

### <a name="leave-and-absence-error-object-reference-not-set-to-an-instance-of-an-object"></a>Errore in Congedo e assenza: riferimento a un oggetto non impostato su un'istanza di un oggetto

Sono state apportate modifiche a Congedo e assenza per correggere questo errore dopo l'approvazione dei record di congedo e assenza nell'elenco **Elementi di lavoro assegnati all'utente**.

### <a name="unable-to-recall-an-image-workflow"></a>Impossibile richiamare un flusso di lavoro di immagine

Dopo il richiamo di un flusso di lavoro di immagine, il flusso di lavoro viene impostato su "Annullato" e la richiesta esistente può essere eliminata nell'area di lavoro Dipendente self-service.

### <a name="rehired-employees-or-contractors-show-up-multiple-times-after-termination"></a>I dipendenti o i terzisti riassunti sono visualizzati più volte dopo la fine del rapporto 

Con questo aggiornamento, i dipendenti con i quali il rapporto di lavoro è concluso sono visualizzati una sola volta nell'elenco delle uscite. 

## <a name="known-issue"></a>Problema noto

- **Problema**: quando si aggiunge un nuovo allegato a un lavoratore, i pulsanti **Nuovo** e **Modifica** sono inattivi. 
- **Soluzione alternativa:** prima di aprire la pagina dell'allegato, verificare che le schede dettaglio della pagina **Lavoratore** siano chiuse. Se i riquadri Dettaglio informazioni sono chiusi quando la pagina **Lavoratore** viene caricata, i pulsanti degli allegati saranno abilitati. Questo problema verrà risolto nel prossimo aggiornamento della piattaforma.

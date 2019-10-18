---
title: Note spese rinnovate
description: In questo argomento vengono fornite informazioni sull'esperienza rinnovata e riprogettata per immissione delle note spese in Microsoft Dynamics 365 Finance. La nuova esperienza semplifica il processo di completamento delle note spese e riduce il tempo necessario.
author: ryansandness
manager: AnnBe
ms.date: 06/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2019-6-30
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 8a8ad1ad84b8acaa54d8b03327157a930e562f59
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187661"
---
# <a name="expense-reports-reimagined"></a>Note spese rinnovate

[!include[banner](../includes/banner.md)]

L'immissione delle note spese è stata riprogettata per semplificare il processo di completamento di note spese e per ridurre il tempo necessario. Di seguito vengono riportati i componenti principali della nuova esperienza di spesa:

- Una nuova area di lavoro Gestione spese che consente di accedere alle spese del delegato.
- Una nuova esperienza di abbinamento delle ricevute per mostrare meglio le ricevute a livello di intestazione e semplificare il processo di collegamento delle ricevute alle righe di spesa.
- Una nuova griglia di sola lettura che consente di visualizzare numerose altre righe di spesa e colonne di dati aggiuntivi. Ora è possibile visualizzare tutte le righe dettagliate e suddivise, insieme alle corrispondenti spese padre.
- Un riquadro semplificato per modificare le spese.
- Messaggi di errore, avvisi e messaggi per i criteri riprogettati per garantire all'utente di avere il contesto corretto per capire qual è il problema e come risolverlo. Microsoft ha rimosso molti messaggi che apparivano prima che gli utenti avessero l'opportunità di completare le loro attività e risolvere i problemi, come il messaggio sui dettagli incompleti.
- Una nuova pagina per specificare quali campi sono richiesti dall'organizzazione, quali campi sono facoltativi e quali campi non devono essere acquisiti. Questa pagina aiuta a ridurre il numero di campi che gli utenti devono impostare.
- Un nuovo aspetto per le note spese, in modo che i report non sembrino più progettati per il personale del reparto contabilità.

Per attivare la nuova esperienza, utilizzare l'area di lavoro **Gestione funzionalità** e abilitare la caratteristica **Note spese rinnovate**. Quando viene attivata questa funzionalità, si verificano le seguenti azioni:

- L'area di lavoro esistente per le spese viene sostituita con la nuova area di lavoro.
- Viene aggiunta una nuova voce di menu per la visibilità del campo delle spese.
- Non vengono rimosse voci di menu esistenti per le note spese (pagina esistente) o il report spese.
- I flussi di lavoro e le eventuali approvazioni portano ancora alla pagina delle note spese esistente.

## <a name="getting-started-video-for-new-users"></a>Video introduttivo per i nuovi utenti

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Y7gO]

Il video relativo all'[esperienza di spesa in Dynamics 365 for Finance and Operations](https://youtu.be/Ocy-MsTvEE0) (mostrato sopra) è incluso nella [playlist di Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponibile in YouTube.

## <a name="new-features"></a>Nuove funzionalità

| Nuova funzionalità | Descrizione |
|---|----|
| Visibilità del campo di spesa | Una nuova pagina di configurazione consente di specificare quali campi devono essere disabilitati per un'organizzazione, quali campi devono essere obbligatori e quali campi sono consigliati. |
| Campi obbligatori | La nuova semplice configurazione consente di rendere alcuni campi obbligatori senza dover utilizzare il framework dei criteri. |
| Campi facoltativi | Viene aggiunta una seconda pagina per i campi facoltativi. In questo modo, i dipendenti non si sentiranno come se dovessero impostare i campi, ma i campi sono ancora facilmente accessibili. |
| Aggiunta di ricevute non allegate | La possibilità di aggiungere ricevute non allegate alla nota spese è più visibile dall'area di lavoro e sulla nota spese. |
| Messaggistica migliorata | Migliore visibilità delle righe di spesa con avvisi o errori. |
| Riduzione dei messaggi sulla barra dei messaggi| Il numero di messaggi del Registro informazioni è stato ridotto e uno sforzo è stato fatto per impedire la visualizzazione di messaggi duplicati in molti casi. |
| Azioni comuni raggruppate | L'interfaccia è stata riorganizzata con l'aggiunta di un nuovo pulsante di azioni per la maggior parte delle azioni comuni a livello di riga e l'aggiunta di un pulsante di ellissi (...) per l'intestazione e altre azioni meno frequenti. |
| Nuova area di lavoro per aumentare visibilità | Una nuova area di lavoro combina funzionalità e collegamenti che consentono agli utenti di spostarsi in aree diverse. |
| Aggiunta di spese e ricevute esistenti durante la creazione della spesa | Quando si creano le note spese, è possibile aggiungere tutte o alcune spese o ricevute selezionate. |
| Calcolatore del tasso di cambio | Viene aggiunto un calcolatore del tasso di cambio che consente di calcolare il tasso di cambio per le transazioni multivaluta su una carta di credito aziendale. |
| Salvataggio e aggiunta di nuove righe di spesa | I pulsanti **Nuovo** e **Salva** sono disponibili quando vengono inserite nuove spese, per inserire rapidamente le righe di spesa. |
| Migliore visibilità della suddivisione e righe dettagliate | Le linee dettagliate e divise vengono aggiunte direttamente all'elenco delle spese, per aumentare la visibilità e aiutare a determinare facilmente eventuali errori di criteri o altri errori. |
| Visualizzazione delle ricevute durante la creazione dei dettagli | Le ricevute possono essere mostrate durante la creazione dei dettagli. |

La versione iniziale è incentrata sugli scenari di immissione delle spese. Qualsiasi scenario di revisione o di approvazione della nota spese continuerà a utilizzare la pagina di immissione spese esistente.

Le funzionalità seguenti sono presenti nella pagina esistente ma non sono ancora presenti nella nuova pagina. Queste funzionalità verranno rintrodotte nelle diverse versioni seguenti:

- Approvazioni
- Approvazioni di contabilità fornitori e possibilità di modificare la contabilità
- Più punti di ingresso
- Integrazione della richiesta di viaggio
- Entità di dati per visibilità del campo di spesa
- Immissione per spese giornaliere
- Flusso di lavoro a livello della riga
- Supporto per l'approvatore temporaneo
- Dettagli avanzati

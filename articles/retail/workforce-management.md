---
title: Panoramica del servizio Gestione della forza lavoro
description: Questo argomento descrive come utilizzare il servizio Gestione della forza lavoro per usufruire di client POS, Modern POS e POS cloud comuni, di modo che i responsabili punto vendita possano gestire facilmente la forza lavoro.
author: shalabhjainmsft
manager: AnnBe
ms.date: 7/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Core
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-07-30
ms.dyn365.ops.version: Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: d67ad79c068651f32ce7dc776bc460698557bc29
ms.openlocfilehash: f747dce6b9595de50297cb5af7db523d5f26a844
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="workforce-management-overview"></a>Panoramica del servizio Gestione della forza lavoro

[!include[banner](includes/banner.md)]
    
Il servizio Gestione della forza lavoro utilizza client POS, Modern POS e POS cloud comuni per consentire ai responsabili punto vendita di gestire facilmente la forza lavoro. Il servizio Gestione della forza lavoro utilizza il framework dell'estensione per scaricare i pacchetti pertinenti nel POS. Questi pacchetti vengono scaricati quando il POS viene chiuso e riaperto. Pertanto, quando Microsoft rilascia nuove funzionalità per il servizio, l'app POS deve essere chiusa e riaperta.

Utilizzando questo servizio, i responsabili punto vendita possono creare e pubblicare facilmente il programma lavori settimanale dei loro punti vendita. I lavoratori dei punti vendita potranno quindi visualizzare rapidamente il proprio programma e quello dei loro colleghi. In tal modo, possono sapere con chi lavoreranno durante i turni assegnati. I lavoratori dei punti vendita possono inoltre creare richieste di assenza, scambio turno e offerta di turno. Tutte queste richieste attivano un flusso di lavoro definito.

Durante un turno, i lavoratori dei punti vendita possono utilizzare la funzionalità di registrazione dell'entrata e dell'uscita che è integrata nei client POS. I dati vengono poi inviati alla sede centrale per l'elaborazione delle retribuzioni. La funzionalità di registrazione dell'entrata e dell'uscita è una funzione esistente del POS. Per ulteriori informazioni sull'impostazione e sugli scenari supportati, vedere [Ora di entrata e di uscita](retail-time-attendance.md).

## <a name="supported-scenarios"></a>Scenari supportati
In questa sezione vengono fornite ulteriori informazioni sugli scenari supportati.

- **Creare e pubblicare programmi**: il servizio Gestione della forza lavoro utilizza le autorizzazioni POS configurate nella sede centrale per stabilire se un lavoratore ha privilegi di un responsabile punto vendita. Solo i responsabili punto vendita possono creare e pubblicare programmi utilizzando l'operazione Gestione programmazione. I responsabili possono creare rapidamente un programma copiando e incollando un turno di lavoro esistente da un lavoratore a un altro lavoratore o importando un programma di una settimana precedente qualsiasi nella settimana corrente.

    Se un programma non è pubblicato, è in stato di bozza e appare diverso da un programma pubblicato. I responsabili punto vendita possono pubblicare un programma facendo clic sul pulsante **Pubblica** per qualsiasi settimana. Dopo la pubblicazione del programma di una settimana, le eventuali modifiche vengono pubblicate automaticamente. Esempi di modifiche includono l'aggiunta, l'eliminazione o la rettifica di turni di lavoro o assenze. I lavoratori dei punti vendita possono visualizzare solo i programmi pubblicati per varie settimane.
    
- **Creare e approvare le richieste**: i lavoratori dei punti vendita possono creare tre tipi di richieste:

    - Assenza
    - Scambio turno
    - Offerta di turno

    Tali richieste possono essere create utilizzando l'operazione per le richieste di programmazione. Ogni richiesta segue un flusso di lavoro definito e i lavoratori possono verificare facilmente lo stato corrente delle richieste.
    
    Le richieste di assenza sono inviate automaticamente al responsabile punto vendita per l'approvazione. Se sono presenti molteplici responsabili punto vendita, tutti i responsabili possono visualizzare una determinata richiesta, ma solo un responsabile può approvarla o rifiutarla. I tipi di assenza vengono configurati in Retail Headquartes utilizzando la pagina **Tipi di congedo e assenza** nel modulo **Vendita al dettaglio**. Dopo l'approvazione o il rifiuto di una richiesta da parte del responsabile punto vendita, la richiesta viene spostata nella scheda **Storico** per l'operazione relativa alle richieste di programmazione.
    
    Una richiesta di scambio turno o offerta di turno viene dapprima inviata al lavoratore a cui la richiesta è stata fatta. Il responsabile punto vendita può visualizzare la richiesta solo dopo che il lavoratore l'ha approvata. Pertanto, se il lavoratore rifiuta la richiesta di scambio turno o offerta di turno, il responsabile non può visualizzarla. Il lavoratore che ha creato la richiesta può anche annullarla prima dell'approvazione o del rifiuto del responsabile.

- **Visualizzare i lavoratori attivi del punto vendita nella visualizzazione del programma**: quando un lavoratore viene aggiunto a un punto vendita, ad esempio associandolo alla rubrica dei dipendenti del punto vendita, il lavoratore diventa disponibile per la programmazione nel servizio Gestione della forza lavoro. Un processo batch ricorrente denominato **Elabora dati lavoratore per la gestione forza lavoro** viene eseguito nella sede centrale. Questo processo prepara le associazioni punto vendita-lavoratore che saranno inviate al servizio Common Data Service (CDS).

    Lo stesso processo viene utilizzato quando un lavoratore viene rimosso da un punto vendita. Tuttavia, il lavoratore che viene rimosso viene ancora visualizzato per le settimane passate, correnti e future se un'assenza o turno di lavoro attivo è assegnato a quel lavoratore. Pertanto, a meno che tali turni di lavoro e assenze siano eliminati, il lavoratore rimosso continuerà a essere visualizzato per quelle settimane.


---
title: Ricerca per navigazione
description: "In questo articolo viene descritto come utilizzare la funzionalità di ricerca per accedere alle pagine di Microsoft Dynamics 365 per le operazioni."
author: aneesmsft
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 25991
ms.assetid: eef0676f-c4b1-490e-a032-e9c8580f3fea
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 87fed576f8cf358520d94f5cd5b326ff9801913a
ms.lasthandoff: 03/31/2017


---

# <a name="navigation-search"></a>Ricerca per navigazione

In questo articolo viene descritto come utilizzare la funzionalità di ricerca per accedere alle pagine di Microsoft Dynamics 365 per le operazioni.

Dynamics 365 per le operazioni sono disponibili funzionalità per si effettua la selezione dei settori e verticali. L'applicazione include una serie di aree e pagine utile per eseguire diverse attività. Per trovare rapidamente le pagine che è necessario completare le attività, utilizzare la funzionalità di ricerca di navigazione. Per utilizzare questa funzionalità, fare clic sull'icona **Cerca** per visualizzare la casella **Cerca**. È possibile quindi digitare una o più parole nella casella. Il sistema cerca immediatamente nell'applicazione le pagine che corrispondono alle parole immesse. Ad esempio, è possibile immettere "fattura fornitore" come input, quindi il sistema visualizza i risultati che corrispondono all'input. **Nota:** la casella **Cerca** consente di trovare e visualizzare le pagine. Non aiuterà a cercare azioni o dati specifici. 

[casella di ricerca![(]. /media/search-box.png)](. /media/search-box.png) Che la funzionalità di ricerca di navigazione anche come estensione in modo da individuare rapidamente a una pagina specifica. Ad esempio, se si dispone del ruolo di addetto alla contabilità fornitori che utilizza spesso ** giornale di registrazione pagamenti ** la pagina, è possibile immettere "il giornale di registrazione pagamenti nella casella di ricerca. Poiché l'input viene esattamente di verifica per il titolo della pagina, nella pagina vengono visualizzate nella parte superiore dei risultati della ricerca e è possibile passare rapidamente. 

[cercare-per-pagamento- giornale di registrazione![(]. /media/searching-for-payment-journal.png)](. /media/searching-for-payment-journal.png) 

L'elenco di risultati della ricerca visualizzati il titolo della pagina nonché il percorso di navigazione. Ciò consente di informare l'utente sulla posizione della pagina nell'applicazione. Consente anche di fare una distinzione tra due o più pagine simili nei risultati. Durante la ricerca di una pagina l'input viene abbinato al titolo della pagina, nonché al relativo percorso di navigazione. Ad esempio, si immette "contabilità clienti" ** ** la casella di ricerca, vedrete i risultati delle pagine disponibili all'utente nell'area Contabilità clientiProduzione suanche se i titoli della pagina non includono la parola "a credito." 

[![ricerca-per a Word- a credito (]. /media/search-for-the-word-receivable.png)](. /media/search-for-the-word-receivable.png) 

In una prospettiva di protezione e amministrazione, superfici delle funzionalità di ricerca di spostamento solo:

-   Pagine abilitate nella configurazione corrente (tramite chiavi di configurazione).
-   Pagine cui l'utente può accedere in base al ruolo utente.

L'elenco dei risultati della ricerca è limitato a 10 voci. Se nei risultati non è presente cosa si ricerca, è necessario provare a ridefinire o aggiornare l'input. Dal punto di vista dello sviluppo, la funzionalità di ricerca di navigazione è molto semplice da utilizzare poiché di fatto non esiste alcun ritardo tra la distribuzione delle voci di menu e la loro capacità di apparire nei risultati della ricerca. A condizione che il collegamento alle voci di menu sia stabilito sia tramite il pannello di navigazione che il dashboard, tali voci diventeranno automaticamente esplorabili. La funzionalità di ricerca di navigazione include inoltre una funzione molto richiesta dai power user: la capacità di esplorare rapidamente una pagina in base al nome tecnico del modulo. Molti utenti hanno così tanta familiarità con il sistema che conoscono i nomi esatti dei moduli con cui lavorano. Se si è uno di questi utenti, è possibile immettere **modulo:** seguito dal nome del modulo che si ricerca. Ad esempio, se si immette **modulo: vendinvoice**, i risultati della ricerca mostreranno tutte le pagine in cui il nome del modulo inizia con **vendinvoice**. 

[ricerca-per- modulo per vendinvoice![(]. /media/search-for-form-vendinvoice.png)](. /media/search-for-form-vendinvoice.png)



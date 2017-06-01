---
title: Distribuzioni contabili
description: Questo articolo fornisce informazioni sulle distribuzioni contabili e descrive le opzioni disponibili per elaborarle. Le distribuzioni contabili vengono utilizzate per allocare gli importi monetari per un documento di origine in conti CoGe specifici.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AccountingDistribution
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 17231
ms.assetid: 9030355d-8e6e-408b-9e7d-7b346eaa652c
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 96ff984310ce5877c37a22f182064a5038d71752
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="accounting-distributions"></a>Distribuzioni contabili

[!include[banner](../includes/banner.md)]


Questo articolo fornisce informazioni sulle distribuzioni contabili e descrive le opzioni disponibili per elaborarle. Le distribuzioni contabili vengono utilizzate per allocare gli importi monetari per un documento di origine in conti CoGe specifici. 

Le distribuzioni contabili sono una funzionalità per tutto il programma che viene utilizzata ed estesa da ciascun documento di origine, ad esempio un ordine fornitore, una fattura fornitore, una nota spese e una fattura a testo libero. Per impostazione predefinita, una distribuzione contabile viene generata per ogni riga e importo monetario del documento di origine ed è condizionatamente abilitata per la modifica. 

> [!Note] 
> Alcuni documenti supportano anche gli importi monetari del documento di intestazione, ad esempio le spese degli ordini e delle fatture. 

Le funzionalità di distribuzione contabile generiche forniscono le seguenti opzioni per elaborare le distribuzioni contabili:

-   **Distribuisci importi**: consente di visualizzare e modificare le distribuzioni contabili per una singola riga o intestazione del documento e per tutte le righe figlio, ad esempio imposte o spese.
    -   Per le distribuzioni superiori di importo monetario (distribuzioni padre), il conto principale e le dimensioni finanziarie potrebbero essere modificabili direttamente nel controllo di voci segmentato nella griglia. Il prezzo esteso è un esempio tipico di distribuzione padre.
    -   Gli importi delle distribuzioni si basano sulla valuta di scadenza del documento. In genere, questa valuta è la valuta della transazione. Gli importi della valuta di dichiarazione e di contabilità vengono generati nell'ambito della contabilità secondaria.
    -   Le distribuzioni visualizzano la data contabile e l'evento contabile. In genere, per l'evento contabile viene impostato **Nessuno** finché il documento non è pubblicato/inserito nel giornale di registrazione. A questo punto, l'evento contabile verrà impostato su **Originale**. Dopo la registrazione delle distribuzioni non è possibile modificare le distribuzioni.
    -   Il pulsante **Dividi** potrebbe essere abilitato per le distribuzioni padre. **Dividi** genera le nuove distribuzioni contabili e la divisione può essere basata sulla percentuale, l'importo o la quantità.
    -   Il pulsante**Distribuisci equamente** può essere utilizzato congiuntamente a **Dividi** per allocare automaticamente ed equamente l'importo in tutte le distribuzioni.
    -   Il pulsante **Reimposta** può essere abilitato per le distribuzioni padre quando esiste più di una distribuzione. **Reimposta** inverte qualsiasi modifica manuale alla distribuzione eliminando tutte le distribuzioni esistenti e rigenerando le distribuzioni predefinite.
    -   Qualsiasi distribuzione figlia, ad esempio sconto, spesa e IVA, segue sempre la distribuzione padre. È possibile visualizzare la relazione padre/figlia in **Riferimento** &gt; **Informazioni padre**.
    -   Il conto principale e la dimensione finanziaria potrebbero essere modificabili anche per i figli.
    -   Le dimensioni finanziarie nelle distribuzioni contabili seguono un modello predefinito che un documento può estendere. Per ulteriori informazioni, vedere gli articoli correlati.
    -   Le distribuzioni di scostamento possono essere generate negli scenari corrispondenti, ad esempio con corrispondenza tra una fattura fornitore e un ordine fornitore. È possibile visualizzare le relazioni corrispondenti tra distribuzione contabile in **Riferimento** &gt; **Informazioni documento**.
    -   Il pulsante **Corretto** viene visualizzato ed è abilitato per i documenti che supportano le correzioni. **Corretto** crea nuove distribuzioni. Innanzitutto, distribuzioni vengono create per stornare le distribuzioni originali. Queste distribuzioni non possono essere modificate. A questo punto, nuove distribuzioni contabili correte vengono create. Le distribuzioni possono essere modificate se le distribuzioni originali potevano essere modificate.
    -   Il pulsante**Dettagli progetto** è abilitato come estensione quando una riga è correlata a un progetto. Le distribuzioni contabili di progetto consentono di modificare dettagli, quali la fonte di finanziamento e la proprietà riga.
    -   È possibile visualizzare lo stato contabile del documento corrente in **Riferimento**. Lo stato è per l'intero documento e indica se il documento è in corso o completato.
-   ** Visualizza distribuzioni**: consente di visualizzare le distribuzioni contabili per tutte le righe e gli importi monetari del documento. Non è possibile modificare le distribuzioni contabili da questa visualizzazione.


Per ulteriori informazioni, vedere [Distribuzioni contabili e sugli inserimenti nel giornale di registrazione secondario per le fatture a testo libero](accounting-distributions-subledger-journal-entries-vendor-invoices.md).




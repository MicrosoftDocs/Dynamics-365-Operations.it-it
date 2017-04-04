---
title: Ricerca di azioni
description: "In questo articolo viene descritto la funzionalità di ricerca di azione in Microsoft Dynamics 365 per le operazioni. La ricerca di azione vengono fornite le informazioni ed eseguire le azioni in una pagina."
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 689d8f9fb0501c5007db21d41f126737af77b89e
ms.lasthandoff: 03/31/2017


---

# <a name="action-search"></a>Ricerca di azioni

In questo articolo viene descritto la funzionalità di ricerca di azione in Microsoft Dynamics 365 per le operazioni. La ricerca di azione vengono fornite le informazioni ed eseguire le azioni in una pagina.

<a name="introduction"></a>Introduzione
------------

Le pagine di Microsoft Dynamics 365 per le operazioni principalmente espongono i controlli presenti nei riquadri azioni, il riquadro azioni standard visualizzato nella parte superiore della pagina che le barre degli strumenti che verranno visualizzati in diverse aree della pagina. Nelle versioni precedenti, una funzionalità chiave suggerimenti si è passato da accedere rapidamente a qualsiasi pulsante nel riquadro azioni premendo la chiave di quindi ALT una serie di lettere. 

![[] (keyTipsAX6. /media/keytipsax6.png)](. /media/keytipsax6.png), Ma la versione corrente di Dynamics 365 per le operazioni, suggerimenti chiave non saranno più disponibili ma sono stati sostituiti dalla funzionalità di ricerca di azione. La nuova funzionalità consente di trovare rapidamente ed eseguire un pulsante da qualsiasi riquadro azioni visibile.

## <a name="using-action-search"></a>Utilizzo della ricerca azioni
Per utilizzare la funzionalità di ricerca azioni, effettuare le operazioni indicate di seguito.

1.  Nel riquadro azioni fare clic nel campo di ** ricerca azioni**. (Il campo di **ricerca azioni** contiene un'icona a forma di lente d'ingrandimento).
2.  Digitare integralmente o parzialmente il nome dei pulsanti da eseguire. È inoltre possibile eseguire la ricerca utilizzando le parole dal percorso dei pulsanti "". Per ulteriori informazioni, vedere la sezione successiva dell'articolo). In genere, verrà visualizzato un pulsante nella parte superiore dei risultati sono elencati dopo aver immesso due - quattro caratteri.
3.  Individuare ed eseguire il pulsante nell'elenco risultati (mediante il mouse o tastiera).

Dopo che il pulsante viene eseguito, lo stato attivo torna all'ultima posizione nella pagina, in modo che sia possibile continuare a lavorare. 

[azione-ricerca- campo![(]. /media/action-search-field.png)](. /media/action-search-field.png)

È inoltre possibile avviare la ricerca azioni premendo i tasti CTRL+/ o ALT+Q. Premere di nuovo i tasti di scelta rapida per riportare lo stato attivo all'ultima posizione nella pagina.

## <a name="understanding-the-results-list"></a>Interpretazione dell'elenco dei risultati
Spesso, in Dynamics 365 per le operazioni, è necessario conoscere e l'ubicazione nel contesto di un pulsante completamente per comprendere lo scopo di tale pulsante. Di conseguenza, informazioni aggiuntive sono indicate da ciascun articolo nell'elenco di risultati, che consentono di acquisire familiarità sia i pulsanti visualizzati nell'elenco. In particolare, verrà visualizzato "il percorso" del pulsante. Questo percorso può includere le etichette dei seguenti elementi di interfaccia utente, a seconda dei casi:

-   Scheda del riquadro azioni
-   Gruppo pulsanti
-   Pulsante di menu (se il pulsante è all'interno di un pulsante di menu)
-   Separatore di menu (se il pulsante è interno un gruppo denominato all'interno di un pulsante di menu)
-   Gruppo o scheda nella pagina (ad esempio, il nome di una scheda dettaglio)

Ad esempio, l'utente digita **tot** nel campo di **ricerca azioni** ed esamina l'elenco risultati. La prima voce, per un pulsante denominato ** totali **, viene evidenziata. Il percorso dei pulsanti ** ordine cliente ** &gt; ** di visualizzazione ** viene anche specificato. ** Ordine cliente ** parte del percorso corrisponde ** ordine cliente ** la scheda nel riquadro azioni e ** visualizzazione ** parte del percorso corrisponde ** visualizzazione ** al gruppo nella scheda. Analogamente, il percorso ** sconto totale ** il pulsante (** vendita ** &gt; ** calcoli **) viene comunicato che questo pulsante è disponibile in ** ** calcola il gruppo ** la vendita ** scheda del riquadro azioni. Di conseguenza, queste informazioni consentono di acquisire familiarità sia presente il pulsante verrà attivato dalla ricerca di azione (se si seleziona il pulsante nell'elenco dei risultati). 

[azione-ricerca-campo-con- dati![(]. /media/action-search-field-with-data.png)](. /media/action-search-field-with-data.png) 

Nell'esempio precedente, la ricerca azioni ha mostrato i risultati dal riquadro azioni standard nella parte superiore della pagina. Tuttavia, la ricerca azioni mostra anche i risultati delle barre degli strumenti visibili situate in altri punti della pagina. Ad esempio, la ricerca ** scorte disponibili abbottonate ** è situato ** righe di ordine cliente ** clic. In questo caso, il percorso del pulsante nell'elenco di risultati (** l'ordine cliente in ** &gt; ** magazzino ** &gt; ** visualizzazione **) viene comunicato che questo pulsante è disponibile in ** ** visualizzazione intestazione ** magazzino ** sul pulsante di menu ** righe di ordine cliente ** clic. 

[![scorte disponibili (-). /media/on del inventory.png -)](. /media/on del inventory.png -)

## <a name="action-search-vs-navigation-search"></a>Confronto tra ricerca di azioni e ricerca di navigazione
Benché che la ricerca di azione viene utilizzata per trovare e azioni eseguite in una pagina, è presente un meccanismo separato di ricerca per cercare e spostarsi nelle pagine di Dynamics 365 per le operazioni. Per ulteriori informazioni sulla funzionalità, vedere [] ricerca di spostamento () navigation-search.md articolo.



---
title: Utilizzare le ricerche per trovare informazioni
description: "In Microsoft Dynamics 365 for Finance and Operations molti campi presentano ricerche per semplificare la ricerca del valore corretto o desiderato. Alle ricerche sono stati aggiunti diversi miglioramenti che rendono questi controlli più utilizzabili e gli utenti più produttivi. In questo argomento si apprenderanno le nuove funzionalità di ricerca e si riceveranno alcuni suggerimenti utili per l'utilizzo ottimale delle ricerche nel sistema."
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269934
ms.assetid: f20cbd2c-14e0-47e7-b351-8e60d3537f96
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: a5d0a9edd2cb5747fc799c6fdca45dd9ba5720f7
ms.contentlocale: it-it
ms.lasthandoff: 06/13/2017

---

# <a name="use-lookups-to-find-information"></a>Utilizzare le ricerche per trovare informazioni

[!include[banner](../includes/banner.md)]


In Microsoft Dynamics 365 for Finance and Operations molti campi presentano ricerche per semplificare la ricerca del valore corretto o desiderato. Alle ricerche sono stati aggiunti diversi miglioramenti che rendono questi controlli più utilizzabili e gli utenti più produttivi. In questo argomento si apprenderanno le nuove funzionalità di ricerca e si riceveranno alcuni suggerimenti utili per l'utilizzo ottimale delle ricerche nel sistema.  

<a name="responsive-lookups"></a>Ricerche responsive
------------------

Nelle versioni precedenti di Finance and Operations, interagendo con un controllo di ricerca, un utente deve eseguire un'azione esplicita per aprire il menu a discesa. Ciò poteva verificarsi digitando un asterisco (\*) nel controllo per filtrare la ricerca sulla base del valore corrente del controllo, facendo clic sul pulsante a discesa oppure tramite i tasti di scelta rapida **Alt**+**Freccia GIÙ**. I controlli della ricerca sono stati modificati nei seguenti modi per allinearli meglio alle pratiche Web in essere:

-   i menu a discesa di ricerca si apriranno ora automaticamente dopo una piccola pausa nella digitazione, con il contenuto dei menu a discesa filtrati in base al valore del controllo di ricerca.
    -   Il vecchio comportamento di apertura automatica della casella a discesa dopo l'immessione di un asterisco (\*) è obsoleto.
-   Dopo che il menu a discesa di ricerca si è aperto, si verificherà quanto segue:
    -   Il cursore resterà nel controllo di ricerca (anziché spostare lo stato attivo nel menu a discesa) in modo che sia possibile continuare ad apportare modifiche al valore del controllo. Tuttavia, l'utente può ancora utilizzare la **Freccia Su** e la **Freccia GIÙ** per modificare le righe del menu a discesa e Invio per selezionare la riga corrente nel menu a discesa.
    -   Il contenuto del menu a discesa cambierà dopo le eventuali modifiche che verranno apportate al valore del controllo di ricerca.

Ad esempio, si consideri un campo di ricerca denominato **Città**. 

Quando lo stato attivo è nel campo **Città**, è possibile avviare la ricerca della città desiderata digitando alcune lettere, ad esempio "col".  Dopo aver smesso di digitare, la ricerca ai aprirà automaticamente, filtrata su quelle città che iniziano con "col". 

[![typeaheadLookupExample](./media/typeaheadlookupexample.png)](./media/typeaheadlookupexample.png) 

A questo punto il cursore è ancora nel campo di ricerca. Se si continua a digitare in modo che il valore sia "colonna", il contenuto della ricerca cambierà automaticamente in base all'ultimo valore nel controllo. 

![updateFilterLookupExample](./media/updatefilterlookupexample.png) 

Sebbene lo stato attivo sia ancora nel controllo di ricerca, sarà possibile utilizzare anche i tasti **Freccia Su** e **Freccia GIÙ** per evidenziare la riga da selezionare. Se si preme **Invio**, la riga evidenziata verrà selezionata automaticamente nella ricerca e il valore del controllo verrà aggiornato. 

![changingSelectionLookup](./media/changingselectionlookup.png)

## <a name="typing-in-more-than-ids"></a>Digitare non solo gli ID
Quando si inseriscono i dati, per gli utenti è naturale tentare di identificare un'entità, ad esempio un cliente o un fornitore, in base al nome anziché a un identificatore che rappresenta l'entità. Nella versione corrente di Finance and Operations molte (ma non tutte) ricerche consentono ora l'immissione di dati contestuali. Questa potente funzionalità consente all'utente di immettere l'ID o il nome corrispondente nel controllo di ricerca. 

Ad esempio, si consideri il campo **Conto cliente** quando si crea un ordine cliente. Questo campo mostra l'**ID conto** per il cliente, ma un utente preferirebbe in genere immettere un **Nome conto** anziché un **ID conto** per questo campo quando si crea un ordine cliente, ad esempio "Forest Wholesales" anziché "US-003".

Se l'utente iniziasse a immettere l'**ID conto** nel controllo di ricerca, il menu a discesa si aprirebbe automaticamente come descritto nella sezione precedente e l'utente vedrebbe la ricerca come indicato di seguito.

[![Ricerca contestuale quando viene immesso un ID conto cliente](./media/howtocontextuallookups-1.png)](./media/howtocontextuallookups-1.png)

Tuttavia, l'utente può immettere anche ora l'inizio di un **Nome conto**. Se viene rilevato, l'utente visualizzerà la ricerca successiva. La colonna **Nome** diventa la prima colonna della ricerca e la ricerca viene ordinata e filtrata in base alla colonna **Nome**.

[![Ricerca contestuale quando viene immesso il nome di un cliente](./media/howtocontextuallookups-2.png)](./media/howtocontextuallookups-2.png)

## <a name="using-grid-column-headers-for-more-advanced-filtering-and-sorting"></a>Utilizzo delle intestazioni di colonna della griglia per una modalità di filtro e ordinamento più avanzata
Le opzioni avanzate di ricerca discusse nelle due sezioni precedenti migliorano notevolmente la capacità di un utente di spostarsi tra le righe di una ricerca nel campo **ID** o **Nome** in base al criterio "inizia con". Tuttavia, sono presenti situazioni in cui un filtro più avanzato (o un ordinamento) è necessario per individuare la riga corretta. In queste situazioni l'utente deve utilizzare le opzioni di filtro e ordinamento nelle intestazioni di colonna della griglia della ricerca. Ad esempio, si consideri un dipendente, che deve individuare il "cavo" esatto come prodotto, mentre inserisce una riga di ordine cliente. Digitare "cavo" nel controllo **Numero articolo** non è utile, perché non sono presenti nomi di prodotto che iniziano con "cavo". 

![emptyitemlookup](./media/emptyitemlookup.png) 

In questo caso, l'utente deve annullare il valore del controllo di ricerca, aprire il menu a discesa di ricerca e filtrare il menu a discesa in base all'intestazione di colonna della griglia, come indicato di seguito. Un utente con il mouse (o toccando) può fare semplicemente clic (o toccare) qualsiasi intestazione di colonna per accedere a opzioni di filtro e ordinamento per la colonna. Per un utente che usa la tastiera, l'utente deve semplicemente premere **Alt**+**Freccia** **GIÙ** una seconda volta per spostare l'elemento attivo nel menu a discesa, dopodiché può utilizzare il tasto TAB per passare alla colonna corretta e premere **Ctrl**+**G** per aprire il menu a discesa dell'intestazione di colonna della griglia. 

[![gridfilteritemlookup](./media/gridfilteritemlookup.png)](./media/gridfilteritemlookup.png) 

Dopo che il filtro è stato applicato (vedere l'immagine di seguito), l'utente può individuare e selezionare la riga come di consueto. 

![filtereditemlookup](./media/filtereditemlookup.png)





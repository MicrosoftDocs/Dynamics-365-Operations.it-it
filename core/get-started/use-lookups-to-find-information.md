---
title: Utilizzare le ricerche per trovare informazioni
description: "In Microsoft Dynamics 365 per le operazioni, molti campi presentano ricerche per semplificare facilmente a individuare il valore corretto o desiderato. Sono miglioramenti sono stati aggiunti alle ricerche che rendono questi controlli più riutilizzabili e rendono più utenti produttive. In questo argomento, imparerete sulle nuove funzionalità di ricerca e verrà restituito alcuni suggerimenti per ottenere per l&quot;utilizzo ottimale dalle ricerche nel sistema."
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 269934
ms.assetid: f20cbd2c-14e0-47e7-b351-8e60d3537f96
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 6a25593632575dcd71fa4a3c9cf5b83c9f8ecd39
ms.lasthandoff: 03/31/2017


---

# <a name="use-lookups-to-find-information"></a>Utilizzare le ricerche per trovare informazioni

In Microsoft Dynamics 365 per le operazioni, molti campi presentano ricerche per semplificare facilmente a individuare il valore corretto o desiderato. Sono miglioramenti sono stati aggiunti alle ricerche che rendono questi controlli più riutilizzabili e rendono più utenti produttive. In questo argomento, imparerete sulle nuove funzionalità di ricerca e verrà restituito alcuni suggerimenti per ottenere per l'utilizzo ottimale dalle ricerche nel sistema.  

<a name="responsive-lookups"></a>Cerca rispondenti
------------------

Nelle versioni precedenti di Dynamics 365 per le operazioni si interagisce con un controllo di ricerca, un utente deve eseguire l'azione espliciti per aprire il menu a discesa. Può essere digitando un asterisco (\*) di controllo per filtrare la ricerca basata sul valore corrente del controllo, facendo clic sul pulsante a discesa, oppure tramite ** ALT **+** sulla freccia ** scorciatoia tasti. Controlla di ricerca sono stati modificati nei seguenti modi meglio classificare con le pratiche in vigore Web:

-   Il menu a discesa di ricerca verrà visualizzato automaticamente dopo che una leggera pausa in ore, al contenuto del menu a discesa filtrati in base al valore del controllo di ricerca.
    -   Si noti che il vecchio comportamento di apertura pianificazione automatica a discesa dopo aver immesso un asterisco (\*) è stato deprecato.
-   Dopo la ricerca dal menu a discesa è aperto, verrà eseguito il seguente:
    -   Il cursore resterà in Controllo shop ricerca (anziché di l che sposta il menu a discesa) in modo che sia possibile continuare ad apportare modifiche al valore del controllo. Tuttavia, è comunque possibile utilizzare ** sulla freccia ** e ** sulla freccia ** modificare le righe dal menu a discesa e immettere per selezionare la riga corrente dal menu a discesa.
    -   Il contenuto del menu a discesa rettifica dopo che tutte le modifiche di lieve al valore del controllo di ricerca.

Ad esempio, si un campo di ricerca denominato ** ** città. 

Quando dello stato attivo in ** città ** sistemi, è possibile avviare la ricerca la città in cui si desidera digitando le lettere, ad esempio "rappresenta il passaggio".  Dopo aver smettete di immettere, la ricerca verrà visualizzato automaticamente, filtrato città a quelli che iniziano con la il passaggio". 

[typeaheadLookupExample![(]. /media/typeaheadlookupexample.png)](. /media/typeaheadlookupexample.png) 

A questo punto, il cursore è ancora nel campo di ricerca. Se continuare a immettere in modo dal valore è "colum", i contenuti di ricerca rettificare automaticamente in base all'ultimo valore nel controllo. 

![updateFilterLookupExample](./media/updatefilterlookupexample.png) 

Anche se l'elemento attivo è ancora in Controllo di ricerca, è possibile utilizzare ** sulla freccia ** o ** sulla freccia ** le chiavi per evidenziare la riga desiderata. Se si preme ** immettere ** la riga selezionata verrà immessa automaticamente la ricerca e il valore di controllo verrà aggiornato. 

![changingSelectionLookup](./media/changingselectionlookup.png)

## <a name="typing-in-more-than-ids"></a>Digitando in più degli ID
In immettere dati, per gli utenti è naturale si tenta di identificare un'entità, ad esempio un cliente o un fornitore, in base al nome anziché un identificatore all'entità. Nella versione corrente di Dynamics 365 per le operazioni, molte (ma non tutte le ricerche ore) consentono l'immissione dei dati contestuale. Questa funzionalità di consente all'utente immettere l'identificazione o il nome corrispondente nel controllo di ricerca. 

Ad esempio, si ** conto cliente ** il campo quando si crea un ordine cliente. Mostra ** identificazione del conto ** per il cliente, ma un utente preferirebbe in genere immettere le ** nome del conto ** anziché ** identificazione del conto ** per il campo quando si crea un ordine cliente, ad esempio "la foresta comercia" anziché "US-003".

Se l'utente avviato per immettere le ** identificazione del conto ** il controllo di ricerca, il menu a discesa è aprisse automaticamente come descritto nella sezione precedente e l'utente vedesse la ricerca come indicato di seguito.

[contestuale![ricerca![quando un ID account cliente viene immessa (]. /media/howtocontextuallookups-1.png)](. /media/howtocontextuallookups-1.png)

Tuttavia, l'utente può ora possibile immettere la data di inizio di l ** nome del conto e **. Se è ubicato, quindi l'utente potrà visualizzare la ricerca successiva. Avviso come ** nome ** la colonna viene spostata dalla prima colonna della ricerca e come la ricerca viene ordinata e filtrata in base ** ** nome nella colonna.

[contestuale![ricerca![quando un nome cliente (]. /media/howtocontextuallookups-2.png)](. /media/howtocontextuallookups-2.png)

## <a name="using-grid-column-headers-for-more-advanced-filtering-and-sorting"></a>Utilizzo delle intestazioni di colonna della griglia per il filtro e ordinamento più avanzate
I potenziamenti di ricerca discussi nelle due sezioni precedenti di migliorare notevolmente la capacità di un utente di accedere le righe in una ricerca in base a "inizia con" la ricerca ** di identificazione ** o ** nome ** sistemi nella ricerca. Tuttavia, sono presenti situazioni in cui più filtro avanzato (o ordini) è necessario individuare la riga corretta. In queste situazioni, le necessità utente di utilizzare il filtro e le opzioni di ordinamento nelle intestazioni di colonna della griglia nella ricerca. Ad esempio, si un dipendente che immette una riga di ordine cliente che deve individuare il cliente potenziale "" a destra del prodotto. Il cliente potenziale "" digitante ** numero di articolo ** il controllo non è utile, perché non sono presenti nomi prodotti che iniziano con la potenziale." 

![emptyitemlookup](./media/emptyitemlookup.png) 

In questo caso, le necessità utente di annullare il valore del controllo di ricerca, quindi aprire il menu a discesa di ricerca e filtrano il menu a discesa in base all'intestazione di colonna della griglia, come indicato di seguito. Un utente singolo tocco o del mouse) può scegliere semplicemente () o tocco qualsiasi intestazione di colonna per accedere a opzioni di filtro e ordinamento per la colonna. Per un utente tastiera, l'utente deve fornire ** premere ALT **+** il drill-down ** ** freccia ** una seconda volta immettere l'elemento attivo dal menu a discesa, di scadenza che l'utente può catalogare la colonna corretta quindi premere CTRL ** **+** G ** per aprire il menu a discesa di intestazione di colonna della griglia. 

[gridfilteritemlookup![(]. /media/gridfilteritemlookup.png)](. /media/gridfilteritemlookup.png) 

Dopo che il filtro applicato (vedere l'immagine di seguito), sarà possibile individuare e selezionare la riga come di consueto. 

![filtereditemlookup](./media/filtereditemlookup.png)



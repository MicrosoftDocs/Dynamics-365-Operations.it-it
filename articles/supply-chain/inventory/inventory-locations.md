---
title: Ubicazioni di magazzino
description: Le ubicazioni di magazzino vengono utilizzate con l'immagazzinaggio base (WMS I) per determinare dove vengono immagazzinati e dove vengono prelevati gli articoli in un magazzino WMS.
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSLocation
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2134
ms.assetid: 69bf6922-4151-447f-b678-4ba95637f54c
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 11be82682fc870cb21959d9e531ff8bf67993fa3
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---

# <a name="inventory-locations"></a>Ubicazioni di magazzino

[!include [banner](../includes/banner.md)]

Le ubicazioni di magazzino vengono utilizzate con l'immagazzinaggio base (WMS I) per determinare dove vengono immagazzinati e dove vengono prelevati gli articoli in un magazzino WMS.

Questo argomento si applica alle funzionalità nel modulo Gestione inventario. Non si applica alle funzioni nel modulo Gestione magazzino.

Il termine ubicazione identifica la posizione da cui vengono stoccati e prelevati gli articoli.

Per ciascuna ubicazione è inoltre possibile specificare la posizione in cui vengono inseriti gli articoli. Per impostazione predefinita, questi due valori sono corrispondenti. Gli articoli in genere vengono inseriti e prelevati dallo stesso lato di un'ubicazione. Esistono tuttavia alcune eccezioni. Gli articoli immagazzinati in scaffali live storage ad esempio vengono inseriti da una sezione e prelevati da un'altra. L'input principale è costituito dal nome dell'ubicazione, in genere determinato in base alle coordinate magazzino, sezione, scaffale, ripiano e contenitore. Il nome o ID può essere immesso manualmente o generato dalle coordinate dell'ubicazione, ad esempio 01-02-03-4 per sezione 1, scaffale 2, ripiano 3, contenitore 4 nella pagina Ubicazioni di magazzino.
Proprietà dell'ubicazione

A un'ubicazione sono associate le seguenti caratteristiche:
-   Dimensione (altezza, larghezza, profondità e quindi volume)
-   Magazzino, Sezione, Scaffale, Ripiano e Ubicazione contenitore
-   Tipo di ubicazione (ubicazione di stoccaggio, prelevante ubicazione, banchina di entrata, banchina di uscita, ubicazioni di entrata produzione, ubicazioni di controllo, o area di deposito kanban)

Nei sistemi in linea è possibile utilizzare un testo di verifica per controllare che l'operatore abbia selezionato l'ubicazione corretta per un articolo specifico. Questo testo di verifica può essere creato manualmente o per impostazione predefinita.

## <a name="sort-codes"></a>Codici di ordinamento
I codici di ordinamento consentono di ottimizzare la gestione delle righe di prelievo, in cui vengono fornite le informazioni richieste per il prelievo di articoli da magazzino, incluso l'ordine di prelievo. I codici di ordinamento possono essere specificati in base alla sezione e ad altre coordinate oppure possono essere assegnati manualmente per l'ubicazione.

## <a name="blocked-locations"></a>Ubicazioni bloccate
Talvolta è necessario bloccare un'ubicazione per un determinato periodo di tempo, ad esempio per consentire l'esecuzione di riparazioni. Altre volte è possibile che l'utente desideri bloccare solo l'entrata o l'uscita

## <a name="tree-structure"></a>Struttura ad albero

Nella pagina delle ubicazioni di magazzino è possibile visualizzare il layout di magazzino in una struttura ad albero in base alle coordinate delle ubicazioni di magazzino, in un formato di visualizzazione definito.

## <a name="maintain-inventory-locations-via-the-warehouse-form"></a>Gestire le ubicazioni di magazzino tramite modulo di magazzino

È possibile copiare le ubicazioni da un magazzino a un altro e creare le ubicazioni tramite la procedura guidata. Prima di eseguire la procedura guidata è necessario verificare di aver definito i nomi di posizione predefinita nella pagina di magazzino.



<a name="additional-resources"></a>Risorse aggiuntive
--------

[Creare un nuovo layout di magazzino (guida attività)](tasks/create-new-warehouse-layout.md)


---
title: Rilasciare gli ordini di produzione
description: Un ordine di produzione rilasciato è un ordine che è stato autorizzato per la produzione. Il termine Rilasciato viene utilizzato per descrivere uno stato del ciclo di vita dell'ordine di produzione, quando l'ordine di produzione è disponibile per l'esecuzione nello shop floor di produzione e per i processi di magazzino.
author: johanhoffmann
ms.date: 03/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdParmRelease
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2414
ms.assetid: 50c2257b-2924-44f5-b7c1-11f498092053
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 740ac516ffa01d8930aedabb9873834b07b7debf700dc61b14d93ac8d6dcd086
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718872"
---
# <a name="release-production-orders"></a>Rilasciare gli ordini di produzione

[!include [banner](../includes/banner.md)]

Un ordine di produzione rilasciato è un ordine che è stato autorizzato per la produzione. Il termine Rilasciato viene utilizzato per descrivere uno stato del ciclo di vita dell'ordine di produzione, quando l'ordine di produzione è disponibile per l'esecuzione nello shop floor di produzione e per i processi di magazzino.

## <a name="characteristics-of-the-released-state"></a>Caratteristiche dello stato Rilasciato

Lo stato **Rilasciato** è uno stato del ciclo di vita dell'ordine di produzione. Gli ordini di produzione nello stato **Rilasciato** sono disponibili per l'esecuzione nello shop floor di produzione e per i processi di magazzino. Lo stato **Rilasciato** ha le caratteristiche seguenti:

- Lo stato di un ordine di produzione può essere impostato su **Rilasciato** dall'ordine di produzione stesso o utilizzando un processo batch. L'ordine di produzione può anche essere aggiornato automaticamente negli ordini di produzione pianificati che vengono consolidati utilizzando il campo **Intervallo temporale stabilizzazione** nella pagina **Piano generale**.
- Lo stato **Rilasciato** indica agli operatori dello shop floor (operatori) di avviare l'esecuzione dei processi di produzione nello shop floor.
- I documenti di produzione, ad esempio schede del ciclo di lavorazione, processi di cicli di lavorazione e schede processi, forniscono informazioni sui processi di produzione e possono essere emessi.
- Per i materiali che vengono prenotati fisicamente, viene generato lavoro di magazzino per prelevare materiali per l'ordine di produzione.

## <a name="releasing-jobs-to-the-shop-floor"></a>Rilascio dei processi nel reparto produzione

Dopo che un ordine di produzione viene rilasciato, i processi di produzione correlati all'ordine sono visibili e pronti per la registrazione. Gli operatori possono effettuare le registrazioni dei processi, ad esempio l'avvio, l'interruzione e il completamento, nella pagina **Terminale schede processi** o nella pagina **Dispositivo schede processo**. Le informazioni su ora e quantità registrate verranno trasferite automaticamente dalle pagine di registrazione ai giornali di registrazione produzione per tenere traccia del tempo e della quantità consumati.

## <a name="route-cards"></a>Schede del ciclo di lavorazione

Una scheda ciclo di lavorazione fornisce una panoramica delle informazioni di impostazione del ciclo di lavorazione e delle operazioni e dei metodi di programmazione delle operazioni e dei processi.

## <a name="route-jobs"></a>Processi cicli di lavorazione

Un processo del ciclo di lavorazione elenca ciascun processo di un'operazione in dettaglio e include i tempi di attrezzaggio, elaborazione, attesa e trasporto. Ad esempio, un'operazione come la verniciatura, può richiedere singoli processi, quali il tempo di attrezzaggio, il tempo di esecuzione della verniciatura e il tempo di attesa per l'asciugatura.

## <a name="job-cards"></a>Schede processi

In una scheda processo sono elencati i singoli processi di una particolare operazione. Viene visualizzato un processo per pagina. I processi inclusi in una scheda processi e i relativi tempi stimati derivano dalle informazioni di impostazione dei cicli di lavorazione e delle operazioni. In una scheda processo, è possibile aprire **Righe giornale di registrazione produzione**, **scheda processo**. Il responsabile delle risorse operative fornisce un riscontro sul processo di produzione. In alcuni campi è possibile immettere le statistiche sui consumi e informazioni quali la quantità difettosa.

## <a name="warehouse-work-for-raw-material-picking"></a>Lavoro di magazzino per il prelievo di materie prime

Il lavoro per il prelievo delle materie prime viene generato durante il rilascio. Il lavoro viene generato solo per la quantità di materiale fisicamente prenotata per l'ordine di produzione prima che l'ordine è stato rilasciato. La seguente impostazione è necessaria per generare il lavoro del magazzino per il prelievo di materie prime:

- Una direttiva di ubicazione per il prelievo delle materie prime che determina l'ubicazione di magazzino da cui prelevare i materiali
- Un modello di ondata per le materie prime, in cui sono configurati i criteri per l'esecuzione di lavoro di magazzino
- Un'ubicazione di entrata produzione che determina l'ubicazione in cui stoccare i materiali

Quando si utilizzano ubicazioni controllate con targa, è possibile scegliere se prelevare la quantità ordinata o l'intera quantità disponibile per l'articolo durante l'elaborazione del lavoro di prelievo delle materie prime. Per impostare questa opzione:

1. Andare a **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati** e aprire l'articolo pertinente.
1. Espandere la Scheda dettaglio **Magazzino**.
1. Selezionare una delle seguenti opzioni per il campo **Prelievo materiale nelle ubicazioni targa**:
    - *Prelievo ordine*: solo la quantità ordinata deve essere prelevata.
    - *Gestione temporanea*: quando possibile la quantità totale disponibile nella targa deve essere prelevata. Affinché un lavoratore possa prelevare l'intera quantità della targa, la targa non deve contenere articoli combinati e non deve avere dimensioni combinate. Se la targa contiene dimensioni o articoli combinati, il prelievo verrà eseguito come se fosse impostato su *Prelievo ordine*.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
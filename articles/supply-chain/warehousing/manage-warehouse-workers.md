---
title: Gestione degli addetti magazzino
description: In questo articolo viene descritto come utilizzare l'app Dynamics 365 Supply Chain Management - Magazzino per agevolare il controllo e il monitoraggio del lavoro svolto dai dipendenti nei magazzini.
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmWorker, InventLocation, WHSLaborStandards, WHSWorker, WHSWorkTable, WHSWorkTableListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 72891
ms.assetid: feaa6f15-49d2-41f5-9b87-453463c52e4e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f0de87e10f9213838dd5e5436b8b5699b19547bf
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "2018623"
---
# <a name="manage-warehouse-workers"></a>Gestione degli addetti magazzino

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto come utilizzare l'app Dynamics 365 Supply Chain Management - Magazzino per agevolare il controllo e il monitoraggio del lavoro svolto dai dipendenti nei magazzini.

Se si utilizza la funzionalità di gestione magazzino, tutte le operazioni del lavoratore di magazzino sono indicate come *lavoro*. Ad esempio il lavoro di prelievo, spostamento e conteggio delle scorte disponibili viene registrato utilizzando i dispositivi mobili. Prima che un lavoratore di magazzino possa completare il lavoro, deve essere associato a un lavoratore nelle Risorse umane. Ogni account **lavoratore** può avere più utenti di lavoro di magazzino associati. Tali utenti di lavoro possono lavorare in magazzini diversi e possono avere diversi livelli di accesso a vari menu del dispositivo mobile. È possibile pensare agli utenti di lavoro di magazzino come a diversi accessi per il lavoratore selezionato. A ogni utente di lavoro è associato un magazzino predefinito e i flussi di lavoro specifici sono esposti dalle voci di menu disponibili per tale utente di lavoro. 

Per creare un nuovo utente di lavoro, nella pagina **Lavoratori** nella scheda **Generale** nella sezione **Magazzini**, fare clic su **Lavoratore**. È necessario specificare un ID utente, un nome utente, un magazzino predefinito e un nome menu. Questo menu viene caricato quando l'utente accede al portale dei dispositivi mobili del magazzino e consente di definire a quali voci di menu l'utente può accedere. 

Nelle impostazioni per ogni utente di lavoro, è possibile definire anche i flussi di lavoro specifici dei processi. Ad esempio, è possibile utilizzare il campo **Supervisore conteggio ciclo** per specificare se l'utente può elaborare le rettifiche alle discrepanze di conteggio ciclo di lavorazione durante un'operazione di conteggio oppure se queste rettifiche devono essere verificate da un'altra persona.

## <a name="defining-labor-standards"></a>Definizione degli standard manodopera
La pagina **Standard manodopera** consente di definire i metodi di calcolo utilizzati dal sistema per calcolare il tempo stimato che un tipo specifico di lavoro deve richiedere. La definizione può essere impostata un livello generico o a livello specifico. Ad esempio, è possibile definire il tempo che deve essere necessario per elaborare il prelievo di un ordine cliente per peso per una definizione specifica dell'unità quando viene utilizzato un processo specifico di prelievo. Contemporaneamente, è possibile registrare il tempo, in base a un altro metodo di calcolo, per l'esecuzione dell'operazione di stoccaggio delle scorte disponibili che vengono prelevate. 

Per abilitare gli standard manodopera definiti, è necessario selezionare l'opzione **Consenti standard manodopera** per ciascun magazzino in cui gli standard verranno utilizzati.

## <a name="monitoring-and-controlling-warehouse-work"></a>Monitoraggio e controllo del lavoro di magazzino
La pagina **Tutto il lavoro** consente di monitorare e gestire qualsiasi lavoro che viene pianificato, eseguito e completato. In questa pagina, è possibile aggiornare i diversi processi, ad esempio le assegnazioni dell'utente al lavoro di magazzino e la priorità di un lavoro. È anche possibile eseguire il drill-down dei dettagli relativi all'intestazione di lavoro e utilizzare le righe del lavoro per analizzare i processi previsti o completati del lavoro. 

Se si abilita l'opzione **Standard di lavoro**, è possibile visualizzare il tempo stimato calcolato per il lavoro. Quindi, quando il lavoro viene elaborato, il tempo effettivo verrà visualizzato anche per ciascuna operazione di lavoro. In questo modo, è possibile confrontare il calcolo del tempo stimato con quello del tempo effettivo. 

Inoltre, è possibile utilizzare il tempo stimato nelle regole per la suddivisione automatica del lavoro durante la creazione di un lavoro. In questo modo, è possibile equilibrare il carico di lavoro, in base al tempo previsto per completare l'attività. 

L'analisi di tempo utilizzato per elaborare gli elementi di lavoro consente di promuovere un miglioramento nell'efficienza dei lavoratori di magazzino. I report seguenti sono disponibili per agevolare l'analisi:

-   **Manodopera per utente**: il report mostra la produttività del lavoratore, in base alle ore effettive e al tempo previsto.
-   **Manodopera per tipo di transazione lavoro**: consente di utilizzare il report per esaminare le inefficienze in processi specifici del magazzino. Ad esempio, si nota che i prelievi per gli ordini di trasferimento richiedono più tempo nella settimana corrente rispetto a quelle precedenti. È quindi possibile utilizzare queste informazioni per un'analisi più approfondita.





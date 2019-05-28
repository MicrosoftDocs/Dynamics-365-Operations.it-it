---
title: Requisiti di impostazione della produzione
description: Questo articolo fornisce informazioni sui requisiti di impostazione per utilizzare un controllo produzione.
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdParameters, RouteOpr, RouteOprTable, WorkCalendarTable, WorkTimeTable, WrkCtrTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 55561
ms.assetid: 1953059f-478d-4706-b461-25b89ace5fc3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b811c11271097f4bb7910c34f7775955abba526d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559119"
---
# <a name="production-setup-requirements"></a>Requisiti di impostazione della produzione

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni sui requisiti di impostazione per utilizzare un controllo produzione. 

Il controllo produzione è integrato con funzionalità in altri moduli. Tale interconnettività consente di modificare gli ordini di produzione e di assicurarsi che vengano aggiornati automaticamente in tutti gli altri processi e calcoli correlati nel sistema. Le procedure di impostazione che seguono dovranno essere completate nell'ordine indicato.

## <a name="required-baseline-setup-in-other-modules"></a>Impostazioni di base obbligatorie in altri moduli
Prima di utilizzare il modulo Controllo produzione è necessario impostare alcune informazioni in altri moduli. L'impostazione include le seguenti attività:

-   Informazioni generali della società
-   Contabilità generale
-   Gruppi di articoli
-   Conti CoGe per i gruppi di articoli
-   Tabella degli articoli di magazzino nella gestione inventario.
-   Creazione di distinte base e di versioni DBA nel modulo Gestione inventario.

## <a name="required-calendar-and-resource-setup"></a>Risorse e calendario obbligatori
Prima di utilizzare il modulo Controllo produzione, aprire Amministrazione organizzazione e creare e definire il calendario e le risorse operative nel seguente ordine:

1.  **Modelli di orario di lavoro**: consente di impostare i modelli di orario di lavoro per definire i tempi disponibili per la programmazione della produzione.
2.  **Calendari**: consente di impostare calendari dell'orario di lavoro per definire i giorni dell'anno disponibili per la programmazione della produzione.
3.  **Gruppi di risorse**: consente di raggruppare le risorse operative per ottenere una panoramica di tutte le capacità disponibili quando si esegue la programmazione. Non è necessario impostare i gruppi di risorse prima di impostare le risorse operative. Tuttavia, è importante capire come raggruppare le risorse quando si imposta il modulo Controllo produzione.
4.  **Risorse**: consente di impostare le risorse operative per definire le risorse utilizzate per completare il processo di produzione e il piano di capacità.

## <a name="required-production-parameters-setup"></a>Impostazione dei parametri di produzione obbligatori
**Parametri di controllo produzione**: consente di impostare i parametri di produzione di base per definire la modalità con cui il sistema gestisce ed elabora gli ordini di produzione. Definire la modalità di creazione, valutazione, programmazione e uso degli ordini di produzione. È inoltre possibile selezionare il genere di riscontro desiderato e il modo in cui la contabilità industriale viene condotta.

## <a name="required-journal-name-identification"></a>Identificazione del nome del giornale
**Nomi giornale di registrazione produzione**: consente di specificare i nomi dei giornali di registrazione produzione utilizzati per memorizzare e registrare le transazioni.

## <a name="setup-if-you-use-operations"></a>Impostazione delle operazioni (se utilizzate)
Le operazioni rappresentano le attività specifiche eseguite per ottenere il prodotto finito. **Nota:** è necessario conoscere i tipi di attività necessarie per preparare l'articolo, nonché l'ordine e le priorità delle attività. È inoltre necessario conoscere le risorse coinvolte, e la quantità.

1.  **Operazioni**: consente di impostare le operazioni che rappresentano le attività che è necessario completare per produrre l'articolo finito.
2.  **Relazioni**: consente di impostare le relazioni operative per determinare le proprietà dettagliate. Per definire le relazioni operative, fare clic su **Relazioni** nella pagina **Operazioni**.

## <a name="setup-if-you-use-routes"></a>Impostazione dei cicli di lavorazione (se utilizzati)
Se si utilizzano i cicli di lavorazione, è necessario definire le operazioni per ogni ciclo di lavorazione produzione impostato. Il ciclo di lavorazione rappresenta il percorso dell'articolo da un'operazione all'altra, dall'inizio alla fine del processo di produzione.

1.  **Categorie costi**: impostare categorie costi per definire il costo orario dei processi specificati e degli orari impostati.
2.  **Gruppi di costi**: impostare gruppi di costi per creare e gestire tipi diversi di determinazione dei costi.
3.  **Gruppi di cicli di lavorazione**: consente di impostare i gruppi di cicli di lavorazione per definire i parametri relativi ai gruppi di cicli di lavorazione. È necessario impostare i gruppi di cicli di lavorazione prima di creare i singoli cicli.
4.  **Cicli di lavorazione**: impostare cicli di lavorazione produzione e definirne le impostazioni predefinite per controllare la programmazione e la determinazione dei costi e dei prezzi delle operazioni dei cicli, nonché le relazioni sullo stato di avanzamento del processo.
5.  **Cicli di lavorazione**: consente di impostare le versioni del ciclo di lavorazione per consentire variazioni dell'articolo nella produzione.

## <a name="optional-advanced-settings"></a>Impostazioni avanzate facoltative
1.  **Gruppi di produzione**: consente di impostare gruppi di produzione per stabilire delle relazioni tra l'ordine di produzione e i conti CoGe. I conti CoGe sono utilizzati per registrare o raggruppare gli ordini da dichiarare.
2.  **Pool di produzioni**: creare pool di produzioni per raggruppare ordini di produzione allo scopo di elaborare gli ordini di produzione urgenti o eliminare e registrare gruppi di ordini.
3.  **Proprietà**: consente di definire le proprietà per creare gli attributi speciali che è possibile assegnare alle risorse per controllare la sequenza delle produzioni. Questi attributi sono collegati al modello di orario di lavoro.





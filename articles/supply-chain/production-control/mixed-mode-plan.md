---
title: "Pianificazione in modalità mista: combinazione dell'approvvigionamento, discreto, di processo e snello"
description: Questo argomento fornisce informazioni sulla pianificazione in modalità mista.
author: cvocph
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 52931
ms.assetid: 2e8b5fd1-cee9-45da-a3ae-6961fb020b89
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 84a580ff6e8fe91de1ce0af315f322487dd8a3b2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814852"
---
# <a name="mixed-mode-planning---combine-discrete-process-and-lean-sourcing"></a>Pianificazione in modalità mista: combinazione dell'approvvigionamento, discreto, di processo e snello

[!include [banner](../includes/banner.md)]

Questo argomento fornisce informazioni sulla pianificazione in modalità mista. Nella pianificazione in modalità mista, è possibile modellare la supply chain in base al flusso di materiale. Dynamics 365 Supply Chain Management garantisce che il flusso di materiale segua i modelli, indipendentemente dai criteri di rifornimento selezionati (kanban, ordini di produzione, ordini fornitore, ordini batch o ordini di trasferimento). 

È possibile selezionare una strategia complessiva per la fornitura di un prodotto, indipendentemente dalla struttura di prodotto.  

Ad esempio, è possibile avere il controllo kanban nell'assemblaggio, in cui i materiali sono originati per l'area di assemblaggio da ordini di produzione, kanban, trasferimenti, ordini batch o una combinazione qualsiasi appropriata alle caratteristiche della supply chain e avere comunque una visibilità completa sulle forniture. Questa funzionalità porta a processi della supply chain ottimizzati e a una maggiore visibilità della supply chain.  

La granularità dei criteri di fornitura che vengono utilizzati nella programmazione generale dipende dalle dimensioni di immagazzinamento abilitate come dimensioni di copertura. Per consentire alla programmazione generale di controllare il rifornimento e la fornitura di diversi tipi di ubicazione (ad esempio, separando il reparto di produzione in differenti unità di produzione o separando i diversi tipi di materiali e di magazzini di prodotti finiti), è consigliabile abilitare Sito e Magazzino come dimensioni di copertura. In alternativa, è possibile omettere Magazzino come dimensione di copertura. In tal caso, quando si utilizza la gestione di magazzino avanzata, tutti i movimenti all'interno di un magazzino sono controllati dal lavoro di magazzino, mentre tutti i movimenti tra i magazzini possono essere controllati da kanban di prelievo.

## <a name="supply-policies"></a>Criteri di fornitura
La pianificazione in modalità mista determina il modo in cui un prodotto viene fornito e, in base alla fornitura, in che modo vengono emessi i requisiti derivati (consumo di articoli da una distinta base \[DBA\]). In base al tipo di ordine, il sistema fornisce automaticamente i materiali per soddisfare i fabbisogni.  

I criteri di fornitura possono essere definiti a livello di prodotto o a qualsiasi granularità che supporta i fabbisogni. Si definisce la granularità dei criteri di fornitura nella pagina **Impostazioni ordine predefinite**.  

I criteri di fornitura possono essere controllati in base al prodotto, le dimensioni articolo (configurazione, colore e dimensione), il sito e il magazzino. Questa impostazione viene effettuata nella pagina **Copertura articoli**.  

Il tipo di ordine predefinito controlla quale pianificazione generale degli ordini viene generata.  

Indipendentemente dalla modellazione della supply chain, Supply Chain Management supporta la combinazione di criteri di fornitura. È possibile avere ordini di produzione che vengono originati da kanban. In alternativa, è possibile avere un ordine batch che richiede che un prodotto venga fornito tramite trasferimenti o kanban.  

Supply Chain Management garantisce che il flusso di materiale segua il modello.  

Il magazzino per il prelievo del materiale viene assegnato dinamicamente in fase di esecuzione, una volta che sono stati definiti i criteri di fornitura.  

In genere, i kanban non vengono creati per le date future data la brevità del ciclo di vita di un kanban. Per mantenere la visibilità completa nella supply chain, abbiamo introdotto un nuovo concetto di pianificazione, il "kanban pianificato", che viene utilizzato per calcolare i requisiti derivati e aiuta a garantire che i requisiti siano originati in base alla stessa logica che viene utilizzata quando viene creato il kanban effettivo.  

La stessa logica è presente per tutti gli altri tipi di criteri di fornitura. Di conseguenza, la pianificazione a lungo termine dei materiali si basa sulla stessa logica che si prevede di applicare con gli ordini effettivi dopo l'approvazione della produzione e della fornitura.

## <a name="materials-allocation-cross-supply-policy--resource-consumption-on-boms"></a>Criteri di fornitura interaziendale per l'allocazione dei materiali: consumo di risorse nelle DBA
Il consumo di risorse è una funzionalità importante. Il consumo di risorse consente a un magazzino di prelevare i materiali da selezionare dinamicamente, in base ai criteri di fornitura (tipo di ordine) e semplifica inoltre la gestione dell'anagrafica.  

Il consumo di risorse richiede che il magazzino da cui vengono prelevati i materiali venga assegnato in base al modo in cui viene fornito il prodotto. In altre parole, in fase di esecuzione, il sistema trova le risorse che devono essere utilizzate per la produzione. In base a tali risorse, il sistema cerca quindi il magazzino di prelievo.  

Per il lavoro che non dipende dai criteri di fornitura, non è necessario modificare le informazioni nella distinta base se la fornitura viene modificata. Per le modifiche ad-hoc, Supply Chain Management garantisce che i materiali siano originati dal magazzino corretto.

## <a name="process-manufacturing--the-production-type"></a>Process manufacturing: tipo di produzione
Per una flessibilità completa in modalità mista, si consiglia di utilizzare DBA di tipo produzione per tutti i prodotti. È quindi possibile utilizzare gli ordini di produzione, i kanban, ordini di trasferimento, o ordini fornitore per fornire un prodotto. Per il process manufacturing, è necessario utilizzare un tipo di produzione **Formula**, **Co-prodotto**, **Sottoprodotto** o **Articolo pianificazione**. I kanban e gli ordini di produzione non possono essere utilizzati per questi tipi di produzione.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
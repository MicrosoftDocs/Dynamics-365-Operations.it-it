---
title: Programmazione operazioni
description: In questo argomento sono riportate informazioni sulla programmazione delle operazioni. Questo tipo di programmazione può essere utilizzato per ottenere una stima generale del processo di produzione nel tempo.
author: johanhoffmann
ms.date: 06/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdSchedule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 198073
ms.assetid: 12c28b11-80aa-4668-b15b-724cb24890bd
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e3c380297b56f615a6b285ef7daf1ecbd7bb420f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7574571"
---
# <a name="operations-scheduling"></a>Programmazione operazioni

[!include [banner](../includes/banner.md)]

In questo argomento sono riportate informazioni sulla programmazione delle operazioni. Questo tipo di programmazione può essere utilizzato per ottenere una stima generale del processo di produzione nel tempo.

È possibile programmare la produzione il livello di operazione e di processo. A differenza della programmazione processi, la programmazione delle operazioni non esplode le operazioni per il ciclo di lavorazione produzione in processi. Se si desidera includere più dettagli nella programmazione, ad esempio informazioni sulla capacità corrente, è possibile eseguire la programmazione processi dopo la programmazione delle operazioni. È inoltre possibile eseguire solo la programmazione processi. La programmazione dei processi viene solitamente utilizzata per programmare singoli processi del reparto produzione e viene eseguita immediatamente o entro un breve intervallo di tempo.

## <a name="components-of-operations-scheduling"></a>Componenti della programmazione delle operazioni
I principali componenti della programmazione delle operazioni sono la direzione di programmazione, la capacità delle risorse e l'ottimizzazione dei materiali. Utilizzando la programmazione delle operazioni è possibile ottenere i seguenti obiettivi:

-   Controllare il metodo di pianificazione programmando in avanti o a ritroso da una data specificata.
-   Ottimizzare l'utilizzo delle risorse programmando le produzioni in base alla capacità delle risorse. Questo approccio contribuisce anche a identificare quando utilizzare le risorse alternative.
-   Ottimizzare l'utilizzo di materiali programmando le produzioni in base alla disponibilità dei materiali richiesti.
-   Programmare e sincronizzare le produzioni di riferimento. Le date di produzione di riferimento vengono rettificate quando vengono apportate modifiche alla programmazione dell'ordine di produzione.

È necessario stimare il costo di un ordine di produzione prima di eseguire la programmazione delle operazioni. Se questa stima non è stata effettuata manualmente, verrà eseguita automaticamente prima dell'inizio del processo di programmazione delle operazioni. Una programmazione di operazioni specifica le informazioni seguenti:

-   Prodotto pianificato per lai produzione
-   Configurazione del prodotto
-   Quantità necessarie per la produzione
-   Date in cui la produzione inizierà e terminerà
-   Prenotazioni di capacità per le risorse che eseguono le attività di produzione

Tempo di attrezzaggio, tempo di elaborazione e tempo di esecuzione vengono impostati per le operazioni di produzione. Dopo aver eseguito la programmazione operazioni, lo stato dell'ordine di produzione è **Programmato** e tutte le operazioni sono programmate nell'ordine specificato dal ciclo di lavorazione produzione. Tuttavia, solo la durata dell'operazione viene considerata. Le ore di inizio e di fine non vengono programmate.

## <a name="scheduling-direction-and-date"></a>Data e direzione di programmazione
La direzione di programmazione è fondamentale ai fini del processo di programmazione. La produzione può essere programmata in avanti o a ritroso a partire da qualsiasi data, a seconda dei requisiti di tempi e programmazione.

-   **Avanti da data programmazione**: è possibile programmare la produzione per l'avvio al più presto possibile. La produzione può iniziare oggi, domani o in una qualsiasi data futura specificata. La produzione è programmata per proseguire in avanti nel tempo fino alla prima data di fine possibile.
-   **Indietro da data programmazione**: è possibile programmare la produzione per l'avvio il più tardi possibile. La programmazione a ritroso è basata sulla data in cui la produzione deve essere completata. La programmazione effettua un conteggio a ritroso dei tempi fino all'ultima data in cui è possibile far partire la produzione e comunque essere completata in tempo.

## <a name="resource-scheduling"></a>Programmazione risorse
Quando si esegue la programmazione di operazioni, ogni operazione del ciclo di lavorazione produzione è programmata per la risorsa specificata per l'operazione. Inoltre, la durata di ciascuna operazione viene specificata nel ciclo di lavorazione produzione. Se si specifica un gruppo di risorse per un'operazione, la programmazione prenota la capacità nel gruppo. Tuttavia, a differenza della programmazione processi, la programmazione operazioni non seleziona le risorse specifiche nel gruppo. Se si utilizza la capacità limitata, la programmazione dipende dalla disponibilità delle risorse necessarie per completare la produzione. La programmazione delle operazioni segue la sequenza delle operazioni specificata nel ciclo di lavorazione produzione. La programmazione consente di prenotare capacità dei gruppi di risorse in base agli orari operativi definiti nel ciclo di lavorazione produzione. La somma della capacità disponibile nelle risorse in questione determina la capacità per il gruppo di risorse. Le prenotazioni di capacità già presenti per le risorse vengono considerate come capacità non disponibile. Se la capacità disponibile è insufficiente per la produzione, gli ordini di produzione possono essere ritardati o persino interrotti. È inoltre possibile specificare l'efficienza che ci si attende delle risorse interessate dalla produzione. Specificare l'efficienza come percentuale della risorsa. La percentuale di efficienza regola la produttività della risorsa. Questa correzione influisce sul tempo prenotato per la risorsa. I lead time per le operazioni che utilizzano la risorsa vengono pertanto rettificati.

## <a name="operations-scheduling-and-master-planning"></a>Programmazione operazioni e pianificazione generale
Il programma delle operazioni influenza inoltre la pianificazione generale e determina i calcoli relativi ai fabbisogni di materiale. La programmazione operazioni considera le seguenti informazioni:

-   **Produzioni in backlog**: prodotti pianificati, rilasciati o iniziati
-   **Disponibilità di materiale**: scorte, produzioni secondarie e fornitori
-   **Disponibilità della capacità**: risorse necessarie per la produzione

> [!NOTE]
> Se si utilizza la programmazione delle operazioni e la pianificazione generale a thread multipli, la capacità limitata non verrà considerata. 

## <a name="cancellations"></a>Annullamenti
Quando si esegue la programmazione operazioni, è possibile annullare determinate parti del ciclo di lavorazione. Sono inclusi il tempo di attesa, il tempo di attrezzaggio, il tempo di processo, il tempo di sovrapposizione e i tempi di trasferimento.

## <a name="finite-materials"></a>Materiale limitati
Se si utilizzano i materiali limitati, la programmazione dipende anche dalla disponibilità dei materiali necessari per la produzione. Se i componenti disponibili non sono sufficienti per la produzione, la produzione può essere ritardata. È possibile basare la programmazione sull'utilizzo di materiali specificando i materiali che devono essere disponibili per la produzione. Quando si ottimizza sia sulla capacità della risorsa che la disponibilità dei materiali, la produzione viene calcolata in base alle restrizioni. L'inizio di un ordine di produzione non può essere programmato finché la capacità e i materiali non saranno disponibili contemporaneamente e nelle quantità richieste.

## <a name="additional-resources"></a>Risorse aggiuntive

[Opzioni di programmazione delle operazioni](operation-scheduling-options.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
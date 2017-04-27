---
title: Registrazione produzione
description: Questo articolo fornisce informazioni sui diversi tipi di registrazioni nel processo di produzione.
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventItemGroup, ProjCategory, WrkCtrResourceGroup, WrkCtrTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 54591
ms.assetid: 0917fe64-f643-46ae-98ff-5013b266a067
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 4a400463c4b84ac8e3e5300bd710fb330458cafd
ms.lasthandoff: 03/31/2017


---

# <a name="production-posting"></a>Registrazione produzione

[!include[banner](../includes/banner.md)]


Questo articolo fornisce informazioni sui diversi tipi di registrazioni nel processo di produzione.

Le attività di registrazione della produzione seguono i processi di produzione descritti nelle sezioni indicate di seguito.

## <a name="material-consumption"></a>Consumo materiali
I materiali vengono registrati come utilizzati in produzione quando il giornale di registrazione distinte di prelievo produzione viene registrato. Questo processo genera transazioni in uscita che riducono le scorte disponibili. Nei parametri di produzione è possibile specificare se il valore delle materie prime in lavorazione \[WIP\]) deve essere registrato nella contabilità generale. Il valore delle materie prime in lavorazione (WIP) viene quindi registrato in un conto distinta di prelievo dedicato e in un conto di contropartita dedicato distinta di prelievo.

## <a name="time-consumption"></a>Consumo di tempo
Il tempo che i lavoratori utilizzano per i processi di produzione viene registrato nel giornale di registrazione schede cicli di lavorazione o nel giornale di registrazione schede processi. Quando questi giornali di registrazione vengono registrati, viene elaborata la registrazione contabile in un conto dedicato per le risorse in lavorazione (WIP). Questa registrazione rappresenta il valore del tempo dedicato sull'ordine di produzione. Una volta che l'ordine di produzione viene registrato come finito, i conti WIP vengono liquidati.

## <a name="reporting-finished-goods-and-error-quantities"></a>Report su prodotti finiti e quantità di errore
Quando un ordine di produzione viene segnalato come finito, la quantità di prodotti finiti che sono stati completati viene aggiornata nella gestione inventario tramite il giornale di registrazione dichiarazioni di finito. Se si sta utilizzando un conto WIP, che può essere impostato nei parametri di produzione, viene creato un giornale di registrazione contabile per ridurre i conti WIP e aumentare l'inventario dei prodotti finiti. Il giornale di registrazione utilizza il costo standard definito per il prodotto.

## <a name="ending-the-production-order"></a>Fine dell'ordine di produzione
Prima che un ordine di produzione venga terminato, vengono calcolati i costi effettivi della quantità che è stata prodotta. Tutti i costi stimati in termini di materiali, manodopera e gestione generale vengono annullati e sostituiti con i costi effettivi. Il costo complessivo dell'articolo finito viene addebitato dal conto entrate in magazzino e accreditato sul conto uscite da magazzino. Se si seleziona la casella di controllo **Processo finale** quando si esegue il calcolo dei costi, lo stato dell'ordine di produzione viene impostato su **Finito**. Tale stato impedisce che vengano inavvertitamente registrati ulteriori costi per un ordine di produzione completato. È possibile specificare che il valore delle quantità difettose dichiarate durante la dichiarazione di finito deve essere allocato alle quantità idonee dichiarate finite. In alternativa, è possibile specificare che il valore delle quantità di errore debba essere registrato in un conto scarti dedicato.

## <a name="controlling-the-level-of-ledger-posting"></a>Controllo del livello di registrazione contabile
Nei **Parametri di controllo produzione**, è possibile utilizzare il campo **Registrazione contabile** per impostare il livello di registrazione contabile per i processi di produzione. Sono disponibili i valori seguenti:

-   **Articolo e risorsa** - Utilizzare i conti CoGe impostati sui gruppi di articoli per le materie prime e i prodotti finiti. Il WIP per il consumo di tempo viene ricavato dalla risorsa o dal gruppo di risorse dalle operazioni del ciclo di lavorazione.
-   **Articolo e categoria** - Utilizzare i conti CoGe impostati sui gruppi di articoli per le materie prime e i prodotti finiti. Il WIP per il consumo di tempo viene ricavato dalle categorie di costi associate alle operazioni del ciclo di lavorazione.
-   **Gruppi di produzioni** - Utilizzare i conti CoGe impostati sui gruppi di produzione per il consumo sia dei materiali che del tempo. I gruppi di produzione sono associati ai prodotti rilasciati e vengono copiati negli ordini di produzione quando tali ordini vengono creati. La registrazione sugli ordini di produzione seguirà quindi i gruppi di produzione associati all'ordine di produzione.

**Nota:** se per il calcolo del costo dell'articolo finito è stato utilizzato il metodo standard, nelle transazioni finali verrà riflesso anche questo aspetto. In caso di differenza tra i costi effettivi e i costi calcolati con il metodo standard, tale differenza verrà registrata sul conto che mostra il profitto o la perdita.





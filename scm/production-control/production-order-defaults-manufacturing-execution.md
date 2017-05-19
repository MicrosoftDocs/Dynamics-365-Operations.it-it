---
title: Impostazioni predefinite degli ordini di produzione nell&quot;esecuzione produzione
description: 
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: JmgProdParameters
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 70073
ms.assetid: 620944ae-3e20-444a-807e-65495f160904
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: cc12a8d75ead1577cf0b31a0dbf3ac072c47dc08
ms.contentlocale: it-it
ms.lasthandoff: 04/25/2017


---

# <a name="production-order-defaults-in-manufacturing-execution"></a>Impostazioni predefinite degli ordini di produzione nell'esecuzione produzione

[!include[banner](../includes/banner.md)]




Prima che i lavoratori inizino ad effettuare registrazioni per i processi di produzione, esaminare attentamente tutte le impostazioni della pagina **Impostazioni predefinite ordini di produzione**. Se la società utilizza la funzionalità multisito, è possibile impostare valori predefiniti diversi per gli ordini di produzione di ciascun sito. Le impostazioni predefinite degli ordini per l'integrazione con il controllo produzione vengono impostate sulle schede seguenti nella pagina **Impostazioni predefinite ordini di produzione**:

-   **Generale**: impostazioni predefinite generali dell'ordine per i processi di produzione in Esecuzione produzione.
-   **Inizio**: impostazioni ordine predefinite che vengono utilizzate durante i processi di produzione o all'avvio delle operazioni.
-   **Operazioni**: impostazioni predefinite dell'ordine che vengono applicate ai processi di produzione e al riscontro sulle operazioni durante il processo di produzione.
-   **Dichiarazione di finito**: impostazioni predefinite dell'ordine che vengono applicate quando gli articoli vengono dichiarati finiti nell'ultima operazione di un ordine di produzione.
-   **Convalida quantità**: impostazioni predefinite dell'ordine per la convalida delle quantità iniziali e di riscontro negli ordini di produzione.

## <a name="types-of-production-jobs"></a>Tipi di processi di produzione
Nella scheda **Operazioni** selezionare i tipi di processi di produzione che richiedono la registrazione nella pagina **Registrazione processi**. I lavoratori in genere eseguono le registrazioni dei processi di impostazione ed elaborazione. Se viene applicata la programmazione dei processi, tuttavia, è possibile selezionare altri tipi di processo, ad esempio processi di trasporto, per i quali i lavoratori dovranno effettuare le registrazioni durante l'elaborazione di un ordine di produzione. **Importante**: verificare che siano selezionati tutti i tipi di processi pertinenti. In caso contrario, i processi potrebbero non essere disponibili per la registrazione nella pagina **Registrazione processi**. Allineare le scelte effettuate alle selezioni effettuate nella colonna **Gestione processo** nella pagina **Gruppi di cicli di lavorazione**. Se nel gruppo di cicli di lavorazione è selezionata l'opzione **Gestione processo**, questo tipo di processo verrà dichiarato finito nell'ordine di produzione. La dichiarazione si verifica quando il processo viene dichiarato finito in Esecuzione produzione. Quando tutti i tipi di processo per i quali è selezionata l'opzione **Gestione processo** sono stati dichiarati come finiti per un'operazione, l'operazione stessa verrà dichiarata finita anche in Esecuzione produzione. **Nota:** per alcuni tipi di processi la dichiarazione può essere eseguita manualmente tramite giornali di registrazione produzione. In questo caso, selezionare **Gestione processo** per il tipo di processo, ma non selezionare il tipo di processo per la registrazione nella scheda **Operazioni** della pagina **Impostazioni predefinite ordini di produzione**.

## <a name="bom-consumption-and-picking-list-journals"></a>Giornali di registrazione del consumo DBA e delle distinte di prelievo
I materiali possono essere impostati in modo da essere utilizzati automaticamente o manualmente durante la produzione. Il consumo automatico è controllato dal principio di registrazione del consumo di materiali impostato sulle righe della distinta base (DBA) e dal campo **Consumo DBA automatico** nelle impostazioni predefinite dell'ordine di produzione. Il consumo automatico può essere impostato in modo che si verifichi quando un ordine di produzione è avviato o dichiarato finito. In alternativa, può verificarsi a livello di processo quando un processo viene avviato o completato.

### <a name="controlling-material-consumption-when-a-production-order-is-started"></a>Controllo del consumo di materiali quando un ordine di produzione viene avviato

Il consumo di materiali durante l'avvio di un ordine di produzione viene controllato nel campo **Consumo DBA automatico** nella scheda **Inizio**. Sono disponibili i valori seguenti:

-   **Principio di registrazione del consumo di materiali**: se un ordine di produzione è avviato, le quantità di materiale verranno utilizzate in base al principio di registrazione del consumo di materiali impostato nelle righe DBA di produzione. Solo le righe relative al materiale in cui il principio di registrazione del consumo di materiali è impostato su **Inizio** verranno utilizzate durante l'avvio della produzione.
-   **Sempre**: le quantità di materiale proporzionali alla quantità avviata verranno sempre utilizzate.
-   **Mai**: le quantità di materiale non verranno mai utilizzate.

### <a name="controlling-material-consumption-when-a-production-job-is-started-or-completed"></a>Controllo del consumo di materiali quando un processo di produzione viene avviato o completato

Il consumo di materiali durante l'avvio o il completamento di un processo di produzione viene controllato nel campo **Consumo DBA automatico** nella scheda **Operazioni**. Sono disponibili i valori seguenti:

-   **Principio di registrazione del consumo di materiali**: se una quantità su un ordine di produzione è iniziata o completata, le quantità di materiale verranno utilizzate in base al principio di registrazione del consumo di materiali impostato nelle righe DBA di produzione. Solo le righe relative al materiale in cui il principio di registrazione del consumo di materiali è impostato su **Inizio** o su **Fine** verranno utilizzate.
-   **Sempre**: le quantità di materiale proporzionali alla quantità avviata nel processo verranno sempre utilizzate.
-   **Mai**: le quantità di materiale non verranno mai utilizzate.

### <a name="controlling-material-consumption-when-a-production-order-is-reported-as-finished"></a>Controllo del consumo di materiale quando un ordine di produzione viene dichiarato finito.

Il consumo di materiali durante il processo di dichiarazione di finito per un ordine di produzione viene controllato nel campo **Consumo DBA automatico** nella scheda **Dichiarato finito**. Sono disponibili i valori seguenti:

-   **Principio di registrazione del consumo di materiali**: se un ordine di produzione viene dichiarato finito, le quantità di materiale verranno utilizzate in base al principio di registrazione del consumo di materiali impostato nelle righe DBA di produzione. Solo le righe relative al materiale in cui il principio di registrazione del consumo di materiali è impostato su **Fine** verranno utilizzate.
-   **Sempre**: le quantità di materiale proporzionali alla quantità dichiarata finita verranno sempre utilizzate.
-   **Mai**: le quantità di materiale non verranno mai utilizzate.






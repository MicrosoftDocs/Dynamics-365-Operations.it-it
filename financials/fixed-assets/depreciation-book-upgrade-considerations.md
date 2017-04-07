---
title: Panoramica di aggiornamento per registri beni ammortizzabili
description: "Nelle versioni precedenti, presenza di due concetti dei prezzi per i cespiti ridotto - modelli di valore e registri beni ammortizzabili. In Microsoft Dynamics 365 for Operations versione 1611, le funzionalità dei modelli di valore e le funzionalità dei registri beni ammortizzabili sono state unite in un unico concetto noto come libro. In questo argomento vengono fornite alcune considerazioni per l&quot;aggiornamento."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer
ms.search.scope: Operations, Core
ms.custom: 221624
ms.assetid: cf434099-36f9-4b0f-a7c8-bed091e34f39
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: bec019d218d80ba059d5a1c232072f46b1ae3ee2
ms.openlocfilehash: d29cb7bc5acc29be93332b4211adebc4486a7a25
ms.lasthandoff: 03/31/2017


---

# <a name="depreciation-book-upgrade-overview"></a>Panoramica di aggiornamento per registri beni ammortizzabili

Nelle versioni precedenti, presenza di due concetti dei prezzi per i cespiti ridotto - modelli di valore e registri beni ammortizzabili. In Microsoft Dynamics 365 for Operations versione 1611, le funzionalità dei modelli di valore e le funzionalità dei registri beni ammortizzabili sono state unite in un unico concetto noto come libro. In questo argomento vengono fornite alcune considerazioni per l'aggiornamento. 

Il processo di aggiornamento sposterà l'impostazione esistente e tutte le transazioni esistenti nella nuova struttura dei libri. I modelli di valore rimarranno come sono attualmente, come libro che registra nella contabilità generale. I registri beni ammortizzabili verranno spostati in un libro con l'opzione **Registra nella contabilità generale** impostata su **No**. I nomi di giornale di registrazione per registri beni ammortizzabili vengono spostati in un nome di giornale di registrazione contabile al livello di registrazione impostato su Nessuno ** **. Le transazioni del registro beni ammortizzabili verranno spostate nelle transazioni cespiti. 

Prima di eseguire l'aggiornamento dei dati, è necessario comprendere le due opzioni disponibili per aggiornare le righe del giornale di registrazione per registri beni ammortizzabili ai giustificativi di transazione e la sequenza numerica da utilizzare per la serie di giustificativi. 

Opzione 1:  **sequenza numerica definita dal sistema-** - Questa è l'opzione predefinita per ottimizzare le prestazioni di aggiornamento. Non verrà utilizzato il framework di sequenze numeriche, ma verranno assegnati i giustificativi con un approccio basato su set. Dopo l'aggiornamento, la nuova sequenza numerica viene creato con ** numero successivo impostato correttamente ** basato sulle transazioni aggiornate. Per impostazione predefinita, la sequenza numerica utilizzata verrà nel formato di FADBUpgr\#\#\#\#\#\#\#\#\#. Sono disponibili alcuni parametri disponibili all'utente per rettificare il formato quando si utilizza questo approccio:

-   ** Codice sequenza numerica ** il codice di identificazione della sequenza numerica. Questo codice di sequenza numerica non può essere presente che verrà creato dall'aggiornamento.
    -   Nome costante: **NumberSequenceDefaultCode**
    -   Valore predefinito: "FADBUpgr"
-   **Prefisso** - Il valore stringa costante da utilizzare come prefisso per i numeri di giustificativo.
    -   Nome costante: **NumberSequenceDefaultParameterPrefix**
    -   Valore predefinito: "FADBUpgr"
-   **Lunghezza alfanumerica** - La lunghezza del segmento alfanumerico della sequenza numerica.
    -   Nome Costante: ** NumberSequenceDefaultParameterAlpanumericLength **
    -   Valore predefinito: 9
-   **Numero iniziale** - Primo numero da utilizzare nella sequenza numerica.
    -   Nome Costante: ** NumberSequenceDefaultParameterStartNumber **
    -   Valore predefinito: 1

Opzione 2: ** La sequenza numerica definita dall'utente esistente ** questa opzione questo modo sarà possibile definire la sequenza numerica da utilizzare per l'aggiornamento. Può essere opportuno di utilizzare questa opzione se si necessita di configurazione Progetto - Avanzato di sequenza numerica. Per utilizzare una sequenza numerica, sarà necessario modificare la classe ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans di aggiornamento con le seguenti informazioni:

-   **Codice sequenza numerica**: Il codice della sequenza numerica.
    -   Nome Costante: ** NumberSequenceExistingCode **
    -   Valore predefinito: Nessun valore predefinito, questo deve essere aggiornato al codice di sequenza numerica.
-   **Sequenza numerica condivisa** È un valore booleano per identificare l'ambito della sequenza numerica. Utilizzare "true" per le sequenze numeriche comuni a tutte le società e "false" per un ambito specifico di una società. Quando mediante la false", la sequenza numerica con il nome specificato deve essere definita in ciascuna società contenente le transazioni del registro beni ammortizzabili. Le sequenze numeriche comuni presenti in ogni partizione contenente le transazioni del registro beni ammortizzabili.
    -   Nome Costante: ** NumberSequenceExistingIsShared **
    -   Valore predefinito: true

I parametri sono presenti all'inizio della classe di ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans. 

*//Specificare un approccio preferibile di 
allocation* di giustificativi *//riga, se si desidera utilizzare un code* 
di sequenza numerica esistente *//falsa, se si intende utilizzare la sequenza numerica definita dal sistema (standard) * const NumberSequenceUseExistingCode booleano = false;  

*//Se si utilizza l'approccio basato definito dal sistema di sequenza numerica, specificare i parametri per il numero sequence.*
*//una nuova sequenza numerica verrà creata con questi parameters.* streptococco NumberSequenceDefaultCode di const = "FADBUpgr"; streptococco NumberSequenceDefaultParameterPrefix di const = "FADBUpgr"; const oggetti NumberSequenceDefaultParameterAlpanumericLength = 9; const oggetti NumberSequenceDefaultParameterStartNumber = 1;   

*//Se si utilizza l'approccio basato di sequenza numerica esistente, specificare la sequenza numerica esistente code.* 
*//l'allocazione del giustificativo andrà riga-da- riga per il numero sequences.* esistente streptococco NumberSequenceExistingCode di const = ''; *//Specificare l'ambito del code* 
di sequenza numerica esistente *//riga, se la sequenza numerica specificata è shared* 
*//falsa, se la sequenza numerica specificata è per-company* 
*//la sequenza numerica definita dal sistema standard verrà utilizzata se un codice sequenza numerica con un ambito non è specificato found.* const boolean NumberSequenceExistingIsShared = true; 

Ricompilare il progetto contenente la classe dopo che le costanti sono state modificate. 

Quando si utilizza l'approccio basato generato dal sistema di sequenze numeriche (opzione) 1, l'aggiornamento verrà utilizzata l'elaborazione basato su set per assegnare i numeri di giustificativo specificato nei parametri dello script di aggiornamento. Vengono inoltre creata una nuova sequenza numerica con i parametri specificati dopo l'allocazione. 

Quando si utilizza l'approccio di sequenza numerica esistente definita dall'utente (opzione 2), l'aggiornamento dei dati controlla se la sequenza numerica con l'ambito specificato esiste nel database per ogni partizione e società con transazioni del registro beni ammortizzabili. In caso affermativo, l'aggiornamento verrà utilizzata la riga-da- riga in modo da assegnare i numeri di giustificativo come specificato dalla sequenza numerica con il framework di sequenza numerica. Se la sequenza numerica non è presente nell'ambito specificato, l'aggiornamento verrà utilizzato l'approccio con di sequenza numerica definito dal sistema standard per assegnare i numeri di giustificativo e verrà creata una nuova sequenza numerica con i parametri predefiniti specificati dopo l'allocazione.

Con l'uno o l'altro approccio, lo script di aggiornamento dei dati utilizzerà la sequenza numerica anche per il campo **Serie giustificativi** nei nuovi nomi di giornale di registrazione di contabilità generale creato per i precedenti nomi di giornale di registrazione per registri beni ammortizzabili.



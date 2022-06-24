---
title: Panoramica dell'aggiornamento dei registri beni ammortizzabili
description: Questo articolo descrive la funzionalità contabile corrente in Cespiti. Questa funzionalità dei libri si basa sulla funzionalità dei modelli di valore disponibile nelle versioni precedenti, ma include anche tutte le funzionalità prima fornite solo nei registri beni ammortizzabili.
author: moaamer
ms.date: 06/20/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User, Developer
ms.reviewer: kfend
ms.custom:
- "221624"
- intro-internal
ms.assetid: cf434099-36f9-4b0f-a7c8-bed091e34f39
ms.search.region: global
ms.author: moaamer
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 784ec32ae886ef7ea9342b085f893eeeec761961
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855493"
---
# <a name="depreciation-book-upgrade-overview"></a>Panoramica dell'aggiornamento dei registri beni ammortizzabili

[!include [banner](../includes/banner.md)]

Questo articolo descrive la funzionalità contabile corrente in Cespiti. Questa funzionalità dei libri si basa sulla funzionalità dei modelli di valore disponibile nelle versioni precedenti, ma include anche tutte le funzionalità prima fornite solo nei registri beni ammortizzabili. Il modello di valore e le funzionalità dei registri beni ammortizzabili sono state unite in un unico concetto noto come libro. La funzionalità contabile consente di utilizzare un unico set di pagine, richieste e report per tutti i processi relativi ai cespiti dell'organizzazione. Questo articolo fornisce alcuni elementi da considerare prima di eseguire l'aggiornamento. 

Il processo di aggiornamento sposterà l'impostazione esistente e tutte le transazioni esistenti nella nuova struttura dei libri. I modelli di valore rimarranno come sono attualmente, come libro che registra nella contabilità generale. I registri beni ammortizzabili verranno spostati in un libro con l'opzione Registra nella contabilità generale impostata su No. I nomi di giornale di registrazione per registri beni ammortizzabili vengono spostati in un nome di giornale di registrazione di contabilità generale con livello di registrazione impostato su Nessuno. Le transazioni del registro beni ammortizzabili verranno spostate nelle transazioni cespiti.

Prima di eseguire l'aggiornamento dei dati, è necessario comprendere le due opzioni disponibili per aggiornare le righe del giornale di registrazione per registri beni ammortizzabili ai giustificativi di transazione e la sequenza numerica da utilizzare per la serie di giustificativi.

Opzione 1:  **sequenza numerica definita dal sistema-** - Questa è l'opzione predefinita per ottimizzare le prestazioni di aggiornamento. Non verrà utilizzato il framework di sequenze numeriche, ma verranno assegnati i giustificativi con un approccio basato su set. Dopo l'aggiornamento, la nuova sequenza numerica viene creato con il **Set di numeri successivo** appropriatamente basato sulle transazioni aggiornate. Per impostazione predefinita, la sequenza numerica utilizzata sarà nel formato FADBUpgr\#\#\#\#\#\#\#\#\#. Sono disponibili alcuni parametri per rettificare il formato quando si utilizza questo approccio:

-   **Codice sequenza numerica**: il codice di identificazione della sequenza numerica. Questo codice di sequenza numerica non può esistere poiché verrà creato dall'aggiornamento.
    -   Nome costante: **NumberSequenceDefaultCode**
    -   Valore predefinito: "FADBUpgr"
-   **Prefisso** - Il valore stringa costante da utilizzare come prefisso per i numeri di giustificativo.
    -   Nome costante: **NumberSequenceDefaultParameterPrefix**
    -   Valore predefinito: "FADBUpgr"
-   **Lunghezza alfanumerica** - La lunghezza del segmento alfanumerico della sequenza numerica.
    -   Nome costante: **NumberSequenceDefaultParameterAlpanumericLength**
    -   Valore predefinito: 9
-   **Numero iniziale** - Primo numero da utilizzare nella sequenza numerica.
    -   Nome costante: **NumberSequenceDefaultParameterStartNumber**
    -   Valore predefinito: 1

Opzione 2: **Sequenza numerica definita dall'utente esistente** - Questa opzione consente di definire la sequenza numerica da utilizzare per l'aggiornamento. Può essere opportuno utilizzare questa opzione se si necessita di una configurazione di sequenza numerica avanzata. Per utilizzare una sequenza numerica, sarà necessario modificare la classe ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans di aggiornamento con le seguenti informazioni:

-   **Codice sequenza numerica**: Il codice della sequenza numerica.
    -   Nome costante: **NumberSequenceExistingCode**
    -   Valore predefinito: Nessun valore predefinito, questo deve essere aggiornato al codice di sequenza numerica.
-   **Sequenza numerica condivisa** È un valore booleano per identificare l'ambito della sequenza numerica. Utilizzare "true" per le sequenze numeriche comuni a tutte le società e "false" per un ambito specifico di una società. Quando si usa "false", la sequenza numerica con il nome specificato deve esistere in ciascuna società contenente le transazioni del registro beni ammortizzabili. Le sequenze numeriche condivise esistono in ogni partizione contenente le transazioni del registro beni ammortizzabili.
    -   Nome costante: **NumberSequenceExistingIsShared**
    -   Valore predefinito: true

I parametri sono situati all'inizio della classe ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans. 

*// Specificare un approccio preferibile di allocazione di giustificativi* 
 *// true, se si desidera utilizzare un codice di sequenza numerica esistente* 
 *// false, se si intende utilizzare la sequenza numerica definita dal sistema (predefinita)* const boolean NumberSequenceUseExistingCode = false;  

*// Se si utilizza l'approccio di sequenza numerica definito dal sistema, specificare i parametri per la sequenza numerica.*
 *// Una nuova sequenza numerica verrà creata con questi parametri.* const str NumberSequenceDefaultCode = 'FADBUpgr'; const str NumberSequenceDefaultParameterPrefix = 'FADBUpgr'; const int NumberSequenceDefaultParameterAlpanumericLength = 9; const int NumberSequenceDefaultParameterStartNumber = 1;   

*// Se si utilizza l'approccio di sequenza numerica esistente, specificare il codice di sequenza numerica esistente.* 
 *// L'allocazione dei giustificativi procederà riga per riga per le sequenze numeriche esistenti.* const str NumberSequenceExistingCode = ''; *// Specificare l'ambito del codice della sequenza numerica esistente* 
 *// true, se la sequenza numerica specificata è condivisa* 
 *// false, se la sequenza numerica specificata è per singola società* 
 *// La sequenza numerica definita dal sistema predefinita verrà utilizzata se un codice di sequenza numerica con l'ambito specificato non viene trovato.* const boolean NumberSequenceExistingIsShared = true; 

Ricompilare il progetto contenente la classe dopo che le costanti sono state modificate. 

Quando si utilizza l'approccio di sequenza numerica generata dal sistema (opzione 1), l'aggiornamento utilizzerà l'elaborazione basata su set per assegnare i numeri di giustificativo come specificato nei parametri dello script di aggiornamento. Viene inoltre creata una nuova sequenza numerica con i parametri specificati dopo l'allocazione. 

Quando si utilizza l'approccio di sequenza numerica esistente definita dall'utente (opzione 2), l'aggiornamento dei dati controlla se la sequenza numerica con l'ambito specificato esiste nel database per ogni partizione e società con transazioni del registro beni ammortizzabili. In caso affermativo, l'aggiornamento utilizzerà l'elaborazione riga per riga per assegnare i numeri di giustificativo come specificato dalla sequenza numerica con il framework di sequenza numerica. Se la sequenza numerica non è presente nell'ambito specificato, l'aggiornamento utilizzerà l'approccio di sequenza numerica definita dal sistema predefinita per assegnare i numeri di giustificativo e verrà creata una nuova sequenza numerica con i parametri predefiniti specificati dopo l'allocazione.

Con l'uno o l'altro approccio, lo script di aggiornamento dei dati utilizzerà la sequenza numerica anche per il campo **Serie giustificativi** nei nuovi nomi di giornale di registrazione di contabilità generale creato per i precedenti nomi di giornale di registrazione per registri beni ammortizzabili.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]

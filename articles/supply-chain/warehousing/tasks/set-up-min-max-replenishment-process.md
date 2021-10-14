---
title: Impostare un processo di rifornimento minimo/massimo
description: Questa procedura mostra come impostare un nuovo processo di rifornimento che utilizza la strategia di rifornimento minima/massima.
author: perlynne
ms.date: 10/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSInventFixedLocation, InventItemIdLookupSimple, WMSLocationIdLookup, WHSLocDirTable, InventLocationIdLookup, SysQueryForm, WHSWorkTemplateTable, WHSReplenishmentTemplates, UnitOfMeasureLookup, SysQueryTableLookUp, SysQueryFieldLookUp, SysRecurrence, WHSInventFixedLocation
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f032f95377fdc6f8ec7fbbfa7aadab8fc448be5d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7577770"
---
# <a name="set-up-a-min-max-replenishment-process"></a>Impostare un processo di rifornimento minimo/massimo

[!include [banner](../../includes/banner.md)]

Questa procedura mostra come impostare un nuovo processo di rifornimento che utilizza la strategia di rifornimento minima/massima. Quando le scorte scendono sotto il livello minimo, il lavoro verrà creato per rifornire l'ubicazione. La procedura mostra anche come utilizzare le ubicazioni fisse di prelievo per consentire il ristoccaggio anche se le scorte scendono sotto il livello minimo e come consentire l'esecuzione regolare del processo di rifornimento utilizzando un processo batch. Queste attività verranno in genere svolte da un responsabile del magazzino. È possibile eseguire questa procedura nella società di dati dimostrativi USMF utilizzando i valori di esempio di seguito oppure è possibile eseguirla sui propri dati. Se si utilizzano i propri dati, assicurarsi che un magazzino sia abilitato per i processi di gestione magazzino.


## <a name="create-a-fixed-picking-location"></a>Creare un'ubicazioni fissa di prelievo
1. Andare **Pannello di navigazione > Moduli > Gestione magazzino > Impostazioni > Magazzino > Ubicazioni fisse**. Si tratta di un'attività facoltativa per il rifornimento min- max, ma se si utilizza l'ubicazione fissa di prelievo, questa consente il rifornimento delle scorte anche se scendono al livello minimo, poiché il sistema può determinare quali articoli devono essere riforniti, anche se non ne sono rimasti.
2. Fare clic su **Nuovo**.
3. Nel campo **Numero articolo** immettere o selezionare un valore. Se si utilizza USMF, è possibile selezionare l'articolo A0001.  
4. Nel campo **Sito** immettere o selezionare un valore. Se si utilizza USMF, è possibile selezionare il sito 2.  
5. Nel campo **Magazzino** immettere o selezionare un valore. Se si utilizza USMF, è possibile selezionare il magazzino 24.  
6. Nel campo **Ubicazione** immettere o selezionare un valore. Se si utilizza USMF, è possibile selezionare CP-003.  
7. Chiudere la pagina.

## <a name="create-a-replenishment-location-directive"></a>Creare una direttiva ubicazione di rifornimento
1. Andare a **Gestione magazzino > Impostazioni > Magazzino > Direttive ubicazione**. Le direttive di ubicazione vengono utilizzate per determinare il luogo di prelievo degli articoli nel processo di rifornimento.
2. Nel campo **Tipo ordine di lavoro** selezionare "Rifornimento".
3. Fare clic su **Nuova** nel **riquadro azioni**.
4. Digitare un valore nel campo **Nome**.
5. Nel campo **Tipo di lavoro**, selezionare 'Preleva'.
6. Nel campo **Sito** immettere o selezionare un valore. Se si utilizza USMF, è possibile selezionare il sito 2.  
7. Nel campo **Magazzino** immettere o selezionare un valore. Se si utilizza USMF, è possibile selezionare il magazzino 24.  
8. Fare clic su **Salva**.
9. Nella sezione **Righe**, fare clic su **Nuovo**.
10. Nell'elenco contrassegnare la riga selezionata.
11. Nel campo **A quantità** immettere un numero. È ad esempio possibile impostarlo su 9999.  
12. Selezionare la casella di controllo **Consenti divisione**. Se si seleziona questa opzione, il processo di creazione del lavoro consentirà la suddivisione delle quantità di righe di lavoro tra più ubicazioni.  
13. Fare clic su **Salva**.
14. Nella sezione **Azioni direttiva ubicazione** fare clic su **Nuovo**.
15. Nell'elenco contrassegnare la riga selezionata.
16. Digitare un valore nel campo **Nome**.
17. Fare clic su **Salva**.
18. Nel **riquadro azioni** fai clic su **Modifica query**. È possibile modificare questa query per aggiungere le restrizioni relative alla selezione dell'inventario nel processo di rifornimento. Ad esempio, è possibile che l'inventario debba essere utilizzato solo dall'area di stoccaggio del magazzino.
19. Fare clic su **OK**.
20. Chiudere la pagina.

## <a name="create-a-replenishment-work-template"></a>Creare un modello di lavoro di rifornimento
1. Andare a **Gestione magazzino > Impostazioni > Lavoro > Modelli di lavoro**. Il modello di lavoro consente di indicare al sistema come deve essere creato il lavoro di rifornimento min/max. Come minimo, deve essere presente una riga del modello di lavoro per un prelievo e un inserimento. Il modello di lavoro dirà che non è valida fino al completamento di tutte le informazioni richieste. 
2. Nel campo **Tipo ordine di lavoro** selezionare "Rifornimento".
3. Fare clic su **Nuova** nel **riquadro azioni**.
4. Digitare un valore nel campo **Modello di lavoro**.
5. Fare clic su **Salva**.
6. Nella sezione **Dettagli modello di lavoro**, fare clic su **Nuovo**.
7. Nel campo **Tipo di lavoro**, selezionare 'Preleva'.
8. Nel campo **ID classe lavoro** immettere o selezionare un valore. Questo deve essere una classe di lavoro correlata al rifornimento. Se si utilizza USMF, selezionare Rifornisci.  
9. Nella sezione **Dettagli modello di lavoro**, fare clic su **Nuovo**.
10. Nell'elenco contrassegnare la riga selezionata.
11. Nel campo **Tipo di lavoro** selezionare "Inserisci".
12. Nel campo **ID classe lavoro** immettere o selezionare un valore.
13. Fare clic su **Salva**.
14. Chiudere la pagina.

## <a name="create-a-new-replenishment-template"></a>Creare un nuovo modello di rifornimento
1. Andare a **Gestione magazzino > Impostazioni > Rifornimento > Modelli rifornimento**. Il modello di rifornimento viene utilizzato per definire gli articoli e le quantità e l'ubicazione da rifornire.
2. Fare clic su **Nuova** nel **riquadro azioni**.
3. Digitare un valore nel campo **Modello rifornimento**. Assegnare al modello un nome per indicare che è per il rifornimento min/max.  
4. Digitare un valore nel campo **Descrizione**
5. Selezionare la casella di controllo **Consenti domanda ondata per utilizzare le quantità non prenotate**. Se si seleziona questa opzione, il rifornimento della domanda di ondata utilizzerà le quantità correlate al rifornimento min/max. Ad esempio, questo può essere utile se il lavoro di rifornimento min/max non viene elaborato immediatamente, per evitare che il lavoro inutile di rifornimento della domanda venga creato.
6. Nella sezione **Dettagli del modello rifornimento**, fare clic su **Nuovo**.
7. Immettere un numero nel campo **Numero progressivo**.
8. Digitare un valore nel campo **Descrizione**
9. Nell'elenco contrassegnare la riga selezionata.
10. Nel campo **Unità di rifornimento** immettere o selezionare un valore. Selezionare, ad esempio, pz. Questa impostazione è obbligatoria. Consente di specificare un'unità di misura diversa per il lavoro di rifornimento rispetto all'unità specificata per i livelli delle scorte minime e massime in questo modello.
11. Nel campo **Modello di lavoro** immettere o selezionare un valore. Scegliere il modello di lavoro creato in precedenza.  
12. Nel campo **Quantità minima** immettere un numero. Selezionare la quantità minima per avviare il rifornimento. Ad esempio, impostarla su 50. È possibile lasciarla impostata su zero, se si sta rifornendo un'ubicazione fissa e l'opzione **Rifornisci ubicazioni fisse vuote** viene impostata su "Sì". Si consiglia inoltre di selezionare l'opzione **Rifornisci solo ubicazioni fisse** per motivi di prestazioni.
13. Nel campo **Quantità massima** immettere un numero. Ad esempio, impostarla su 100.  
14. Nel campo **Unità** immettere o selezionare un valore. Assegnare l'unità per le quantità minima e massima. Ad esempio, impostarla su pz.  
15. Selezionare la casella di controllo **Rifornisci ubicazioni fisse vuote**. Selezionare questa casella di controllo per rifornire le ubicazioni fisse quando sono vuote. In caso contrario, verranno rifornite solo le ubicazioni in cui è presente una quantità disponibile.
16. Selezionare la casella di controllo **Rifornisci solo ubicazioni fisse**.
17. Fare clic su **Seleziona prodotti**. Si tratta della posizione per definire quali prodotti devono essere riforniti. Se l'opzione relativa alle ubicazioni di prelievo fisse è selezionata, è necessario definire le ubicazioni anche in questa query. Sono disponibili query specifiche sulle varianti così come query specifiche sui prodotti.
18. Selezionare la riga **Articoli**.
19. Digitare un valore nel campo **Criteri**. Selezionare gli articoli che devono essere riforniti presso ubicazioni fisse. Ad esempio, immettere A* per selezionare tutti i numeri di articolo che iniziano con A.
20. Scegliere **Aggiungi**. Aggiungere l'entità Ubicazione (a meno che non sia già presente) per poter limitare il lavoro di rifornimento alle ubicazioni di prelievo fisse all'interno di un'area specifica del magazzino.
21. Nell'elenco contrassegnare la riga selezionata.
22. Impostare il campo **Tabella** su "Ubicazioni".
23. Nel campo **Campo** selezionare "ID profilo ubicazione".
24. Nel campo **Criteri** immettere o selezionare un valore.
25. Fare clic su **OK**.
26. Chiudere la pagina.

## <a name="set-the-replenishment-process-to-run-as-a-batch-job"></a>Impostare il processo di rifornimento in modo che venga eseguito come processo batch
1. Andare a **Gestione magazzino > Impostazioni > Rifornimento > Rifornimenti**. La pagina Rifornimento consente di impostare il rifornimento da eseguire come processo batch o di richiedere che venga attivato manualmente.
2. Fare clic su **Filtro**.
3. Nell'elenco contrassegnare la riga selezionata.
4. Nel campo **Criteri** immettere o selezionare un valore.
5. Fare clic su **OK**.
6. Espandere la sezione **Esecuzione in background**.
7. Impostare l'opzione **Elaborazione batch** su "Sì".
8. Fare clic su **Ricorrenza**.
9. Selezionare l'opzione **Nessuna data di fine**.
10. Impostare il **Criterio ricorrenza**. Selezionare, ad esempio, Giorni.  
11. Fare clic su **OK**.
12. Fare clic su **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
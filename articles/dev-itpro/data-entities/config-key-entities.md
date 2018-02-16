---
title: "Chiavi di configurazione ed entità di dati"
description: "In questo argomento viene descritta la relazione tra le chiavi di configurazione e le entità di dati di Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
author: Sunil-Garg
manager: AnnBe
ms.date: 01/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application user
ms.reviewer: margoc
ms.search.scope: Operations
ms.custom: 25341
ms.assetid: 8e214c95-616b-4ee1-b5a4-fa5ce5147f2c
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Platform update 13
ms.translationtype: HT
ms.sourcegitcommit: 40bfc3f1f7c5fe1eec788d252cbe7be7d1c7536f
ms.openlocfilehash: 1dab5e2e93bb87a926e9c66599ad711556206765
ms.contentlocale: it-it
ms.lasthandoff: 01/19/2018

---

# <a name="configuration-keys-and-data-entities"></a>Chiavi di configurazione ed entità di dati
Prima di utilizzare le entità di dati per importare o esportare dati, si consiglia di determinare innanzitutto l'impatto delle chiavi di configurazione sulle entità di dati che si prevede di utilizzare. 

Per ulteriori informazioni sulle chiavi di configurazione in Finance and Operations, vedere [Report su codici di licenza e chiavi di configurazione](../sysadmin/license-codes-configuration-keys-report.md).

### <a name="configuration-key-assignments"></a>Assegnazioni della chiave tasti di configurazione
Le chiavi di configurazione possono essere assegnate a uno o tutti i seguenti elementi.
-   Entità di dati
-   Tabella utilizzata come origine dati
-   Campi tabella
-   Campi entità di dati

La seguente tabella riepiloga in che modo i valori delle chiavi di configurazione dei diversi elementi che sono alla base di un oggetto modificano il comportamento previsto dell'oggetto.

| Impostazione della chiave di configurazione nell'entità di dati | Impostazione della chiave di configurazione nella tabella | Impostazione della chiave di configurazione nel campo | Chiave di configurazione nell'entità di dati | Comportamento previsto                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------|-----------------------------|-----------------------------------|---------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Disabilitata                          | Non valutata               | Non valutata                     | Non valutata                   | Se la chiave di configurazione per l'entità di dati è disabilitata, l'entità di dati non sarà funzionale. Non è rilevante se le chiavi di configurazione nelle tabelle e nei campi sottostanti sono abilitate o disabilitate.                                                                                                                                                                                                                                                                                                                                          |
| Abilitate                           | Disabilitata                    | Non valutata                     | Non valutata                   | Se la chiave di configurazione per un'entità di dati è abilitata, il framework di gestione dei dati controlla la chiave di configurazione in tutte le tabelle sottostanti. Se la chiave di configurazione per una tabella è disabilitata, quella tabella non sarà disponibile nell'entità di dati per l'uso funzionale. Se la chiave di configurazione di una tabella è disabilitata, la tabella e le impostazioni della chiave di configurazione dell'entità dati non vengono valutate. Se la tabella primaria nell'entità ha la rispettiva chiave di configurazione disabilitata, il sistema agirà come se la chiave di configurazione dell'entità fosse disabilitata. |
| Abilitate                           | Abilitate                     | Disabilitata                          | Non valutata                   | Se la chiave di configurazione per un'entità di dati è abilitata e chiavi di configurazione sottostanti delle tabelle sono abilitate, il framework di gestione dei dati verificherà la chiave di configurazione nei campi delle tabelle. Se la chiave di configurazione per un campo è disabilitata, tale campo non sarà disponibile nell'entità di dati per l'utilizzo funzionale anche se il campo dell'entità di dati corrispondente ha la chiave di configurazione abilitata.                                                                                                                                   |
| Abilitate                           | Abilitate                     | Abilitate                           | Disabilitata                        | Se la chiave di configurazione è abilitata a tutti gli altri livelli, ma la chiave di configurazione del campo entità non è abilitata, il campo non sarà disponibile per l'utilizzo nell'entità di dati.                                                                                                                                                                                                                                                                                                                                                                          |

> [!NOTE]
> Se un'entità ha un'altra entità come un'origine dati, la semantica sopra riportata viene applicata in modo ricorsivo.

### <a name="entity-list-refresh"></a>Aggiornamento dell'elenco di entità
Quando l'elenco delle entità viene aggiornato, il framework di gestione dei dati crea i metadati della chiave di configurazione per l'utilizzo in runtime. Questi metadati vengono creati utilizzando la logica descritta sopra. Si consiglia vivamente di attendere il completamento dell'aggiornamento dell'elenco delle entità prima di utilizzare i processi e le entità nel framework di gestione dei dati. Se non si attende, i metadati della chiave di configurazione potrebbero non essere aggiornati e determinare esiti imprevisti. Quando l'elenco delle entità viene aggiornato, viene visualizzato il seguente messaggio nella pagina di elenco delle entità.

![Aggiornamento dell'elenco di entità](./media/Entity_refresh_list.png)

### <a name="data-entity-list-page"></a>Pagina elenco di entità di dati
La pagina di elenco delle entità di dati nell'area di lavoro Gestione dati mostra le impostazioni della chiave di configurazione per le entità. Iniziare da questa pagina per comprendere l'impatto delle chiavi di configurazione sull'entità di dati.
Queste informazioni vengono visualizzate utilizzando i metadati creati durante l'aggiornamento dell'entità. La colonna della chiave di configurazione mostra il nome della chiave di configurazione associata all'entità di dati. Se questa colonna è vuota, significa che non vi è alcuna chiave di configurazione associata all'entità di dati. La colonna dello stato della chiave di configurazione mostra lo stato della chiave di configurazione. Se è presente un segno di spunta, significa che la chiave è abilitata. Se non è presente un segno di spunta, significa che la chiave è disabilitata o non è associata alcuna chiave.

![Pagina elenco di entità](./media/Data_entity_list_page.png)

### <a name="target-fields"></a>Campi di destinazione
Il passaggio successivo consiste nell'eseguire il drill nell'entità di dati per visualizzare l'impatto delle chiavi di configurazione su tabelle e campi. Il modulo dei campi di destinazione per un'entità di dati mostra la chiave di configurazione e le informazioni sullo stato della chiave per le tabelle e i campi correlati nell'entità di dati.  Se l'entità di dati stessa ha la rispettiva chiave di configurazione disabilitata, viene visualizzato un messaggio di avviso che informa che le tabelle e i campi nel modulo dei campi di destinazione per questa entità non saranno disponibili a tutti, indipendentemente dallo stato della chiave di configurazione.

![Campi di destinazione](./media/Target_fields_1.png)

### <a name="child-entities"></a>Entità figlio 
Alcune entità hanno altre entità come origine dati o entità di dati compositi: le informazioni sulla chiave di configurazione per queste entità sono mostrate nel modulo Entità figlio. Utilizzare questo modulo in modo simile nella pagina elenco di entità descritta in precedenza. Il modulo dei campi di destinazione per l'entità figlio si comporta anche come descritto sopra.

![Campi di destinazione](./media/Target_fields_2.png)

### <a name="using-data-entities"></a>Utilizzo di entità di dati
Dopo aver compreso l'impatto completo, se esistente, delle chiavi di configurazione sulle entità di dati che si desidera utilizzare, è possibile utilizzare le entità di dati aggiungendole ai progetti di dati. 

### <a name="run-time-validations-for-configuration-keys"></a>Convalida del tempo di esecuzione per le chiavi di configurazione
Utilizzando i metadati della chiave di configurazione creati durante l'elenco di aggiornamento delle entità, le convalide dei tempi di esecuzione vengono eseguite nei seguenti casi d'uso.

-   Quando un'entità di dati viene aggiunta a un processo

-   Quando l'utente fa clic su "convalida" nell'elenco di entità

-   Quando l'utente carica un pacchetto di dati in un progetto di dati

-   Quando l'utente carica un modello in un progetto di dati

-   Quando un progetto di dati esistente viene caricato

-   Quando un modello viene caricato in un progetto di dati

-   Prima dell'esecuzione del processo di esportazione/importazione (batch, non batch, ricorrente, Odata)

-   Quando l'utente genera il mapping

-   Quando l'utente mappa i campi nell'interfaccia utente di mapping

-   Quando l'utente aggiunge solo "campi importabili"


### <a name="managing-configuration-key-changes"></a>Gestione delle modifiche alla chiave di configurazione
Ogni volta che si aggiornano le chiavi di configurazione a livello di entità, tabella o campo, l'elenco delle entità nel framework di gestione dei dati deve essere aggiornato. Questo processo garantisce che il framework riceva le ultime impostazioni della chiave di configurazione. Fino a quando l'elenco delle entità non viene aggiornato, il seguente avviso verrà visualizzato nella pagina dell'elenco delle entità. Le modifiche della chiave di configurazione aggiornata avranno effetto immediatamente dopo l'aggiornamento dell'elenco delle entità. Si consiglia di convalidare processi e progetti di dati esistenti per assicurarsi che funzionino come previsto dopo che le modifiche alle chiavi di configurazione sono state applicate.

![Campi di destinazione](./media/Target_fields_3.png)



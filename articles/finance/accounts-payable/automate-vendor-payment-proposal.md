---
title: Automatizzare le proposte di pagamento fornitore
description: Questo argomento spiega come le organizzazioni che pagano i fornitori in base a una programmazione ricorrente possono automatizzare il processo di generazione di proposte di pagamento fornitore.
author: kweekley
manager: AnnBe
ms.date: 04/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 2b4e6b42326ecbd07efe006afb23931849f5cf58
ms.sourcegitcommit: e544c51a68ad5daf748c0e877bdbde094ad40bd2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4445005"
---
# <a name="automate-vendor-payment-proposals"></a>Automatizzare le proposte di pagamento fornitore

[!include [banner](../includes/banner.md)]

Le organizzazioni che pagano i fornitori in base a una programmazione ricorrente ora possono automatizzare il processo di generazione di proposte di pagamento fornitore. Le automazioni delle proposte di pagamento fornitore definiscono i seguenti dettagli:

- Quando vengono eseguite le proposte di pagamento
- Quali criteri sono utilizzati per selezionare le fatture che devono essere pagate
- In quale giornale di registrazione dei pagamenti fornitore vengono salvati i pagamenti risultanti

Le automazioni delle proposte di pagamento non registrano automaticamente i pagamenti. Pertanto, è possibile continuare a utilizzare qualsiasi processo di convalida e flusso di lavoro attualmente utilizzato per approvare i pagamenti creati.

## <a name="define-the-occurrence-of-vendor-payment-proposals"></a>Definire l'occorrenza delle proposte di pagamento fornitore

Le automazioni delle proposte di pagamento fornitore utilizzano il framework di automazione dei processi. Diversi processi aziendali utilizzano questo framework per definire la ricorrenza di un processo selezionato. Per le proposte di pagamento fornitore, è possibile accedere all'automazione in **Contabilità fornitori \> Impostazione pagamenti \> Automazione processi**.

Innanzitutto, utilizzare l'opzione di automazione **Crea nuovo processo** e selezionare **Proposta pagamento fornitore**. Una procedura guidata consente di eseguire il processo di impostazione della proposta di pagamento fornitore.

## <a name="general-page"></a>Pagina Generale

Nella pagina **Generale** della procedura guidata, immettere il nome della proposta di pagamento fornitore che si sta creando. Ad esempio, se si pagano tutti i fornitori nazionali tramite assegno il lunedì, immettere un nome descrittivo come **Nazionali\_Assegno**. Il nome immesso viene visualizzato nella vista settimanale delle automazioni dei processi nell'area di lavoro **Pagamenti fornitore**.

Successivamente, definire il proprietario del giornale di registrazione dei pagamenti creato. Il proprietario è di solito l'addetto al pagamento della contabilità fornitori, responsabile del giornale di registrazione dei pagamenti che viene creato.

Le impostazioni restanti nella pagina sono generiche e sono utilizzate per definire il modello di occorrenza per questa versione della proposta di pagamento fornitore. Ad esempio, se un'occorrenza è per i pagamenti con assegni il lunedì, è possibile definirla in modo che venga eseguita settimanalmente e quindi selezionare il lunedì come giorno della settimana in cui viene eseguita. È inoltre possibile immettere un orario di programmazione anticipato, ad esempio le 2:00, in modo che l'automazione dei processi venga completata prima dell'inizio del giorno lavorativo successivo.

È importante comprendere che si sta utilizzando la procedura guidata per definire quando viene elaborata la proposta di pagamento fornitore. Non si sta definendo quando i pagamenti fornitore vengono generati, stampati e registrati. Nella vista settimanale, l'automazione dei processi per le proposte di pagamento fornitore sarà visualizzata nei giorni selezionati nel modello di occorrenza.

Per ulteriori informazioni sugli altri campi nella pagina **Generale**, consultare la documentazione sull'automazione dei processi.

## <a name="vendor-payment-proposal-page"></a>Pagina Proposta di pagamento fornitore

La pagina successiva nella procedura guidata è la pagina **Proposta di pagamento fornitore**. È utilizzata per definire i criteri per la selezione delle fatture fornitore che devono essere pagate. In generale, le stesse opzioni si trovano nella proposta di pagamento nel giornale di registrazione dei pagamenti fornitore. Tuttavia, vi sono alcune eccezioni. Ad esempio, tutte le date in questa pagina devono essere definite come date relative, poiché la data della proposta di pagamento cambia ogni volta che la proposta viene eseguita.

### <a name="journal-name"></a>Nome giornale di registrazione

Il campo **Nome giornale di registrazione** definisce il nome del giornale di registrazione in cui vengono creati i pagamenti fornitore. I risultati dell'automazione delle proposte di pagamento fornitore creeranno pagamenti nel giornale di registrazione definito, ma il giornale non viene registrato.

### <a name="from-date-and-to-date"></a>Data iniziale e data finale

Anziché definire una data iniziale e una data finale per selezionare le fatture in base alla data di scadenza o alla data dello sconto di cassa, è necessario utilizzare l'opzione **Definisci criteri di data finale** e il campo **Rettifica numero di giorni per data finale** per definire la data finale. Non esiste il concetto di data iniziale nelle automazioni delle proposte di pagamento.

Per impostazione predefinita, l'opzione **Definisci criteri di data finale** è impostata su **No**. Se si utilizza questo valore predefinito, il processo selezionerà tutte le fatture per il pagamento quando viene eseguito il processo, poiché non è stata definita alcuna data finale.

Se si imposta l'opzione **Definisci criteri di data finale** su **Sì**, utilizzare il campo **Rettifica numero di giorni per data finale** per definire la data in cui le fatture sono selezionate come numero di giorni specificato prima o dopo la data di esecuzione del processo. Il numero può essere positivo, negativo o 0 (zero). Il sistema pagherà quindi le fatture in cui le date di scadenza, o le date di sconto di cassa, sono il numero di giorni specificato prima o dopo la data di esecuzione del processo. Ad esempio, per tutte le fatture che scadono il venerdì o prima, la serie di pagamenti crea pagamenti per tutti i fornitori tramite assegno il mercoledì. In questo caso, impostare il campo **Rettifica numero di giorni per data finale** su **2**. Quando l'occorrenza della proposta di pagamento viene eseguita mercoledì 25 marzo, tutte le fatture la cui data di scadenza o data dello sconto di cassa è il 27 marzo o prima saranno selezionate per il pagamento.

### <a name="minimum-payment-date"></a>Data di pagamento minima

La data di pagamento minima definisce la prima data utilizzata durante la creazione dei pagamenti. È necessario dapprima impostare l'opzione **Definisci criteri data di pagamento minima** su **Sì**. Questa impostazione ti consente di utilizzare la funzionalità della data di pagamento minima. Se si imposta questa opzione su **Sì**, utilizzare il campo **Rettifica numero di giorni per data di pagamento minima** per definire la data di pagamento minima come numero di giorni specificato prima o dopo la data di esecuzione del processo. Il numero può essere positivo, negativo o 0 (zero). Ad esempio, la serie di pagamenti genera pagamenti il mercoledì per includere tutti i pagamenti la cui data di pagamento minima è il lunedì precedente. In questo caso, impostare il campo **Rettifica numero di giorni per data di pagamento minima** su **-2**.

Di seguito viene riportato un esempio che mostra come i campi per la data finale e la data di pagamento minima funzionano insieme. L'automazione delle proposte di pagamento è impostata per essere eseguita mercoledì. Il campo **Rettifica numero di giorni per data finale** è impostato su **1** per definire la data finale in base alla data di scadenza. Il campo **Rettifica numero di giorni per data di pagamento minima** è impostato su **-2**. Se l'automazione del processo di pagamento inizia mercoledì 25 marzo, tutte le fatture la cui data di scadenza è il 26 marzo o prima verranno incluse nella proposta di pagamento. Le proposte di pagamento verranno generate nel modo seguente:

- Tutte le fatture la cui data di scadenza è il 23 marzo avranno 23 marzo come data di pagamento.
- Le fatture la cui data di scadenza è il 24 marzo avranno 24 marzo come data di pagamento.
- Le fatture la cui data di scadenza è il 25 marzo avranno 25 marzo come data di pagamento.
- Le fatture la cui data di scadenza è il 26 marzo avranno 26 marzo come data di pagamento.

### <a name="summarized-payment-date"></a>Data pagamenti riepilogati

La data di pagamento riepilogativa viene utilizzata solo se il campo **Periodo** è impostato su **Totale** per il metodo di pagamento delle fatture. Se il campo **Periodo** è impostato su **Totale** per i metodi di pagamento, è necessario impostare l'opzione **Definisci criteri data di pagamento riepilogativa** su **Sì**. Se si imposta questa opzione su **Sì**, utilizzare il campo **Rettifica numero di giorni per data di pagamento riepilogativa** per definire la data di pagamento riepilogativa come numero di giorni specificato prima o dopo la data di esecuzione del processo. Il numero può essere positivo, negativo o 0 (zero). Ad esempio, la serie genera pagamenti il mercoledì e la società desidera creare un pagamento riepilogativo il mercoledì. In questo caso, impostare il campo **Rettifica numero di giorni per data di pagamento riepilogativa** su **0**.

### <a name="records-to-include"></a>Record da includere

Le opzioni di filtro possono ancora essere definite per la proposta di pagamento. Se viene definito un filtro, i criteri di filtro non vengono visualizzati nella pagina della procedura guidata. Tuttavia, possono essere visualizzati riaprendo il filtro.

I campi rimanenti per la proposta funzionano esattamente come per la proposta di pagamento nel giornale di registrazione dei pagamenti fornitore. Per informazioni sugli altri campi, vedere [Creare pagamenti fornitore utilizzando una proposta di pagamento](create-vendor-payments-payment-proposal.md).

> [!NOTE]
> Alcuni campi specifici di un paese e alcuni campi del settore pubblico non sono ancora disponibili nelle automazioni delle proposte di pagamento fornitore.

È consigliabile valutare se l'automazione sarà vantaggiosa per l'organizzazione, in base alle proprie esigenze.

## <a name="view-the-results-of-a-vendor-payment-proposal-automation"></a>Visualizzare i risultati di un'automazione delle proposte di pagamento fornitore

Dopo la creazione della serie di automazioni delle proposte di pagamento fornitore, le occorrenze di ciascun pagamento sono visualizzate nella vista settimanale delle automazioni dei processi. Per i pagamenti fornitore, la vista settimanale delle automazioni dei processi è stata aggiunta all'area di lavoro **Pagamenti fornitore** e alla pagina **Automazione processi**.

[![Vista settimanale delle automazioni dei processi nell'area di lavoro Pagamenti fornitore](./media/vendor-payment-proposal-1.png)](./media/vendor-payment-proposal-1.png)

La vista settimanale delle automazioni dei processi nell'area di lavoro **Pagamenti fornitore** mostra solo le automazioni delle proposte di pagamento fornitore. Mostra tutte le occorrenze dei pagamenti per la settimana corrente, per tutte le persone giuridiche per le quali l'utente connesso dispone di autorizzazioni di sicurezza. Ad esempio, se l'addetto ai pagamenti delle contabilità fornitori è responsabile dei pagamenti nelle società USMF e USSI, vedrà le occorrenze dell'automazione delle proposte di pagamento fornitore per queste due società ma non per altre società.

[![Vista settimanale delle automazioni dei processi per le società USMF e USSI](./media/vendor-payment-proposal-2.png)](./media/vendor-payment-proposal-2.png)

Ogni occorrenza mostra la società in cui il giornale di registrazione dei pagamenti è stato o verrà creato. Se i pagamenti vengono creati utilizzando pagamenti centralizzati, la società visualizzata è la società in cui i pagamenti verranno creati. L'evento non mostra necessariamente quali fatture della società verranno pagate.

Viene inoltre visualizzato il nome di ciascuna occorrenza per consentire l'identificazione della proposta di pagamento.

Viene inoltre visualizzato lo stato di ciascuna occorrenza. Vengono utilizzati i seguenti stati:

- **Programmata** - La proposta di pagamento è programmata, ma non è ancora stata eseguita.
- **Errore** - La proposta di pagamento è stata eseguita, ma si è verificato un errore. È possibile visualizzare gli errori selezionando il pulsante **Visualizza risultati**.
- **Completata** - La proposta di pagamento è stata eseguita correttamente. È possibile visualizzare i pagamenti selezionando il collegamento **Visualizza pagamenti**. Questo collegamento apre il giornale di registrazione dei pagamenti creato dall'occorrenza.

Dopo aver creato i pagamenti, è possibile visualizzare gli importi dei pagamenti nel giornale di registrazione. Gli importi sono visualizzati nelle valute delle transazioni. Ad esempio, se il giornale di registrazione dei pagamenti contiene pagamenti in dollari statunitensi e canadesi, viene visualizzato il totale dei pagamenti per ciascuna valuta. 

Il giornale di registrazione dei pagamenti può essere eliminato dopo essere stato creato tramite l'automazione dei processi. Se un pagamento viene completamente eliminato, si verificano i seguenti eventi:

- Lo stato dell'automazione dei processi della settimana rimane **Completata**.
- Il processo rimuove i totali dei pagamenti e il collegamento **Visualizza pagamenti** viene sostituito da un pulsante **Visualizza risultati**.
- Quando si visualizzano i risultati, si riceve un messaggio che informa dell'eliminazione del giornale di registrazione originale.

Dopo l'eliminazione di un pagamento, le fatture vengono nuovamente aperte per il pagamento. Una nuova occorrenza può quindi essere creata per pagare nuovamente le fatture.

## <a name="edit-a-vendor-payment-proposal-automation"></a>Modificare un'automazione delle proposte di pagamento fornitore

Il framework di automazione dei processi consente di modificare il pagamento, la serie e le occorrenze create per la proposta di pagamento. La serie può essere modificata nella pagina **Automazione processi** o nella vista settimanale delle automazioni dei processi. Ad esempio, se il responsabile della contabilità fornitori decide di generare tutti gli assegni per i fornitori nazionali il mercoledì anziché il lunedì, può trovare un'occorrenza nella vista settimanale e selezionare **Visualizza/Modifica - Serie**. Se si modifica una serie, il sistema richiede di specificare se la modifica deve essere apportata a tutte le ricorrenze esistenti o solo a nuove ricorrenze. Le occorrenze storiche il cui stato è **Completata** o **Errore** non verranno modificate.

È inoltre possibile aggiungere una nuova occorrenza o modificare un'occorrenza esistente. Ad esempio, la successiva occorrenza di proposte di pagamento è programmata per mercoledì 1° gennaio, ma questa data è un giorno festivo. L'occorrenza può essere modificata nella vista settimanale delle automazioni dei processi o nella pagina **Automazione processi**. Viene aperta una pagina che mostra i dettagli della programmazione e i criteri delle proposte di pagamento. Qui è possibile modificare l'ora e la data programmate. È inoltre possibile modificare i criteri delle proposta di pagamento, se necessario. Ad esempio, se si cambia la data programmata dell'occorrenza di pagamento dal 1° gennaio al 2 gennaio, è possibile che si desideri modificare anche le date relative della data finale.

È anche possibile disabilitare un'occorrenza o una serie. Per disabilitare un'occorrenza e sospenderne l'elaborazione, selezionarla nella vista settimanale delle automazioni dei processi, quindi selezionare **Disabilita**. È possibile disabilitare una serie nella pagina **Automazione processi**.

## <a name="security-for-payment-proposal-automations"></a>Sicurezza per le automazioni delle proposte di pagamento fornitore

I seguenti compiti e privilegi sono stati aggiunti per le automazioni delle proposte di pagamento fornitore. Questi compiti e privilegi sono le impostazioni di sicurezza predefinite, ma possono essere modificati in base ai requisiti dell'organizzazione. Ad esempio, se una ricorrenza della progammazione può essere modificata e creata non solo dal responsabile della contabilità fornitori ma anche dall'addetto ai pagamenti della contabilità fornitori, assegnare il compito **Gestire occorrenze programmazione** alla persona con il ruolo di addetto al pagamento della contabilità fornitori.

| Compito                              | Ruolo                                                                       | Privilegi |
|-----------------------------------|----------------------------------------------------------------------------|------------|
| Gestire serie programmazione          | Responsabile contabilità fornitori                                                   | Questo compito concede i diritti di creare e gestire la serie e le occorrenze delle automazioni delle proposte di pagamento attraverso i seguenti privilegi:<ul><li>Gestire occorrenze programmazione</li><li>Gestire serie programmata</li><li>ProcessScheduleOccurrenceListMaintain</li><li>Visualizzare vista settimanale occorrenze</li></ul> |
| Richiedere informazioni su occorrenze programmazione | Addetto ai pagamenti della contabilità fornitori, Addetto ai pagamenti centralizzati della contabilità fornitori | Questo compito concede i diritti di visualizzare le occorrenze delle automazioni delle proposte di pagamento mediante i seguenti privilegi:<ul><li>Visualizzare occorrenze programmazione</li><li>Visualizzare vista settimanale occorrenze</li></ul> |
| Richiedere informazioni su serie programmata      | Nessuno                                                                       | Questo compito concede i diritti di visualizzare le impostazioni della serie e delle occorrenze mediante i seguenti privilegi:<ul><li>Visualizzare occorrenze programmazione</li><li>Visualizza pagina elenco occorrenze</li><li>Visualizzare vista settimanale occorrenze</li></ul>|
| Gestire occorrenze programmazione     | Nessuno                                                                       | Questo compito garantisce i diritti di creare e gestire un'occorrenza mediante i seguenti privilegi:<ul><li>Gestire occorrenze programmazione</li><li>Visualizzare vista settimanale occorrenze</li></ul> |

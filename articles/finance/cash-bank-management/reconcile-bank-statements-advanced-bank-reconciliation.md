---
title: Riconciliare rendiconti bancari utilizzando la riconciliazione bancaria avanzata
description: La funzionalità di riconciliazione bancaria avanzata consente di importare rendiconti bancari elettronici e riconciliarli automaticamente con le transazioni bancarie in Microsoft Dynamics 365 Finance. In questo argomento viene descritto il processo di riconciliazione.
author: saraschi2
manager: AnnBe
ms.date: 06/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankReconciliationWorksheet
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 98243
ms.assetid: 9df13adf-aa9d-4f6b-bde6-25a214611692
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c13203217af1788fe3b8a6f9bbf805e03b650a0d
ms.sourcegitcommit: 8a1621327568edf49758b70964e0a3e637527e1b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2020
ms.locfileid: "3497147"
---
# <a name="reconcile-bank-statements-by-using-advanced-bank-reconciliation"></a>Riconciliare rendiconti bancari utilizzando la riconciliazione estratti conto avanzata

[!include [banner](../includes/banner.md)]

La funzionalità di riconciliazione bancaria avanzata consente di importare rendiconti bancari elettronici e riconciliarli automaticamente con le transazioni bancarie in Dynamics 365 Finance. In questo argomento viene descritto il processo di riconciliazione.  

<a name="import-an-electronic-bank-statement"></a>Importare un rendiconto bancario elettronico
-----------------------------------

Si importano i rendiconti bancari utilizzando l'azione **Importa rendiconto** nella pagina **Rendiconti bancari**. Sul rendiconto bancario, il conto bancario è identificato tramite una combinazione di valori che vengono impostati nei dettagli del conto bancario. Questi valori comprendono il nome della banca, il numero di conto bancario, il numero di registrazione, il codice SWIFT (Society for Worldwide Interbank Financial Telecommunication) e il numero IBAN (International Bank Account Number). 

È possibile caricare un rendiconto bancario che contiene informazioni per un singolo conto o più conti. Se sono presenti più conti, i conti possono essere in persone giuridiche diverse.

-   Per importare un singolo file di rendiconto bancario per un singolo conto, impostare l'opzione **Importa rendiconto per più conti bancari in tutte le persone giuridiche** su **No** e selezionare il conto bancario associato con il rendiconto. Fare clic su **Sfoglia** per selezionare il file di rendiconto bancario associato, quindi fare clic su **Carica**.
-   Per importare un singolo file di rendiconto bancario per più conti, impostare l'opzione **Importa rendiconto per più conti bancari in tutte le persone giuridiche** su **Sì**. Fare clic su **Sfoglia** per selezionare il file di rendiconto bancario associato, quindi fare clic su **Carica**.

Se alcuni rendiconti nel file elettronico non possono essere associati a un conto bancario o se sono associati a più conti bancari tramite i campi di identificazione, non verranno importati. Tuttavia, altri rendiconti nel file possono comunque essere importati. L'utente riceve un messaggio indicante che l'importazione dei rendiconti bancari non è riuscita per specifici conti bancari. Tenere presente che l'utente che importa il file di rendiconto bancario deve avere accesso a una persona giuridica per importare i rendiconti per i conti bancari di tale persona giuridica. 

È possibile usare un file ZIP per caricare più file di rendiconto in Finance in un unico processo. Per importare più file di rendiconto bancario per più conti, combinare tutti i file di rendiconto bancario in un unico file zip. Nella finestra di dialogo **Importa rendiconti bancari**, impostare l'opzione **Importa rendiconto per più conti bancari in tutte le persone giuridiche** su **Sì**. Fare clic su **Sfoglia** per selezionare il file zip che contiene i file di rendiconto bancario, quindi fare clic su **Carica**. Il processo di importazione riconoscerà il file ZIP e caricherà ciascun rendiconto incluso in esso, indipendentemente dalla persona giuridica del conto bancario.

Un'opzione **Riconcilia dopo l'importazione** è disponibile. Quando questa opzione è impostata su **Sì**, il sistema automaticamente convalida il rendiconto bancario, crea una nuova riconciliazione e un foglio di lavoro estratti conto ed esegue il set di regole di abbinamento predefinite quando viene caricato il rendiconto bancario. Questa funzionalità consente di automatizzare il processo fino al punto in cui le transazioni devono essere abbinate manualmente.

## <a name="validate-the-bank-statement"></a>Convalidare il rendiconto bancario
Per convalidare un rendiconto, fare clic su **Convalida** nella pagina **Rendiconti bancari**. I rendiconti bancari devono essere convalidati prima di essere riconciliati. Questo passaggio viene completato automaticamente se l'opzione **Riconcilia dopo l'importazione** è stata impostata su **Sì** al momento dell'importazione. 

La convalida del rendiconto bancario consente di verificare i dettagli seguenti:

-   Il rendiconto bancario corrisponde al conto bancario selezionato.
-   La valuta del rendiconto bancario corrisponde alla valuta del conto bancario.
-   Il saldo iniziale del rendiconto è uguale al saldo finale del rendiconto precedente per il conto bancario.
-   La data non si sovrappone alla data di un altro rendiconto bancario per lo stesso conto bancario.
-   Non vi sono intervalli nelle date dei rendiconti per il conto bancario.
-   Le date nelle righe del rendiconto sono comprese tra la data di inizio e la data di fine del rendiconto bancario.
-   Il saldo iniziale e gli importi di riga riepilogati sono uguali al saldo finale.

Al termine della convalida, lo stato del rendiconto bancario viene aggiornato a **Convalidato**. Un rendiconto bancario devono essere convalidato prima di essere riconciliato.

## <a name="reconcile-the-bank-statement"></a>Riconciliare il rendiconto bancario
Dopo aver importato un rendiconto bancario elettronico e convalidato il rendiconto nella pagina **Rendiconti bancari**, è possibile riconciliare il rendiconto bancario utilizzando le pagine **Riconciliazione estratti conto** e **Foglio di lavoro riconciliazione estratti conto**. 

Nella pagina **Riconciliazione estratti conto** fare clic su **Nuovo** per creare una nuova riconciliazione e quindi selezionare il conto bancario del rendiconto che è stato importato. Un conto bancario può avere una sola riconciliazione bancaria aperta. La data limite determina le transazioni dei rendiconti bancari e le transazioni bancarie di Operations incluse nel foglio di lavoro di riconciliazione. Per impostazione predefinita, viene utilizzata la data di sistema corrente come data limite, ma è possibile modificare la data per la riconciliazione. Le informazioni di intestazione rimanenti vengono ottenute automaticamente dal rendiconto. Questo passaggio viene completato automaticamente se l'opzione **Riconcilia dopo l'importazione** è stata impostata su **Sì** al momento dell'importazione. 

Nella pagina **Riconciliazione bancaria**, fare clic su **Foglio di lavoro** per aprire la pagina **Foglio di lavoro riconciliazione estratti conto**. Se l'opzione **Riconcilia dopo l'importazione** è stata impostata su **Sì**, il set di regole di abbinamento predefinite viene eseguito automaticamente per la riconciliazione. Per eseguire manualmente le regole di abbinamento, fare clic su **Esegui regole di abbinamento** per selezionare i set di regole di abbinamento o le regole di abbinamento da eseguire sulle transazioni bancarie. Se si dispone di molte transazioni da elaborare, è possibile completare questo passaggio come processo batch. 

La pagina **Foglio di lavoro riconciliazione estratti conto** ha quattro griglie che contengono transazioni. Le due griglie superiori mostrano le transazioni dal rendiconto bancario e Operations che non sono ancora state abbinate. Le due griglie inferiori mostrano le transazioni abbinate. La scheda **Dettagli transazione del rendiconto bancario** mostra i dettagli per la transazione del rendiconto bancario non abbinata selezionata nella griglia superiore. 

Esistono tre modi per abbinare o riconciliare transazioni del rendiconto bancario:

-   Abbinare le transazioni con le transazioni bancarie di Operations.
-   Abbinare le transazioni con una transazione del rendiconto bancario di storno.
-   Contrassegnare le transazioni come **Nuove**, in modo che possono essere registrate in un secondo momento come una transazione bancaria in Finance.

Per abbinare le transazioni manualmente, selezionare le transazioni nella griglia **Transazioni rendiconto bancario**, selezionare le transazioni corrispondenti nella griglia **Transazioni bancarie Operations** e quindi fare clic su **Associa**. Le transazioni selezionate vengono spostate dalle griglie superiori delle transazioni non abbinate a quelle inferiori delle transazioni abbinate. Inoltre, gli importi totali abbinati e non abbinati vengono aggiornati. È possibile avere abbinamenti di transazioni uno a uno, molti-a-uno e molti-a-molti. Gli abbinamenti devono seguire le regole per le differenze di date consentite e il mapping dei tipi di transazione. Queste regole vengono impostate nella pagina **Parametri di gestione cassa e banche**.

Potrebbero verificarsi differenze in centesimi nella riconciliazione. È possibile abbinare una transazione di rendiconto bancario singola e una singola transazione bancaria Operations che presentano differenze di centesimi se le differenze in centesimi rientrano nell'importo di tolleranza definito dal campo **Differenza in centesimi consentita** del conto bancario. L'importo viene mostrato nel campo **Importo correttivo** nella transazione bancaria Operations abbinata. Quando la riconciliazione degli estratti conto è contrassegnata come riconciliata, le rettifiche vengono registrate automaticamente utilizzando il conto principale definito nel tipo di transazione bancaria associato. Le correzioni non sono supportate per i tipi di documento **Assegno** e **Deposito**. 

Gli storni di transazioni di rendiconto bancario vengono abbinati utilizzando il foglio di lavoro di riconciliazione. Se gli importi sono opposti e una delle transazioni è contrassegnata come uno storno, possono essere abbinate due righe del rendiconto. È inoltre possibile impostare una regola di abbinamento per l'azione **Cancella righe del rendiconto di storno**.

Le transazioni bancarie stornate di Operations devono essere riconciliate utilizzando la pagina **Transazioni bancarie Operations**. Se i documenti hanno stesso conto corrente bancario, tipo di documento e riferimento del pagamento, e se hanno importi opposti, è possibile riconciliare tra loro due transazioni bancarie di Operations. È inoltre possibile riconciliare un singolo assegno annullato per impedire che le transazioni vengano visualizzati nel foglio di lavoro di riconciliazione. 

Se esistono nuove transazioni avviate da banca, ad esempio interessi, commissioni e spese, che non sono ancora in Finance, è possibile aggiungerle a un giornale di registrazione associato alla riconciliazione del rendiconto bancario selezionato. Selezionare una transazione del rendiconto bancario nella griglia **Transazioni rendiconto bancario** per le transazioni non abbinate, quindi scegliere **Contrassegna come nuovo**. Lo stato della transazione viene impostato su **Nuovo**, e la transazione viene spostata nella griglia **Transazioni rendiconto bancario** griglia per le transazioni abbinate. Si registreranno le transazioni contrassegnate come **Nuovo** in un momento successivo, dalla pagina **Rendiconto bancario**. 

È possibile annullare l'abbinamento delle transazioni che erano state abbinate in modo non corretto. Selezionare la transazione del rendiconto bancario abbinata e quindi fare clic su **Annulla associazione**. Tutte le transazioni associate vengono nuovamente spostate alle griglie superiori per le transazioni non abbinate e gli importi totali abbinati e non abbinati vengono aggiornati. 

Dopo il completamento del processo di riconciliazione, è necessario contrassegnare il foglio di lavoro riconciliazione estratti conto come riconciliato.  Questo processo registrerà automaticamente gli importi correttivi utilizzando i conti impostati nella pagina **Tipo di transazione bancaria**.  La riconciliazione estratti conto per un rendiconto può essere contrassegnata come riconciliata in qualsiasi momento, anche se sono presenti righe del rendiconto bancario non ancora abbinate.  Le transazioni non abbinate verranno spostate automaticamente nel foglio di lavoro di riconciliazione successivo come transazioni del rendiconto bancario non abbinate da riconciliare.  Tenere presente che se si contrassegna una riconciliazione del rendiconto bancario come riconciliata, l'operazione non può essere annullata.  La riconciliazione non sarà più modificabile e non sarà più possibile aggiornarla.

## <a name="post-new-transactions-that-are-associated-with-the-reconciliation"></a>Registare nuove transazioni associate alla riconciliazione
Le transazioni del rendiconto bancario contrassegnate come **Nuovo** nel foglio di lavoro di riconciliazione vengono registrate nella pagina **Rendiconto bancario**. Nella pagina **Rendiconto bancario**, selezionare l'ID del rendiconto per visualizzarne i dettagli. Nel menu **Contabilità**, è possibile utilizzare le opzioni **Visualizza distribuzioni** e **Visualizza contabilità** per visualizzare i dettagli dietro le nuove transazioni e i movimenti contabili associati. Selezionare l'opzione **Registra** per registrare le righe del rendiconto bancario contrassegnate come **Nuovo** nella contabilità generale. Notare che la registrazione può essere completata solo una volta per ogni rendiconto bancario.




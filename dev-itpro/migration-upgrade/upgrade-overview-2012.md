---
title: Aggiornare Dynamics AX 2012 a Dynamics 365 for Finance and Operations, Enterprise edition
description: Questo argomento descrive il processo che i clienti che eseguono attualmente Microsoft Dynamics AX 2012 possono utilizzare per spostare dati e codice in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.
author: tariqbell
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Operations Platform
ms.search.region: Global
ms.author: tabell
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: Platform update 8
ms.translationtype: Human Translation
ms.sourcegitcommit: 6816e3820ab77c71bbf9bde4a068375448331671
ms.openlocfilehash: 13507fcf9c0d626709aeb4e00a8632411204c20f
ms.contentlocale: it-it
ms.lasthandoff: 06/15/2017

---

# <a name="upgrade-microsoft-dynamics-ax-2012-to-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition"></a>Aggiornare Microsoft Dynamics AX 2012 a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition

[!include[banner](../includes/banner.md)]

Nell'aggiornamento 8 della piattaforma, Microsoft Dynamics 365 for Finance and Operations, Enterprise edition offre un percorso di aggiornamento che i clienti che attualmente eseguono Microsoft Dynamics AX 2012 possono utilizzare per spostare dati e codice in Finance and Operations. Il processo di aggiornamento si basa sui seguenti elementi:

- Gli strumenti per consentire di trasferire il codice delle applicazioni personalizzate esistenti da AX 2012.
- Un processo di aggiornamento dei dati che consente di trasferire il database. Di conseguenza, è possibile aggiornare l'intero storico transazionale.

## <a name="overview"></a>Panoramica

Il processo di aggiornamento globale può essere visto come un processo a tre complesse fasi: analisi, esecuzione e convalida.

Il diagramma seguente illustra il processo di aggiornamento end-to-end e le attività che consideriamo parte di ciascuna fase. 

![Processo di aggiornamento](./media/upgrade-process.png)

## <a name="analyze"></a>Analizza

Le attività nella fase di analisi aiutano a stimare le risorse richieste per l'aggiornamento. Aiutano inoltre a preparare il piano di progetto. Queste attività possono essere eseguite prima di acquistare Finance and Operations. Aiutano a prendere una decisione di acquisto più informata fornendo i dati sulle attività e le risorse che saranno necessarie.

### <a name="sign-up-for-a-public-preview-in-lcs"></a>Iscriversi a un'anteprima pubblica in LCS

Per eseguire le attività di analisi prima di acquistare Finance and Operations, è possibile iscriversi a un'anteprima pubblica. L'anteprima pubblica consente di distribuire i propri ambienti Finance and Operations. Permette inoltre di accedere agli strumenti di Microsoft Dynamics Lifecycle Services (LCS) che vengono utilizzati per valutare l'ambiente AX 2012 in uso e il codice personalizzato esistente.

Se si dispone di un progetto LCS esistente per AX 2012, è ancora possibile registrarsi per un nuovo progetto aggiuntivo per valutare Finance and Operations.

Per informazioni su come ottenere un'anteprima pubblica per i clienti, visitare la pagina https://mbs.microsoft.com/customersource/global/AX/news-events/news/Microsoft_Dynamics_AX_Public_Preview.

Per informazioni su come ottenere un'anteprima pubblica per i partner, visitare la pagina https://mbs.microsoft.com/partnersource/global/news-events/news/Microsoft_Dynamics_AX_Public_Preview.

L'anteprima pubblica è diversa da una [versione di valutazione di 30 giorni](https://aka.ms/D365OperationTrials). Le versioni di valutazione di 30 giorni forniscono un'istanza distribuita di Finance and Operations che è possibile utilizzare per esplorare e valutare l'applicazione. Tuttavia, le attività di analisi richiedono l'esperienza e gli strumenti completi di LCS.

### <a name="select-the-upgrade-methodology"></a>Selezionare la metodologia di aggiornamento
Nel nuovo progetto LCS, impostare la metodologia di progetto su **Aggiornare AX 2012 a Dynamics 365 for Operations**. Questa metodologia viene effettuata specialmente per i clienti di AX 2012 che intendono eseguire l'aggiornamento. Descrive nel dettaglio le tre fasi e fornisce i collegamenti a tutta la documentazione di supporto relativa al processo.

![Metodologia di aggiornamento(./media/methodology.png)
 
### <a name="run-the-upgrade-analyzer"></a>Eseguire lo strumento Analisi aggiornamenti
Lo strumento Analisi aggiornamenti viene eseguito in relazione all'ambiente AX 2012 e identifica le attività da svolgere per preparare che l'ambiente AX 2012 in modo che l'aggiornamento risulti un'esperienza semplice e meno costosa:

- **Pulitura dati** - Questo processo consente di identificare i dati che è possibile rimuovere senza causare perdita di funzionalità. Lo strumento identifica vari tipi di dati che è possibile ridurre eseguendo un processo di pulitura. Per ogni tipo di dati viene fornita una descrizione dell'impatto della pulitura. Si decide quindi se eseguire il processo di pulitura. Parte del costo della sottoscrizione a Finance and Operations dipende dalla dimensione del database. Di conseguenza, riducendone la dimensione si riduce quel componente del costo della sottoscrizione e si riduce anche il tempo necessario per il passaggio dell'aggiornamento alla fase operativa. Un database più piccolo aiuta a garantire un aggiornamento più veloce.
- **Configurazione SQL** - Questo processo esamina la configurazione SQL e consiglia alcuni modi per ottimizzarla. Assicurando prestazioni ottimali di SQL, questo processo riduce il tempo necessario per il passaggio dell'aggiornamento alla fase operativa.
- **Funzionalità deprecate** - Questo processo identifica le funzionalità attualmente in uso ma che non sono disponibili in Finance and Operations. Il processo aiuta quindi a individuare in anticipo le differenze nelle funzionalità. Fornisce inoltre suggerimenti per alternative.

Inoltre, come parte di questo passaggio, è necessario installare KBXXXXXXX nell'ambiente AX 2012. Questo hotfix fornisce un elenco di controllo pre-aggiornamento. Nell'ambiente AX 2012, è possibile utilizzare questo elenco di controllo per immettere dati che verranno richiesti per la procedura di aggiornamento. Ad esempio, in un'attività dell'elenco di controllo pre-aggiornamento, si immettono le informazioni di accesso ad Active Directory di Microsoft Azure (Azure AD) per ogni utente corrente di AX 2012, in modo che ciascun utente potrà accedere a Finance and Operations.

L'output di questo passaggio diventa la sequenza di lavoro nel piano di progetto dell'aggiornamento per gli amministratori di sistema di AX 2012.

Per ulteriori informazioni, vedere [Analisi: utilizzare lo strumento Analisi aggiornamenti per pianificare la migrazione](upgrade-analyzer-tool.md).

### <a name="run-the-code-upgrade-estimation-tools"></a>Eseguire gli strumenti di stima di aggiornamento codice
Questo passaggio prende il codice da AX 2012, lo converte nel nuovo formato e fornisce commenti e suggerimenti sui conflissi che uno sviluppatore dovrà risolvere in un secondo momento. Questo passaggio rappresenta la base per la stima del costo di aggiornamento del codice.

Per completare questo passaggio, è necessario esportare il codice da AX 2012 come esportazione dell'archivio modelli e caricarlo nello strumento di aggiornamento del codice di LCS. Lo strumento di aggiornamento del codice produce una versione aggiornata del codice e un report sui conflitti rimanenti che devono essere risolti. Lo sviluppatore può quindi esaminare sia il codice aggiornato che il report per determinare le attività che saranno necessarie per aggiornare la base di code.

L'output di questo passaggio rappresenta la sequenza di lavoro nel piano di progetto dell'aggiornamento per gli sviluppatori di Microsoft Dynamics AX.

Per ulteriori informazioni, vedere [Analisi: stimare l'impegno di aggiornamento del codice](analyze-code-upgrade.md).

### <a name="deploy-a-demo-environment"></a>Distribuire un ambiente di dimostrazione
Gli ambienti di dimostrazione sono ambienti predefiniti contenenti dati dimostrativi (non i propri dati) e codice standard (senza personalizzazioni). Si consiglia di distribuire un ambiente di dimostrazione per valutare le nuove funzionalità e per eseguire un'analisi degli scostamenti di base dei processi standard che vengono utilizzati in AX 2012 ma che potrebbero essere cambiati in Finance and Operations. È possibile distribuire questi ambienti dimostrativi in Azure o scaricarli come macchina virtuale (VM) da eseguire nel proprio hardware. Se si distribuisce questi ambienti in Azure, è necessario fornire la propria sottoscrizione di Azure, in quanto si sta utilizzando un progetto di anteprima pubblica e non si ha ancora acquistato la sottoscrizione a Finance and Operations.

L'output di questo passaggio rappresenta la sequenza di lavoro nel piano di progetto dell'aggiornamento per gli utenti aziendali o operativi.

Per ulteriori informazioni, vedere [Analisi: distribuire un ambiente sandbox](analysis-sandbox.md)

### <a name="create-a-project-plan"></a>Creare un piano di progetto
Un modello per un piano di progetto viene fornito nella metodologia di aggiornamento. In questo passaggio, l'output dei passaggi precedenti della fase di analisi viene utilizzato per compilare il piano del progetto di aggiornamento. Nel piano di progetto verranno inclusi anche tutti i dettagli dei test: test di aggiornamento dei dati, test di passaggio, iterazioni dei passaggi dei test funzionali e dettagli relativi alle varie assegnazioni di risorse per tali attività.

In questa fase il piano di progetto fornisce un punto di informazioni che può aiutare a comprendere il tempo e il costo di un aggiornamento a Finance and Operations.

## <a name="execute"></a>Elabora
Durante la fase di esecuzione si eseguono le attività pianificate durante la fase di analisi. Per passare alla fase di esecuzione è necessario acquistare Finance and Operations e disporre di risorse disponibili a lavorare all'aggiornamento.

### <a name="switch-to-the-lcs-implementation-project"></a>Passare al progetto di implementazione di LCS
Il progetto di anteprima pubblica utilizzato per la fase di analisi è servito a questo scopo. Ora è possibile metterlo da parte. Per i passaggi rimanenti sono necessari solo il piano di progetto creato all'ultimo passaggio della fase di analisi.

Quando si acquista una sottoscrizione a Finance and Operations, si ricevono i dettagli su come sottoscrivere un nuovo progetto LCS. Questo progetto è definito progetto di implementazione e sarà il nuovo progetto LCS permanente per la sottoscrizione, fintanto che si mantiene tale sottoscrizione. Questo progetto differisce dal progetto di anteprima pubblica in quanto è gestito da Microsoft. Di conseguenza, il progetto presenta le caratteristiche seguenti:

- Tutti gli ambienti nel progetto sono ospitati in Azure.
- La sottoscrizione di Azure che è associata al progetto è gestita da Microsoft. Di conseguenza, i costi di Azure non vengono fatturati separatamente. I costi sono coperti dalla sottoscrizione di Finance and Operations.
- L'ambiente di produzione nel progetto è mantenuto da Microsoft. Di conseguenza, le distribuzioni del codice, gli aggiornamenti e la manutenzione dell'infrastruttura sono gestiti direttamente da Microsoft, non dal proprio personale. 

### <a name="perform-the-ax-2012-preparation-tasks"></a>Eseguire le attività di preparazione di AX 2012
Completare le attività individuare dallo strumento Analisi aggiornamenti e che sono documentate nel piano del progetto di aggiornamento. Queste attività devono essere eseguite dall'amministratore di sistema di Microsoft Dynamics AX e dall'amministratore del database (DBA).

[Aggiornamento dei dati da AX 2012 a Dynamics 365 for Operations - Elenco di controllo pre-aggiornamento in AX 2012](prepare-data-upgrade.md)

### <a name="perform-code-upgrade"></a>Eseguire l'aggiornamento del codice
Completare le attività pianificate durante la fase di stima di aggiornamento codice della fase di analisi. Queste attività devono essere eseguite dagli sviluppatori.

Da questo punto in poi è necessario congelare eventuali modifiche al codice in AX 2012. Devono essere consentite solo le modifiche al codice di emergenza in AX 2012. Eventuali modifiche devono essere migrate manualmente alla nuova base di codice.

### <a name="develop-new-code"></a>Sviluppare il nuovo codice
Completare le attività dell'analisi degli scostamenti che è stata eseguita durante il passaggio "Distribuire un ambiente di dimostrazione" nella fase di analisi. Queste attività saranno probabilmente una combinazione di attività funzionali che definiscono la configurazione e di attività di sviluppo per le personalizzazioni che sono correlate alle nuove funzionalità che verranno acquisite.

### <a name="data-upgrade-development-environment"></a>Aggiornamento dei dati (ambiente di sviluppo)
Dopo aver completato le attività di aggiornamento dei codice, è possibile aggiornare per la prima volta il database di AX 2012 a Finance and Operations. Il primo aggiornamento si verifica in un ambiente di sviluppo, in modo da poter correggere più facilmente eventuali problemi che vengono individuati in questa fase. In un ambiente di sviluppo, possibile eseguire immediatamente il debug di un problema, il codice può essere modificato e l'aggiornamento può essere ripetuto in pochi minuti. Gli ambienti sandbox di dimensioni più grandi non offrono questa agilità e occorrono varie ore per eseguire il debug e correggere i problemi, aggiornare il codice, distribuire il codice aggiornato e rieseguire l'aggiornamento.

Nella seguente illustrazione viene mostrato il processo. Eseguire semplicemente il backup del database di AX 2012, caricarlo in Azure, ripristinarlo nell'ambiente di Finance and Operations, quindi eseguire l'aggiornamento dei dati.

![Aggiornamento dei dati in un ambiente di sviluppo](./media/data-upgrade-dev.png)
 
L'aggiornamento dei dati viene eseguito attraverso uno speciale tipo di pacchetto distribuibile. Lo stesso meccanismo viene utilizzato per distribuire il nuovo codice di Finance and Operations da un ambiente a un altro.

Il framework sottostante che viene utilizzato per convertire i dati nel database durante questo processo è in gran parte uguale al framework di aggiornamento in AX 2012 che è basato sui processi batch X++ che eseguono le classi **ReleaseUpdatexxx**.

per i dettagli, vedere [Aggiornamento dei dati da AX 2012 a Dynamics 365 for Operations in un ambiente di sviluppo](data-upgrade-2012.md).

### <a name="data-upgrade-sandbox-environments"></a>Aggiornamento dei dati (ambienti sandbox)
Quando l'aggiornamento dei dati in un ambiente di sviluppo è completato, lo stesso processo può essere eseguito in un ambiente sandbox. L'ambiente sandbox è un ambiente in cui gli utenti aziendali e i membri del team funzionale possono testare i processi aziendali utilizzando i dati e il codice aggiornati di AX 2012.

Nella figura seguente è illustrato il processo per l'esecuzione dell'aggiornamento dei dati in un ambiente sandbox. La differenza qui che è viene utilizzato lo strumento bacpac al posto del tradizionale backup SQL. Questo strumento è necessario per eseguire la conversione tra Microsoft SQL Server e il database SQL di Azure. Si tratta di uno strumento SQL standard e non è specifico di Finance and Operations.

![Aggiornamento dei dati in un ambiente sandbox](./media/data-upgrade-sandbox.png)

Per i dettagli, vedere [Aggiornamento dei dati da AX 2012 a Dynamics 365 for Operations in un ambiente sandbox](upgrade-data-sandbox.md).
 
## <a name="validate"></a>Convalida
Nella fase di convalida si disporrà di ambienti che includono codice personalizzato aggiornato e dati aggiornati. Questa fase descrive il processo di convalida e di test del corretto funzionamento dell'ambiente aggiornato. Descrive inoltre il processo di preparazione alla fase operativa.

### <a name="perform-cutover-testing-and-create-a-cutover-plan"></a>Eseguire il test di passaggio e creare un piano di passaggio
Il termine _passaggio_ viene utilizzato qui per descrivere il processo finale di rendere disponibile il nuovo sistema. Questo processo è costituito da attività che vengono eseguite dopo la disattivazione di AX 2012 e prima dell'attivazione di Finance and Operations. 

Lo scopo dei test è di esercitare il processo di passaggio. In questo modo, è possibile garantire che tutti coloro che sono coinvolti nel passaggio effettivo verso il passaggio dell'aggiornamento alla fase operativa abbiano un'esperienza semplice e senza problemi.

Sono disponibili due sequenze di lavoro principali:

- **Sequenza di lavoro tecnico** - Rappresenta il processo di esecuzione dell'aggiornamento dei dati. L'azienda impone un limite sulla quantità di inattività consentita. Durante questa inattività, né AX 2012 né Finance and Operations saranno disponibili. La sequenza di lavoro tecnico potrebbe dover ottimizzare la procedura di aggiornamento dei dati per rientrare nel limite di inattività dell'azienda. 
- **Sequenza di lavoro funzionale** - Dopo l'aggiornamento dei dati, è necessario eseguire varie attività di configurazione nell'ambiente Finance and Operations. Tutte queste attività devono essere documentate e quantificate ed è necessario assegnare una risorsa, perché sia la sequenza di lavoro funzionale che la sequenza tecnica devono rispettare il limite di inattività imposto dall'azienda.

Per informazioni dettagliate, vedere 
- [Convalida: test di passaggio](upgrade-cutover-testing.md)
- [Convalida: processo di convalida app](app-validation-process.md)

### <a name="functional-test-pass"></a>Passaggio dei test funzionali
Completare un passaggio di test funzionali di tutti i processi aziendali. Questo passaggio di test sarà un esteso test di tutti i processi aziendali che coinvolgono Finance and Operations. Questi processi aziendali includono i processi precedenti trasferiti da AX 2012 e i processi nuovi che coinvolgono le nuove funzionalità acquisite per la prima volta in Finance and Operations. 

A seconda della qualità del codice, la risoluzione dei problemi e i test potrebbero richiedere numerose iterazioni del passaggio dei test funzionali. Quando si risolve un problema, è necessario testare nuovamente tutti i processi coinvolti per garantire che i processi a monte e a valle non siano influenzati dalla modifica.

Per informazioni dettagliate, vedere [Convalida: test funzionale](upgrade-functional-validation.md).

### <a name="pre-go-live-checklist"></a>Elenco di controllo precedente al passaggio dell'aggiornamento alla fase operativa
Questo elenco di controllo è una procedura consigliata che può ridurre le possibilità di errore durante il passaggio finale della fase operativa. Una settimana prima del passaggio dell'aggiornamento alla fase operativa, interrompere le modifiche alla configurazione in AX 2012 (vale a dire in \<module\>\Setup). Tale restrizione alle modifiche di configurazione è solo procedurale. Gli amministratori di sistema di Microsoft Dynamics AX stabiliscono semplicemente di sospendere a questo punto le modifiche di questo tipo.

Si consiglia inoltre di congelare le modifiche del codice della base di codice di Finance and Operations. Nessun'altra modifica deve essere consentita fino a quando non sia stata valutata e non risulti dannosa al passaggio dell'aggiornamento alla fase operativa.  

Nella fase in cui le modifiche al codice e alla configurazione sono bloccate, è necessario eseguire un'ultima volta l'aggiornamento dei dati prima del passaggio. In questo modo, è possibile assicurarsi che tutto funzioni come previsto. 

Per informazioni dettagliate, vedere [Convalida: preparazione per il passaggio alla fase operativa](upgrade-go-live-prep.md).



### <a name="supported-upgrade-paths"></a>Percorsi di aggiornamento supportati
A giugno 2017 l'aggiornamento a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, versione 0617 è supportato da Microsoft Dynamics AX 2012 R3. Tutti gli aggiornamenti cumulativi (CU) per AX 2012 R3 sono supportati.

Microsoft Dynamics AX 2012 R2 e Microsoft Dynamics AX 2012 RTM al momento non sono supportati. Il supporto sarà aggiunto successivamente nel 2017.

Solo l'aggiornamento alla versione di Finance and Operations distribuita nel cloud è supportato. L'aggiornamento alla versione locale non è supportato. Il supporto per l'aggiornamento alla versione locale sarà aggiunto successivamente nel 2017.


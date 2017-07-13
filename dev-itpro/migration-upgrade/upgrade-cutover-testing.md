---
title: Test di passaggio dell'aggiornamento
description: "In questo argomento viene descritto come testare le attività che si verificano dopo che si disattiva AX 2012 ma prima di attivare Dynamics 365 for Finance and Operations, Enterprise edition."
author: tariqbell
manager: AnnBe
ms.date: 05/29/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Operations, UnifiedOperations, Platform
ms.search.region: Global
ms.author: tabell
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: Platform update 8
ms.translationtype: Human Translation
ms.sourcegitcommit: 6816e3820ab77c71bbf9bde4a068375448331671
ms.openlocfilehash: 711ad5cc3aafacf209704349effb4e08019205ac
ms.contentlocale: it-it
ms.lasthandoff: 06/15/2017

---

# <a name="upgrade-cutover-testing"></a>Test di passaggio dell'aggiornamento

[!include[banner](../includes/banner.md)]

[!include[upgrade banner](../includes/upgrade-banner.md)]

*Passaggio* è il termine che utilizziamo per indicare il processo finale che porta ad avere un nuovo sistema live. Questo processo di passaggio è costituito da attività che vengono eseguite dopo la disattivazione do Microsoft Dynamics AX 2012 ma prima dell'attivazione di Microsoft Dynamics 365 for Finance and Operations, Enterprise edition. Lo scopo dei test di passaggio dell'aggiornamento è di testare nella pratica il processo di passaggio per garantire che tutti gli utenti coinvolti nel passaggio effettivo possano utilizzare la nuova applicazione senza alcun problema.

Sono disponibili due sequenze di lavoro principali durante il passaggio:

- **Sequenza di lavoro tecnico** - Include il processo di esecuzione dell'aggiornamento dei dati. L'azienda impone un limite sulla quantità di inattività consentita. Durante questa inattività, né AX 2012 né Finance and Operations saranno disponibili. Questa sequenza di lavoro potrebbe dover ottimizzare la procedura di aggiornamento dei dati per rientrare nel limite di inattività dell'azienda.
- **Sequenza di lavoro funzionale** - Include le attività di configurazione che vengono eseguite dopo il completamento dell'aggiornamento dei dati. Tutte queste attività devono essere documentate e quantificate ed è necessario assegnare una risorsa, perché sia la sequenza di lavoro funzionale che la sequenza tecnica devono rispettare il limite di inattività imposto dall'azienda.

Nella figura seguente è mostrato il processo complessivo per il passaggio alla fase operativa del passaggio come avrà luogo nell'ambiente di produzione.

![Processo di passaggio](./media/cutover_1.png)

Questo processo differisce da un aggiornamento dei dati di base in un ambiente sandbox nei seguenti modi:

- Il database di AX 2012 non viene copiato ma ne viene semplicemente eseguito il backup, quindi il database originale viene modificato. Questo comportamento è più veloce e il backup consente il rollback, in caso di necessità.
- Poiché l'ambiente di produzione per Finance and Operations ha accesso limitato, le attività che sono state eseguite precedentemente nell'istanza sandbox del server oggetti applicativi (AOS, Application Object Server) vengono ora eseguite dal team di Microsoft DSE. Queste attività includono lo scaricamento e l'importazione del file bacpac e l'esecuzione del pacchetto MajorversionDataUpgrade.zip.
- Abbiamo aggiunto le attività seguenti:

    - Eseguire uno smoke test.
    - Completare le attività di impostazione dell'applicazione. Questo passaggio può essere complesso, a seconda della funzionalità utilizzata. Durante questo passaggio, il team funzionale configura la nuova funzionalità dell'applicazione in modo che sia pronta per essere utilizzata nel sistema aggiornato.
    - Consentire agli utenti di tornare indietro. Notificare alla base di utenti che l'aggiornamento è completato e che possono iniziare a utilizzare il sistema.

## <a name="technical-workstream"></a>Sequenza di lavoro tecnico

La sequenza di lavoro tecnico coinvolge vari membri del team tecnico: l'amministratore del database (DBA), l'amministratore di sistema di AX 2012, gli amministratori dei server e gli sviluppatori che hanno familiarità con AX 2012 e Finance and Operations. Questo argomento spiega quali attività sono assegnate ai singoli ruoli.

Durante il test di passaggio, il team tecnico è concentrato sui testi di affidabilità e di prestazioni del processo di aggiornamento dei dati per assicurare che il processo rispetti il limite di inattività imposto dall'azienda. Questo processo interessa molti elementi hardware e software. Alcuni di questi elementi sono locali, mentre altri si trovano nel cloud Microsoft. Sono inoltre interessati molti elementi del codice dell'applicazione personalizzato e del codice standard. Il risultato di questi test deve essere la fiducia nel processo di passaggio per l'ambiente.

### <a name="turn-off-the-ax-2012-aos-instances"></a>Disattivare le istanze AOS di AX 2012

Questa attività coinvolge l'amministratore di sistema di AX 2012 e gli amministratori dei server.

È necessario convalidare le aree seguenti:

- **Processi batch in esecuzione al momento del passaggio** - Un lungo processo batch che ha già iniziato l'esecuzione eviterà che il sistema si arresti. Pianificare in anticipo, in modo che sia possibile arrestare le istanze AOS al momento desiderato. Potrebbe essere necessario programmare i batch in modo da completarli qualche tempo prima della disattivazione di AX 2012.
- **Sistemi integrati** - È possibile che siano presenti altri sistemi che sono integrati con l'ambiente AX 2012. È necessario considerare questi sistemi nella pianificazione per disattivare AX 2012. Ad esempio, potrebbe essere necessario disattivare i sistemi integrati alcuni minuti prima di disattivare AX 2012, in modo da consentire il completamento di tutte le restanti transazioni in corso. I requisiti per i sistemi integrati variano ampiamente da azienda ad azienda. Pertanto il team di esperti delle singole aziende devono pianificare in base al proprio scenario.

### <a name="create-a-backup-of-the-ax-2012-database"></a>Creare un backup del database AX 2012.

Questa attività coinvolge la distinta base. Il backup verrà utilizzato in caso sia necessario eseguire un rollback. Verrà inoltre utilizzato come punto di riferimento che sarà conservato per un periodo e che mostrerà lo stato del sistema al momento del passaggio.

È necessario convalidare le aree seguenti:

- Ottenere tempistiche concrete per il processo di backup.
- Regolare le opzioni di backup utilizzate (ad esempio l'utilizzo o meno della compressione), per garantire che il backup venga svolto nel modo più rapido possibile.

### <a name="export-the-database-to-bacpac"></a>Esportare il database in bacpac

Questa attività coinvolge la distinta base. L'output di questa attività è il file di esportazione che verrà caricato in Microsoft Azure per il nuovo sistema.

È necessario convalidare le aree seguenti:

- Ottenere tempistiche concrete per il processo di backup.
- Ottimizzare il processo di esportazione per garantire l'esperienza più veloce possibile. L'ottimizzazione può richiedere le attività seguenti:

    - Misurare le risorse di sistema durante l'esportazione, ad esempio la CPU, l'I/O del disco e la memoria.
    - Se vengono rilevati colli di bottiglia nell'utilizzo delle risorse, creare un piano per attenuarli. In genere, i colli di bottiglia vengono mitigati assegnando una maggiore quantità della risorsa richiesta.

### <a name="upload-the-bacpac-file-to-azure-storage"></a>Caricare il file bacpac in Archiviazione di Azure

Questa attività coinvolge la distinta base o gli amministratori dei server. Durante questa attività, il file bacpac viene trasferito in Azure.

È necessario convalidare le aree seguenti:

- Selezionare il computer che verrà utilizzato per il caricamento e assicurarsi che lo strumento di esplorazione di Archiviazione di Azure sia configurato e pronto per l'utilizzo.
- Ottenere tempistiche concrete per il processo di caricamento misurandolo più volte. I tempi di caricamento varieranno in base alla velocità della connessione Internet e alla posizione geografica del data center di Azure rispetto alla posizione dell'azienda.

### <a name="download-and-import-the-bacpac-file-to-the-azure-sql-database"></a>Scaricare e importare il file bacpac nel database SQL di Azure

Quando questa attività viene eseguita nel passaggio alla fase operativa, viene eseguita dal team di Microsoft DSE. Tuttavia, durante i test di passaggio, include la distinta base. L'esito di questa attività è il file di esportazione che verrà caricato in Azure per il nuovo sistema.

È necessario convalidare le aree seguenti:

- Ottenere tempistiche concrete per il processo di importazione.
- Ottimizzare il processo di esportazione per garantire l'esperienza più veloce possibile. L'ottimizzazione può richiedere le attività seguenti:

    - Misurare le risorse di sistema durante l'esportazione. Di seguito sono riportati alcuni esempi.

        - **Nel computer AOS:** CPU, I/O del disco e memoria
        - **Nell'istanza del database SQL di Azure:** velocità effettiva del database SQL (DTU). È possibile monitorare la DTU SQL di Azure da Microsoft SQL Server Management Studio nel computer AOS guardando la vista di sistema sys.dm_resource_stats.

    - Se vengono rilevati colli di bottiglia nell'utilizzo delle risorse, creare un piano per attenuarli. In genere, i colli di bottiglia vengono mitigati assegnando una maggiore quantità della risorsa richiesta. Poiché questo computer è ospitato da Microsoft, è necessario inoltrare una richiesta a Microsoft per incrementare le risorse che causano un collo di bottiglia.

### <a name="run-the-majorversiondataupgradezip-package"></a>Eseguire il pacchetto MajorVersiondataUpgrade.zip

Quando questa attività viene eseguita nel passaggio alla fase operativa, viene eseguita dal team di Microsoft DSE. Tuttavia, durante i test di passaggio, coinvolge gli sviluppatori. Durante questa attività, la struttura del database precedente viene trasformata nella struttura del nuovo sistema.

Il processo di sincronizzazione del database viene eseguito come parte di questa attività. La sincronizzazione del database potrebbe richiedere una significativa quantità di tempo in alcune situazioni, ad esempio quando un indice con cluster viene modificato in una tabella, perché questa operazione è costosa in SQL.

Si consiglia pertanto di eseguire prima il processo di analisi e di debug in un ambiente di sviluppo. In una ambiente sandbox, le opzioni di debug e di analisi sono più limitate. Lo scopo è di avere pochi problemi, o di non averne affatto, da risolvere quando di eseguono i test di passaggio.

È necessario convalidare le aree seguenti:

- Ottenere tempistiche concrete per il processo di importazione.
- Ottimizzare il processo per garantire l'esperienza più veloce possibile. L'ottimizzazione può richiedere le attività seguenti:

    - Monitorare le prestazioni di singoli script di aggiornamento attraverso la tabella ReleaseUpdateScriptsExecution.
    - Regolare gli script per ottimizzare le prestazioni. Questa attività può richiedere che si personalizzi il codice X++ di uno script in modo da ottimizzarlo per il set di dati.
    - Monitorare la DTU SQL di Azure utilizzando il monitoraggio di Microsoft Dynamics Lifecycle Services (LCS) o la vista di sistema sys.dm_resources_stats in Management Studio. Se le risorse sono al limite massimo, potrebbe essere necessario richiedere un livello più elevato del database al team di Microsoft DSE.

### <a name="roll-back-to-ax-2012"></a>Eseguire il rollback ad AX 2012

Lo scopo di questa attività è di ripristinare il database utilizzando il backup effettuato quando AX 2012 è stato disattivato e quindi attivare nuovamente AX 2012. Anche lo stato dei sistemi integrati può essere ripristinato. Tuttavia, poiché i sistemi integrati variano da azienda ad azienda, è necessario pianificare lo scenario in base alle condizioni specifiche. Sebbene il ricorso al rollback sia improbabile, è molto importante che il processo sia stato testato nel caso che sia necessario.

## <a name="functional-workstream"></a>Sequenza di lavoro funzionale

Dopo l'aggiornamento dei dati, è necessario eseguire diverse attività di configurazione nel nuovo ambiente. Lo scopo di questa sequenza di lavoro è di documentare e quantificare tutte le attività di configurazione e di assegnare una risorsa a ogni attività per garantire che queste attività vengano eseguite insieme alla sequenza di lavoro tecnica durante il periodo di inattività.

In genere, le attività funzionali includono la modifica dei valori di specifici parametri di sistema o altri dati di configurazione. Queste attività vengono identificate tramite il passaggio dei test funzionali completi, che rappresenta un'attività separata dai test di passaggio. Quando un'attività di questo tipo viene identificata, deve essere esaminata insieme alla risorsa funzionale e allo sviluppatore.

Modifiche più importanti potrebbero richiedere la scrittura di un nuovo script di aggiornamento dei dati personalizzato per aggiornare i dati durante il processo di aggiornamento dei dati. La risorsa funzionale può comunque eseguire manualmente modifiche più piccole nel nuovo sistema dopo l'aggiornamento dei dati.

Le modifiche più grandi che richiedono nuovi script di aggiornamento dei dati devono essere sottoposte ai test. Di conseguenza, sarà necessario eseguire una o più iterazioni aggiuntive del pacchetto MajorVersionDataUpgrade.zip. È importante soppesare il costo di eseguire nuovamente il pacchetto rispetto al costo dell'immissione manuale dei dati.

Per ogni modifica manuale, è necessario aggiungere un'attività al documento del piano di passaggio. Questa attività deve visualizzare i seguenti dettagli:

-   Qual è l'attività e cosa si deve fare?
-   Chi deve eseguirla?
-   Quanto tempo richiede?


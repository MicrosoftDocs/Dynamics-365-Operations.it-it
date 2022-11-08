---
title: Domande frequenti sulla migrazione dei clienti di Human Resources
description: Questo articolo fornisce le risposte alle domande frequenti sulla migrazione di Microsoft Dynamics 365 Human Resources all'infrastruttura unita di finanza e operazioni.
author: twheeloc
ms.date: 07/06/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0e11d26ebe084762a8616c8aa0aa041a87306473
ms.sourcegitcommit: e25fe4228add88dd37f4f38ece86979e1c621f6a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2022
ms.locfileid: "9734360"
---
# <a name="human-resources-customer-migration"></a>Migrazione dei clienti di Human Resources

## <a name="how-should-dynamics-365-human-resources-customers-plan-to-move-to-the-finance-and-operations-infrastructure"></a>In che modo i clienti di Dynamics 365 Human Resources prevedono di spostare l'infrastruttura di finanza e operazioni?

Due categorie di clienti Microsoft Dynamics 365 Human Resources saranno interessati e dovranno apportare modifiche per assicurarsi di disporre dell'infrastruttura di finanza e operazioni più aggiornata:

- Clienti che usano Dynamics 365 Human Resources e non hanno altre app di operazioni da Dynamics 365
- Clienti che usano Dynamics 365 Human Resources e Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce o Dynamics 365 Project Operations

Indipendentemente dalla categoria cui appartengono, i clienti dovranno spostare i dati in un ambiente di nuova creazione nell'infrastruttura di finanza e operazioni per poi convalidare la corretta esecuzione dell'unione.

In futuro, l'app Dynamics 365 Human Resources avrà un proprio ambiente di finanza e operazioni separato rispetto alle altre app di operazioni. In questo modo, i clienti potranno sfruttare le opzioni di estendibilità senza dover unire i dati correnti. Microsoft fornirà gli strumenti e un ambiente sandbox che i clienti potranno usare per testare e convalidare la migrazione dei dati prima di passare a un ambiente di produzione. Gli strumenti permetteranno un'elaborazione pressoché totalmente automatizzata e saranno disponibili tra agosto e novembre 2022.

I clienti che usano altre app nell'infrastruttura di finanza e operazioni avranno l'opzione di unire i loro dati Human Resources con un ambiente esistente. 

## <a name="when-will-customers-be-moved-to-the-finance-and-operations-infrastructure"></a>Quando verranno spostati i clienti all'infrastruttura di finanza e operazioni?

La transizione per ogni società dipenderà dalla sua configurazione attuale e dalla predisposizione a passare alla nuova infrastruttura di finanza e operazioni. Consigliamo ai clienti di collaborare con il proprio partner Microsoft per determinare il percorso migliore.

- Le organizzazioni che usano il modulo **Human Resources** in Dynamics 365 Finance potranno abilitare le nuove funzionalità da Dynamics 365 Human Resources come parte del regolare processo di aggiornamento One Version. Le nuove funzionalità sono pianificate per diventare generalmente disponibili a partire da gennaio 2022.
- Le organizzazioni che usano Dynamics 365 Human Resources avranno accesso agli strumenti necessari per completare l'unione dell'infrastruttura. Microsoft collaborerà con i clienti alla transizione, per evitare possibili interruzioni del servizio. I clienti avranno 12 mesi per portare a termine la transizione, a partire dal momento in cui gli strumenti di migrazione saranno resi disponibili.
- Le organizzazioni che usano sia Dynamics 365 Human Resources che il modulo **Human Resources** possono spostare la propria infrastruttura Human Resources autonoma nell'infrastruttura di finanza e operazioni. Un'altra opzione consiste nell'uso degli strumenti di unione per creare un unico ambiente. Non sono previsti requisiti o tempistiche per l'unione dei due ambienti.

Per informazioni aggiornate, consultare regolarmente i [piani di rilascio](/dynamics365/release-plans/).

## <a name="will-customers-still-need-custom-integrations-between-dynamics-365-human-resources-and-the-human-resources-module"></a>I clienti avranno ancora bisogno di integrazioni personalizzate tra Dynamics 365 Human Resources e il modulo Human Resources?

- I clienti che usano sia Dynamics 365 Human Resources che altri ambienti di infrastruttura di finanza e operazioni attualmente integrati dovranno continuare a integrare i due ambienti dopo l'unione.
- I clienti che scelgono di mantenere il proprio ambiente Dynamics 365 Human Resources separato dall'ambiente delle app per la finanza e le operazioni dovranno continuare a integrare gli ambienti per rendere disponibile i dati in entrambi gli ambienti.
- I clienti possono continuare a usare lo strumento di integrazione dei dati per copiare i dati tra i due ambienti. i clienti che uniscono i dati in un unico ambiente dopo la migrazione non dovranno più integrare i dati, perché tutti i dati saranno in un database singolo.

## <a name="will-customer-isv-solutions-automatically-be-migrated"></a>Le soluzioni ISV verranno migrate automaticamente?

L'esperienza di migrazione per ogni soluzione di fornitore di software indipendente (ISV) varierà a seconda del metodo di integrazione della soluzione. Microsoft lavorerà a stretto contatto con gli ISV per garantire una transizione agevolata alla nuova infrastruttura di finanza e operazioni. Molte soluzioni ISV sono create su Dataverse mediante le funzionalità di Microsoft Power Platform. Queste soluzioni dipendono dall'integrazione di Dataverse tra l'ambiente Dynamics 365 Human Resources e l'ambiente Dataverse. L'integrazione di Dataverse verrà deprecata nell'ambito dell'unione dell'infrastruttura. Nell'infrastruttura di finanza e operazioni, sono previste nuove mappe di doppia scrittura per sostituire la funzionalità di integrazione di Dataverse.

## <a name="how-will-the-data-integrator-that-moves-data-between-dynamics-365-human-resources-and-other-dynamics-365-apps-be-affected"></a>In che modo sarà interessato lo strumento di integrazione dei dati che sposta i dati tra Dynamics 365 Human Resources e altre app Dynamics 365?

Una volta passati all'infrastruttura di finanza e operazioni, i clienti dovranno continuare a integrare i dati tra i due ambienti. I clienti possono continuare a usare lo strumento di integrazione dei dati per eseguire le attività di migrazione dei dati. I clienti che prevedono di mantenere il proprio ambiente Dynamics 365 Human Resources separato dall'ambiente delle app per la finanza e le operazioni dovranno continuare a integrare gli ambienti per rendere disponibile i dati in entrambi gli ambienti. Per i clienti che uniscono i due ambienti in un unico ambiente, l'integrazione tra i due ambienti non sarà più richiesta.

## <a name="how-will-data-be-moved-between-dynamics-365-human-resources-on-the-finance-and-operations-infrastructure-and-dataverse-after-the-migration"></a>In che modo verranno spostati i dati tra Dynamics 365 Human Resources nell'infrastruttura di finanza e operazioni e Dataverse dopo la migrazione?

L'integrazione corrente di Dataverse tra Dynamics 365 Human Resources e Dataverse verrà deprecata nell'ambito dell'infrastruttura di finanza e operazioni. È prevista l'introduzione di mappe di doppia scrittura per associare le entità di finanza e operazioni alle tabelle di Dataverse. I clienti dovranno decidere quali mappe di doppia scrittura sono necessarie per la loro implementazione. Si consiglia di usare le tabelle virtuali per le integrazioni e le soluzioni ISV, a meno che non vi sia un'esigenza aziendale specifica per la duplicazione dei dati in Dataverse ai fini dell'esecuzione della logica di business.

## <a name="how-does-the-migration-affect-dataverse-extensions-for-dynamics-365-human-resources"></a>In che modo la migrazione interesserà le estensioni Dataverse per Dynamics 365 Human Resources?

Ai clienti verrà richiesto di eseguire la migrazione in un ambiente sandbox prima della migrazione all'ambiente di produzione. Quando i clienti migrano il proprio ambiente sandbox, dovranno creare una copia dell'ambiente Dataverse per la connessione al nuovo ambiente di finanza e operazioni migrato. È consigliabile che un cliente copi sia i dati che le soluzioni per l'ambiente, in modo che questo corrisponda in tutto e per tutto all'ambiente di produzione.

Quando i clienti sono pronti a migrare il proprio ambiente di produzione Dynamics 365 Human Resources, Microsoft migrerà automaticamente il database e Archiviazione BLOB di Azure. Il database e l'archiviazione migrati punteranno al nuovo ambiente nell'infrastruttura di finanza e operazioni allo stesso ambiente di produzione Dataverse. Prima di poter continuare a copiare i dati in Dataverse, i clienti dovranno abilitare eventuali mappe di doppia scrittura necessarie per le proprie integrazioni, estensioni e soluzioni ISV create su Dataverse.

## <a name="will-microsoft-power-platform-components-that-were-built-for-dynamics-365-human-resources-automatically-work-after-the-infrastructure-migration-is-completed"></a>I componenti Microsoft Power Platform creati per Dynamics 365 Human Resources funzioneranno automaticamente una volta completata la migrazione dell'infrastruttura?

Le app create in Power Apps, i flussi creati in Power Automate e altre personalizzazioni Microsoft Power Platform sono assimilabili a estensioni di Dataverse. Durante la migrazione degli ambienti di produzione del cliente, non ci sarà alcun impatto sugli ambienti Dataverse, incluse eventuali estensioni. Le app, i flussi e altre personalizzazioni Power Microsoft Platform dovrebbero continuare a funzionare senza richiedere un'ulteriore configurazione.

## <a name="what-will-happen-to-dataverse-virtual-table-entities-for-dynamics-365-human-resources-during-the-migration"></a>Cosa accadrà alle entità tabelle virtuali di Dataverse per Dynamics 365 Human Resources durante la migrazione?

Quando i clienti migrano il proprio ambiente Dynamics 365 Human Resources all'infrastruttura di finanza e operazioni, l'ambiente resterà connesso all'ambiente Dataverse attualmente connesso a Dynamics 365 Human Resources. Le tabelle virtuali di Dataverse generate nell'ambiente continueranno a funzionare senza richiedere ulteriori configurazioni. Le tabelle virtuali potrebbero dover essere rigenerate nell'ambiente Dataverse connesso a un ambiente di finanza e operazioni esistente del cliente.

## <a name="how-will-an-integration-that-uses-the-applicant-tracking-system-ats-api-payroll-api-dataverse-virtual-tables-for-dynamics-365-human-resources-or-other-entities-in-the-dataverse-web-api-work-after-the-infrastructure-merge-is-completed"></a>In che modo funzionerà un'integrazione che usa API Applicant Tracking System (ATS), API per le retribuzioni, tabelle virtuali di Dataverse per Dynamics 365 Human Resources o altre entità nell'API Web di Dataverse una volta completata l'unione dell'infrastruttura?

Quando i clienti migrano il proprio ambiente Dynamics 365 Human Resources all'infrastruttura di finanza e operazioni, l'ambiente resterà connesso all'ambiente Dataverse attualmente connesso a Dynamics 365 Human Resources. Eventuali integrazioni sviluppate per l'API Web di Dataverse continueranno a funzionare dopo il completamento della migrazione.

## <a name="our-organization-has-configured-custom-security-in-dynamics-365-human-resources-will-it-still-be-applied-after-the-infrastructure-migration-is-completed"></a>La nostra organizzazione ha configurato la sicurezza personalizzata in Dynamics 365 Human Resources. Verrà ancora applicata dopo il completamento della migrazione dell'infrastruttura?

Sì, le configurazioni di sicurezza personalizzata saranno incluse nella migrazione dei dati.

## <a name="will-workflows-in-dynamics-365-human-resources-automatically-be-migrated"></a>I flussi di lavoro in Dynamics 365 Human Resources verranno migrati automaticamente?

Sì, le configurazioni del flusso di lavoro, la cronologia del flusso di lavoro e gli attuali flussi di lavoro in uso verranno migrati nell'infrastruttura unita.

## <a name="will-saved-views-in-dynamics-365-human-resources-automatically-be-migrated"></a>Le visualizzazioni salvate in Dynamics 365 Human Resources verranno migrate automaticamente?

Sì, le visualizzazioni salvate verranno migrate nell'infrastruttura unita.

## <a name="will-features-that-are-enabled-in-dynamics-365-human-resources-automatically-be-available-after-the-infrastructure-merge"></a>Le funzionalità abilitate in Dynamics 365 Human Resources saranno automaticamente disponibili nell'unione dell'infrastruttura?

- Per i clienti che usano il modulo **Human Resources**, le funzionalità disponibili solo in Dynamics 365 Human Resources verranno gestite tramite Gestione delle funzionalità. In genere, queste funzionalità non verranno abilitate per impostazione predefinita. Tutte le funzionalità che devono essere abilitate per impostazione predefinita verranno documentate.
- Per i clienti che usano Dynamics 365 Human Resources, le funzionalità saranno disponibili nell'infrastruttura. Le funzionalità non disponibili verranno documentate. Ogni chiave di Gestione funzionalità abilitata nell'ambiente Dynamics 365 Human Resources corrente verrà abilitata nell'infrastruttura unita. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](/fin-ops/get-started/feature-management-overview.md).

## <a name="what-happens-to-byod-databases-during-the-migration"></a>Cosa accade ai database BYOD durante la migrazione?

Le configurazioni di importazione ed esportazione per il database BYOD verranno migrate nella nuova infrastruttura di finanza e operazioni.

## <a name="is-there-an-impact-on-the-azure-region-when-the-customer-environment-is-migrated"></a>La migrazione dell'ambiente del cliente ha impatto sull'area di Azure?

L'ambiente Dynamics 365 Human Resources resterà nella stessa area di Azure per la migrazione. Se è previsto un requisito per spostare un ambiente in una diversa area di Azure, i clienti dovranno attenersi ai passaggi standard per eseguire la migrazione in una nuova area dopo il completamento della migrazione.

## <a name="what-happens-to-azure-data-lakes-during-the-migration"></a>Cosa accade agli Azure Data Lake durante la migrazione?

Qualsiasi esportazione attualmente configurata per Azure Data Lake nelle app per la finanza e le operazioni manterrà la stessa configurazione dopo la migrazione.

> [!NOTE]
> Le mappe di doppia scrittura dovranno essere abilitate per continuare a scrivere i dati dall'ambiente Human Resources in Dataverse.

I clienti che desiderano esportare i dati Human Resources nel data lake possono abilitare questa funzionalità dopo il completamento della migrazione all'infrastruttura di finanza e operazioni. Per altre informazioni, vedere [Data lake - Centro architetture di Azure](/azure/architecture/data-guide/scenarios/data-lake).

I clienti possono collegare più ambienti di finanza e operazioni allo stesso data lake. Tuttavia, ogni cliente punterà a una cartella e a un contenitore diversi. I clienti che prevedono di unire gli ambienti in un successivo momento dovranno pianificare attentamente il loro approccio.
 
## <a name="what-migration-will-be-required-if-a-customer-is-currently-using-the-human-resources-module"></a>Quale migrazione sarà necessaria per i clienti che attualmente usano il modulo Human Resources?

Per i clienti che usano il modulo **Human Resources**, la nuova funzionalità verrà applicata da Dynamics 365 Human Resources al proprio ambiente tramite il processo di aggiornamento One Version standard. I clienti potranno vedere la nuova funzionalità nel proprio ambiente dal momento che questa diventa disponibile in ogni aggiornamento. I clienti possono usare Gestione delle funzionalità per abilitare le funzionalità. I clienti devono pianificare la convalida di queste nuove funzionalità usando i processi già in uso e provvedere alla convalida di altri aggiornamenti nel proprio ambiente.

## <a name="what-will-happen-to-custom-integrations-to-external-systems"></a>Cosa accadrà alle integrazioni personalizzate ai sistemi esterni?

I clienti dovranno migrare le proprie integrazioni all'ambiente di finanza e operazioni. Poiché l'endpoint di questo ambiente è diverso, i clienti potrebbero dover aggiornare o modificare le integrazioni in modo che puntino al nuovo ambiente. Questa attività è un processo essenzialmente manuale, e le modifiche richieste dipenderanno dall'architettura dell'integrazione. I clienti dovranno collaborare con il proprio partner Microsoft per determinare l'approccio migliore per spostare le integrazioni.

## <a name="what-will-happen-to-microsoft-power-platform-dataverse-extensions-if-customers-merge-a-dynamics-365-human-resources-environment-with-an-existing-finance-and-operations-environment"></a>Cosa accadrà alle estensioni di Microsoft Power Platform (Dataverse) se un cliente unisce un ambiente Dynamics 365 Human Resources con un ambiente di finanza e operazioni esistente?

Se i clienti decidono di unire un ambiente Dynamics 365 Human Resources e un ambiente di finanza e operazioni esistente in un'unica istanza di Dataverse dopo la migrazione, i loro ambienti Dataverse devono essere combinati nell'ambito del processo di unione. Questa attività richiederà che qualsiasi app creata mediante Power Apps e altre eventuali personalizzazioni vengano ridistribuite nel nuovo ambiente.

## <a name="what-will-happen-to-documents-during-the-migration"></a>Cosa accadrà ai documenti durante la migrazione?

Quando i clienti migrano il proprio ambiente Dynamics 365 Human Resources all'infrastruttura di finanza e operazioni, i documenti rimarranno nell'archivio dei documenti esistente e verranno automaticamente mappati al nuovo ambiente nell'infrastruttura di finanza e operazioni.

In una versione futura, verranno fornite nuove entità di dati. Dopo aver apportato questa modifica, i clienti che scelgono di unire il proprio ambiente Dynamics 365 Human Resources a un ambiente di finanza e operazioni esistente potranno quindi esportare i documenti e spostarli nell'ambiente esistente.

## <a name="after-the-migration-what-happens-to-the-batch-jobs-that-were-configured-in-dynamics-365-human-resources"></a>Dopo la migrazione, cosa accade ai processi batch precedentemente configurati in Dynamics 365 Human Resources?

I processi batch dovranno essere riconfigurati nell'ambiente di finanza e operazioni. I clienti dovranno valutare ogni processo batch e confrontarlo all'elenco corrente di processi batch nell'ambiente di finanza e operazioni. I clienti dovranno inoltre analizzare la programmazione batch complessiva quando uniscono due set di processi batch, per determinare se occorre apportare delle modifiche alla programmazione batch, alle priorità o ai gruppi di batch.

## <a name="how-will-the-migration-affect-the-lcs-project-for-dynamics-365-human-resources"></a>In che modo la migrazione inciderà sul progetto LCS per Dynamics 365 Human Resources?

Ai clienti verrà richiesto di creare un nuovo progetto Microsoft Dynamics Lifecycle Service (LCS) e dovranno selezionare le app per la finanza e le operazioni come prodotto e **Implementazione** come tipo di progetto. Inoltre, sarà disponibile un nuovo campo per il tipo di progetto secondario quando viene creato un progetto LCS. I clienti dovranno selezionare l'opzione per la migrazione di Dynamics 365 Human Resources per migrare un progetto LCS di Human Resources esistente nell'infrastruttura di finanza e operazioni.

Le funzionalità dei progetti LCS di finanza e operazioni sono diverse rispetto alle funzionalità dei progetti LCS di Human Resources.

Ai fini dell'attivazione, i nuovi clienti dovranno completare le seguenti attività:

- Completare l'onboarding del progetto.
- Completare la metodologia.
- Compilare una stima di abbonamento.
- Completare il processo di predisposizione per l'attivazione.

## <a name="how-will-the-business-process-modeler-be-migrated"></a>In che modo verrà migrato il modellatore di processi aziendali?

Ai clienti verrà richiesto di esportare la propria libreria di modellatori di processi aziendali dal progetto LCS di Human Resources e di importarla nel progetto LCS di finanza e operazioni. Inoltre, i clienti dovranno aggiornare le impostazioni della Guida nell'applicazione in modo che puntino al nuovo progetto LCS.

## <a name="how-will-the-service-update-process-be-affected-by-the-migration"></a>In che modo la migrazione influirà sul processo di aggiornamento del servizio?

Dopo la migrazione, i clienti avranno molta più flessibilità in termini di gestione del ciclo di vita delle applicazioni (ALM) e aggiornamenti del servizio. Gli aggiornamenti del servizio non verranno più applicati automaticamente agli ambienti Human Resources. Il servizio seguirà invece i processi e le funzionalità di aggiornamento del servizio di One Version e verranno abilitate le opzioni di configurazione per gli aggiornamenti tramite LCS.

## <a name="will-customers-be-eligible-for-fasttrack-assistance-with-the-infrastructure-merge"></a>I clienti saranno idonei per l'assistenza FastTrack con l'unione dell'infrastruttura?

Microsoft sta ancora definendo quali strumenti e risorse saranno disponibili da FastTrack per semplificare l'unione.

## <a name="licensing-impact"></a>Impatto sulle licenze

Per ulteriori informazioni su come ciò interesserà le licenze, vedere [Unione dell'infrastruttura Dynamics 365 Human Resources](hr-infrastructure-merge.md#licensing).

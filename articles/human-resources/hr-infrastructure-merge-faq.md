---
title: Domande frequenti sull'unione dell'infrastruttura Dynamics 365 Human Resources
description: Questo argomento fornisce le risposte alle domande frequenti sull'unione dell'infrastruttura per Microsoft Dynamics 365 Human Resources e le app Finance and Operations.
author: rachel-profitt
ms.date: 07/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 537917e9a987d701a0c96dfb7592e124e09bb748e4f2f52d39f8d97000c70ae3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6712003"
---
# <a name="dynamics-365-human-resources-infrastructure-merge-faq"></a>Domande frequenti sull'unione dell'infrastruttura Dynamics 365 Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo argomento fornisce le risposte alle domande frequenti sull'unione dell'infrastruttura per Microsoft Dynamics 365 Human Resources e le app Finance and Operations.

## <a name="what-is-the-dynamics-365-human-resources-infrastructure-merge"></a>Qual è l'unione dell'infrastruttura di Dynamics 365 Human Resources?

Dynamics 365 Human Resources è un'applicazione autonoma che utilizza un'infrastruttura diversa da altre app Finance and Operations, come Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce, e Dynamics 365 Project Operations. L'unione dell'infrastruttura porterà Dynamics 365 Human Resources nella stessa infrastruttura di altre app Finance and Operations.

## <a name="value-and-benefits-of-the-infrastructure-merge"></a>Valore e vantaggi dell'unione dell'infrastruttura

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-its-hr-operations-what-benefits-will-we-see-from-these-changes"></a>La mia organizzazione utilizza Dynamics 365 Human Resources per gestire le operazioni HR. Quali vantaggi vedremo da questi cambiamenti?

- Queste modifiche eliminano più set di funzionalità delle risorse umane (HR) in Dynamics 365.
- Forniscono l'estendibilità di Microsoft Power Platform e un modo per estendere le opzioni di logica aziendale e funzionalità.
- Portano coerenza tra Dynamics 365 Human Resources e altre app Finance and Operations in termini di Application Lifecycle Management (ALM), Microsoft Dynamics Lifecycle Services (LCS), disponibilità geografica, estendibilità e altro ancora.
- Consentono di utilizzare i servizi e gli strumenti condivisi e aiutano a ridurre i costi.

### <a name="my-organization-uses-dynamics-365-human-resources-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-what-benefits-will-we-see-from-these-changes"></a>La mia organizzazione utilizza Dynamics 365 Human Resources in Dynamics 365 Finance, Supply Chain Management, Commerce, o Project Operations. Quali vantaggi vedremo da questi cambiamenti?

Le capacità e gli investimenti che sono stati fatti in Dynamics 365 Human Resources saranno ora disponibili per i clienti che utilizzano il modulo HR in Dynamics 365 Finance. Alcune di queste funzionalità includono la gestione di congedi e assenze, la gestione dei benefit e la gestione delle attività.

### <a name="will-i-lose-any-features-or-capabilities-that-i-currently-use"></a>Perderò le funzioni o le capacità che utilizzo attualmente?

Ci sarà parità funzionale tra Dynamics 365 Human Resources e il modulo HR nelle app Finance and Operations. Dynamics 365 Human Resources è prioritario per le funzionalità simili. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="will-the-experience-change-for-my-users"></a>L'esperienza cambierà per i miei utenti?

Le nuove funzionalità HR saranno gestite tramite la gestione delle funzionalità. I clienti decideranno se vogliono accettarli. In alcuni casi, le funzionalità potrebbero essere modificate. In questi casi verrà fornita la documentazione.

### <a name="how-does-this-change-affect-me-if-i-am-an-existing-customer-and-i-use-both-the-hr-module-on-the-finance-and-operations-infrastructure-and-dynamics-365-human-resources-through-custom-integrations"></a>In che modo questo cambiamento mi influenza se sono un cliente esistente e utilizzo il modulo HR sull'infrastrutture Finance and Operations e Dynamics 365 Human Resources tramite integrazioni personalizzate?

Le integrazioni personalizzate tra Dynamics 365 Human Resources e il modulo HR in Dynamics 365 Finance non saranno più richieste. Tutti i dati HR risiederanno nello stesso database delle altre app Finance and Operations.

## <a name="migration-from-dynamics-365-human-resources-to-finance-and-operations-apps"></a>Migrazione da Dynamics 365 Human Resources alle app Finance and Operations

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-hr-operations-what-do-we-have-to-plan-for-to-migrate-to-the-new-experience"></a>La mia organizzazione utilizza Dynamics 365 Human Resources per gestire le operazioni HR. Cosa dobbiamo pianificare per eseguire la migrazione alla nuova esperienza?

Se l'organizzazione utilizza Dynamics 365 Human Resources ma non usa le app Finance and Operations, il tuo ambiente Human Resources verrà migrato alla nuova infrastruttura. Gran parte di questo processo di migrazione sarà automatizzato. Saranno attivati i processi per migrare il database e sincronizzarlo con la nuova infrastruttura.

Inoltre, saranno disponibili gli strumenti in modo da poter testare il processo di migrazione e convalidare i dati e l'esperienza prima di eseguire la migrazione dell'ambiente di produzione.

Se l'organizzazione utilizza Dynamics 365 Human Resources e le app Finance and Operations dovresti pianificare più tempo per la convalida per assicurarti che i tuoi dati vengano migrati correttamente nel nuovo ambiente. La migrazione alla nuova infrastruttura unirà i dati del tuo ambiente Human Resources con il tuo ambiente Finance and Operations . Saranno utilizzati gli strumenti per automatizzare il più possibile il processo di unione dei dati. Tuttavia, le istanze di dati in conflitto richiederanno l'input dell'utente per definire come risolvere il conflitto. Gli utenti e gli amministratori dovranno gestire i mapping dei dati in caso di conflitti e testare la migrazione in ambienti sandbox prima di eseguire la migrazione dell'ambiente di produzione.

### <a name="my-organization-uses-dynamics-365-human-resources-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-what-do-we-have-to-plan-for-to-migrate-to-the-new-experience"></a>La mia organizzazione utilizza Dynamics 365 Human Resources in Dynamics 365 Finance, Supply Chain Management, Commerce, o Project Operations. Cosa dobbiamo pianificare per eseguire la migrazione alla nuova esperienza?

Per le organizzazioni che utilizzano il modulo HR nelle app Finance and Operations, la nuova funzionalità di Dynamics 365 Human Resources verrà applicata all'ambiente tramite il processo di aggiornamento One Version standard. Potrai vedere la nuova funzionalità nel tuo ambiente non appena diventa disponibile in ogni aggiornamento. Puoi utilizzare Gestione funzionalità per attivare le nuove funzionalità. Tuttavia, dovresti pianificare la convalida di tali funzionalità. Segui i processi in atto per convalidare altri aggiornamenti del tuo ambiente. Per ulteriori informazioni su come vengono applicati gli aggiornamenti alle app Finance and Operations, vedi [Panoramica di One Version](../fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview.md).

### <a name="when-will-my-organization-be-migrated"></a>Quando verrà eseguita la migrazione della mia organizzazione?

La migrazione di ogni organizzazione dipenderà dalla sua configurazione attuale e dalla preparazione a migrare alla nuova infrastruttura. Queste date sono soggette a modifiche.

- Le organizzazioni che attualmente utilizzano il modulo HR nelle app Finance and Operations riceveranno la funzionalità HR per Dynamics 365 Human Resources come parte del normale processo di aggiornamento One Version. Le nuove funzionalità dovrebbero diventare generalmente disponibili a partire da ottobre 2021.
- Le organizzazioni che attualmente utilizzano solo Dynamics 365 Human Resources avranno accesso agli strumenti di migrazione in modo che possano iniziare i test e avviare la migrazione a partire dalla metà del 2022. La data entro la quale deve essere completata la migrazione alla nuova infrastruttura non è stata ancora stabilita. Tuttavia, sarà trascorso almeno un anno dalla data in cui gli strumenti di migrazione saranno disponibili.
- Le organizzazioni che attualmente utilizzano Dynamics 365 Human Resources e altre app Finance and Operations avranno accesso agli strumenti di migrazione in modo che possano iniziare i test e avviare la migrazione a partire dalla fine del 2022. La data entro la quale deve essere completata la migrazione alla nuova infrastruttura non è stata ancora stabilita. Tuttavia, sarà trascorso almeno un anno dalla data in cui gli strumenti di migrazione saranno disponibili.

Per ulteriori informazioni sulle nuove funzionalità di Dynamics 365 Human Resources, vedi [Novità o modifiche in Human Resources](./hr-admin-whats-new.md).

### <a name="i-am-using-new-capabilities-that-are-available-only-in-dynamics-365-human-resources-such-as-leave-and-absence-and-benefits-management-will-these-capabilities-now-be-available-in-the-human-resources-module-on-the-finance-and-operations-infrastructure-too"></a>Sto utilizzando nuove funzionalità disponibili solo in Dynamics 365 Human Resources (ad esempio **Congedi e assenze** e **Gestione benefit**). Queste funzionalità saranno ora disponibili anche nel modulo Human Resources dell'infrastruttura Finance and Operations?

Sì, tutti i moduli di Dynamics 365 Human Resources funzioneranno così come sono nelle app Finance and Operations con una parità di funzionalità del 100%. Come parte della strategia di migrazione complessiva per i clienti che attualmente utilizzano queste funzionalità in HR, i dati dei clienti verranno migrati in modo che continuino a funzionare nell'infrastruttura Finance and Operations.

### <a name="i-use-the-new-dynamics-365-human-resources-benefits-management-capabilities-ive-built-custom-integrations-with-the-hr-module-on-the-finance-and-operations-infrastructure-so-that-i-can-take-advantage-of-the-payroll-capabilities-by-using-benefits-data-will-these-custom-integrations-be-required-going-forward"></a>Uso le nuove funzionalità di gestione dei benefit di Dynamics 365 Human Resources. Ho creato integrazioni personalizzate con il modulo HR nell'infrastruttura Finance and Operations in modo da poter utilizzare le capacità di gestione degli stipendi utilizzando i dati dei benefit. Queste integrazioni personalizzate saranno necessarie in futuro?

Come parte dell'unione dell'infrastruttura, i dati di HR vengono portati nello stesso database delle altre app Finance and Operations. L'integrazione tra moduli nelle app Finance and Operations non sarà più necessaria.

### <a name="my-organization-uses-one-or-more-isv-solutions-with-dynamics-365-human-resources-will-our-isv-solutions-be-migrated-automatically"></a>La mia organizzazione utilizza una o più soluzioni ISV con Dynamics 365 Human Resources. Le nostre soluzioni ISV verranno migrate automaticamente?

L'esperienza di migrazione per ogni soluzione di fornitore di software indipendente (ISV) varierà a seconda del metodo di integrazione della soluzione. Microsoft lavorerà a stretto contatto con gli ISV per garantire una transizione agevolata alla nuova infrastruttura.

### <a name="my-organization-uses-linkedin-talent-hub-integration-with-dynamics-365-human-resources-will-this-integration-continue-to-work-after-the-infrastructure-change-is-completed"></a>La mia organizzazione utilizza l'integrazione di LinkedIn Talent Hub con Dynamics 365 Human Resources. Questa integrazione continuerà a funzionare dopo il completamento della modifica dell'infrastruttura?

Sì, l'integrazione di LinkedIn Talent Hub continuerà a funzionare dopo la migrazione alla nuova infrastruttura.

### <a name="my-organization-uses-the-human-resources-app-for-teams-will-the-app-continue-to-work-after-the-infrastructure-change-is-completed"></a>La mia organizzazione usa l'app Human Resources per Teams. L'app continuerà a funzionare dopo il completamento della modifica dell'infrastruttura?

Sì, l'app Human Resources per Teams continuerà a funzionare dopo la migrazione alla nuova infrastruttura.

### <a name="my-organization-has-configured-custom-security-in-dynamics-365-human-resources-will-our-custom-security-still-be-applied-after-the-infrastructure-change-is-completed"></a>La mia organizzazione ha configurato la sicurezza personalizzata in Dynamics 365 Human Resources. La nostra sicurezza personalizzata verrà ancora applicata dopo il completamento della modifica dell'infrastruttura?

Sì, le configurazioni di sicurezza personalizzata saranno incluse nella migrazione dei dati alla nuova infrastruttura.

### <a name="we-are-using-data-integrator-to-move-data-between-dynamics-365-human-resources-and-finance-and-operations-apps-how-will-the-data-that-is-currently-being-integrated-be-affected"></a>Stiamo utilizzando l'integrazione dei dati per spostare i dati tra Dynamics 365 Human Resources e le app Finance and Operations. In che modo saranno interessati i dati attualmente in fase di integrazione?

Dati HR attualmente gestiti in Dynamics 365 Human Resources vengono sincronizzati con Dataverse. L'integrazione dei dati può quindi essere utilizzata per la sincronizzazione unidirezionale con le app Finance and Operations. Dopo la migrazione alla nuova infrastruttura, i dati HR saranno nativi per le app Finance and Operations. L'integrazione dei dati non sarà più necessaria per sincronizzare i dati tra le app Finance and Operations e Human Resources.

Le tabelle di dati nativi correnti di Dataverse per Human Resources continueranno a sincronizzare i dati dall'ambiente nella nuova infrastruttura. Le entità verranno convertite per supportare la doppia scrittura. Eventuali altre integrazioni di dati configurate tramite l'integrazione dei dati rispetto a queste tabelle per altre app Dynamics 365 continueranno a funzionare come attualmente configurate.

### <a name="we-are-using-dual-write-to-move-hr-data-between-dataverse-and-other-finance-and-operations-apps-how-will-the-data-that-is-currently-being-integrated-be-affected-by-the-migration-to-the-new-infrastructure"></a>Stiamo usando la doppia scrittura per spostare i dati HR tra Dataverse e altre app Finance and Operations. In che modo i dati attualmente in fase di integrazione saranno influenzati dalla migrazione alla nuova infrastruttura?

I dati HR saranno nativi per le app Finance and Operations nell'ambiente della nuova infrastruttura. La doppia scrittura verrà quindi utilizzata per spostare i dati HR tra il nuovo ambiente e l'ambiente Dataverse.

### <a name="we-have-built-custom-integrations-from-dynamics-365-human-resources-to-one-or-more-external-systems-will-we-have-to-develop-new-integrations-after-the-infrastructure-change-is-completed"></a>Abbiamo creato integrazioni personalizzate da Dynamics 365 Human Resources a uno o più sistemi esterni. Dobbiamo sviluppare nuove integrazioni dopo il completamento della modifica dell'infrastruttura?

Dipende dall'endpoint di integrazione. Per ulteriori informazioni sulle tecnologie di integrazione disponibili nelle app Finance and Operations e su come scegliere la migliore tecnologia di integrazione, vedi [Panoramica dell'integrazione](../fin-ops-core/dev-itpro/data-entities/integration-overview.md).

### <a name="we-have-extended-dataverse-for-dynamics-365-human-resources-will-these-extensions-be-migrated-automatically"></a>Abbiamo esteso Dataverse per Dynamics 365 Human Resources. Queste estensioni verranno migrate automaticamente?

Se gli ambienti Dynamics 365 Human Resources e Finance and Operations che saranno uniti nell'ambiente della nuova infrastruttura sono collegati allo stesso ambiente Dataverse, le due app continueranno ad essere connesse allo stesso ambiente Dataverse dopo la migrazione. Pertanto, non è richiesta alcuna migrazione per le estensioni Dataverse.

Tuttavia se gli ambienti Dynamics 365 Human Resources e Finance and Operations sono attualmente collegati a ambienti Dataverse diversi, i due ambienti Dataverse dovranno essere combinati in modo da connettersi a un singolo ambiente della nuova infrastruttura. Per questa migrazione Dataverse, le tabelle Dataverse standard per le soluzioni Human Resources possono essere collegate e risincronizzate con il nuovo ambiente Dataverse. Tuttavia, eventuali estensioni all'ambiente Dataverse non verranno migrate automaticamente, ma dovranno essere ridistribuite nel nuovo ambiente. Ti consigliamo di utilizzare soluzioni gestite per gestire le tue estensioni Dataverse. Per ulteriori informazioni, vedi [Introduzione alle soluzioni](https://docs.microsoft.com/powerapps/developer/data-platform/introduction-solutions).

### <a name="we-have-configured-microsoft-power-automate-flows-andor-microsoft-power-apps-to-work-with-dynamics-365-human-resources-will-these-microsoft-power-platform-components-be-migrated-and-work-automatically-after-the-infrastructure-change-is-completed"></a>Abbiamo configurato flussi Microsoft Power Automate e/o Microsoft Power Apps per lavorare con Dynamics 365 Human Resources. Questi componenti Microsoft Power Platform saranno migrati e funzionano automaticamente dopo che la modifica dell'infrastruttura è stata completata?

I flussi Power Apps, Power Automate e altre personalizzazioni Microsoft Power Platform sono simili alle estensioni Dataverse. Il funzionamento automatico dopo la migrazione alla nuova infrastruttura varia se l'app Human Resources e le app Finance and Operations sono collegate allo stesso ambiente Power Apps prima della migrazione.

Se le app sono attualmente connesse allo stesso ambiente Power Apps, continueranno ad essere collegate a quell'ambiente Power Apps dopo la migrazione alla nuova infrastruttura. In questo caso, i flussi Power Apps, Power Automate e altre personalizzazioni Microsoft Power Platform continueranno a funzionare senza alcuna configurazione aggiuntiva. Ti consigliamo di utilizzare soluzioni gestite per gestire le tue estensioni delle applicazioni in Dataverse. Per ulteriori informazioni, vedi [Introduzione alle soluzioni](https://docs.microsoft.com/powerapps/developer/data-platform/introduction-solutions).

Tuttavia, se l'app Risorse umane e le app Finance and Operations sono collegate ad ambienti Power Apps separati dovranno essere combinate come parte della migrazione. Questa attività richiederà che qualsiasi personalizzazione Power Apps e altre personalizzazioni vengano ridistribuite nel nuovo ambiente.

### <a name="we-have-enabled-dataverse-virtual-tables-for-dynamics-365-human-resources-what-will-happen-to-these-tables-during-the-migration"></a>Abbiamo abilitato le tabelle virtuali Dataverse per Dynamics 365 Human Resources. Cosa accadrà a queste tabelle durante la migrazione?

Dopo la migrazione, se l'ambiente della nuova infrastruttura rimane connesso all'ambiente Dataverse attualmente connesso a Dynamics 365 Human Resources, le tabelle virtuali Dataverse che sono state generate in quell'ambiente continueranno a funzionare senza alcuna configurazione aggiuntiva.

Tuttavia, se l'ambiente della nuova infrastruttura è connesso a un altro ambiente Dataverse dopo la migrazione, le tabelle virtuali dovranno essere rigenerate nel nuovo ambiente Dataverse.

### <a name="we-have-developed-an-integration-by-using-the-applicant-tracking-system-ats-api-payroll-api-dataverse-virtual-tables-for-dynamics-365-human-resources-or-other-entities-in-the-dataverse-web-api-will-these-integrations-continue-to-work-after-the-infrastructure-change-is-completed"></a>Abbiamo sviluppato un'integrazione utilizzando l'API Applicant Tracking System (ATS), l'API Payroll, le tabelle virtuali Dataverse per Dynamics 365 Human Resources, o altre entità nell'API Web Dataverse. Queste integrazioni continueranno a funzionare dopo il completamento della modifica dell'infrastruttura?

Dopo la migrazione, se l'ambiente della nuova infrastruttura rimane connesso all'ambiente Dataverse attualmente connesso a Dynamics 365 Human Resources, qualsiasi integrazione sviluppata con l'API Web Dataverse continuerà a funzionare una volta completata la migrazione.

Tuttavia, se l'ambiente della nuova infrastruttura è connesso a un ambiente Dataverse diverso dopo la migrazione, qualsiasi integrazione sviluppata con l'API Web Dataverse dovrà essere riconfigurata in modo da connettersi al nuovo ambiente Dataverse.

### <a name="is-there-an-impact-on-the-azure-region-when-my-environment-is-migrated"></a>La migrazione dell'ambiente ha impatto sull'area di Azure?

È previsto che l'ambiente Human Resources rimanga in genere nella stessa area di Azure durante la migrazione. L'unica eccezione si verifica se l'ambiente Human Resources viene unito a un ambiente Finance and Operations che si trova in un'area diversa. In questo caso, l'ambiente Human Resources verrà migrato nell'area di Azure dell'ambiente Finance and Operations.

### <a name="my-organization-depends-on-workflows-in-dynamics-365-human-resources-for-one-or-more-business-processes-will-the-workflows-be-migrated-automatically"></a>La mia organizzazione utilizza i flussi di lavoro di Dynamics 365 Human Resources per uno o più processi aziendali. Questi flussi di lavoro verranno migrati automaticamente?

Sì, verranno migrate le configurazioni del flusso di lavoro, la cronologia del flusso di lavoro e gli attuali flussi di lavoro in uso.

### <a name="what-training-and-resources-will-be-available-to-help-with-the-migration-process"></a>Quale formazione e risorse saranno disponibili per facilitare il processo di migrazione?

Verrà fornita la documentazione completa per descrivere in dettaglio ogni fase del processo di migrazione. Possono essere disponibili anche risorse di formazione aggiuntive, come video e workshop, a seconda delle necessità.

### <a name="my-organization-has-created-saved-views-in-dynamics-365-human-resources-to-improve-the-usability-of-the-interface-will-the-saved-views-be-migrated-automatically"></a>La mia organizzazione ha creato Visualizzazioni salvate in Dynamics 365 Human Resources per migliorare l'usabilità dell'interfaccia. Queste visualizzazioni salvate verranno migrate automaticamente?

Sì, le visualizzazioni salvate verranno migrate alla nuova infrastruttura.

### <a name="we-are-using-ceridian-with-dynamics-365-human-resources-will-the-ceridian-integration-be-available-after-the-infrastructure-change-is-completed"></a>Stiamo usando Ceridian con Dynamics 365 Human Resources. L'integrazione Ceridian sarà disponibile dopo il completamento della modifica dell'infrastruttura? 

L'integrazione con Ceridian verrà migrata all'integrazione basata sull'API retribuzioni. L'integrazione basata su file che esiste attualmente in Dynamics 365 Human Resources non verrà migrata nell'infrastruttura Finance and Operations. Per ulteriori informazioni, vedi [Introduzione all'API retribuzioni](./hr-admin-integration-payroll-api-introduction.md).

### <a name="how-will-the-migration-affect-the-service-update-process"></a>In che modo la migrazione influirà sul processo di aggiornamento del servizio?

Dopo la migrazione, i clienti avranno molta più flessibilità in termini di ALM e aggiornamenti del servizio. Gli aggiornamenti del servizio non verranno più applicati automaticamente agli ambienti Human Resources. Il servizio seguirà invece i processi e le funzionalità di aggiornamento del servizio One Version. Pertanto, le opzioni di configurazione per gli aggiornamenti saranno disponibili tramite LCS. Per ulteriori informazioni, vedi [Panoramica di One Version](../fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview.md).

### <a name="how-will-the-migration-affect-my-lcs-project-for-dynamics-365-human-resources"></a>In che modo la migrazione influenzerà il mio progetto LCS per Dynamics 365 Human Resources?

La migrazione alla nuova infrastruttura sposterà la gestione dei tuoi ambienti Dynamics 365 Human Resources in un progetto di implementazione LCS. Se la migrazione sta unendo Dynamics 365 Human Resources con un ambiente esistente Finance and Operations, il progetto LCS Human Resources sarà unito nel progetto di implementazione LCS per l'app Finance and Operations. Se stai attualmente utilizzando solo Dynamics 365 Human Resources, verrà creato un nuovo progetto di implementazione LCS e il progetto LCS Human Resources esistente verrà migrato al nuovo progetto.

Il nuovo progetto sarà lo stesso tipo di progetto usato dalle app Finance and Operations. Avrà le stesse caratteristiche e funzionalità per la gestione dell'ambiente. Per ulteriori informazioni, vedi [Risorse Lifecycle Services](../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

### <a name="we-have-linked-our-task-recordings-to-the-business-process-modeler-in-human-resources-how-will-the-business-process-modeler-be-migrated-and-merged-into-lcs"></a>Abbiamo collegato le nostre registrazioni attività al Modellatore di processi aziendali in Human Resources. In che modo il Modellatore di processi aziendali verrà migrato e unito in LCS?

Le librerie dei processi aziendali per il progetto LCS verranno migrate al nuovo progetto LCS per Human Resources.

### <a name="my-organization-currently-uses-only-dynamics-365-human-resources-what-resources-are-available-so-that-we-can-learn-more-about-the-development-capabilities-after-the-infrastructure-change-is-completed"></a>La mia organizzazione attualmente utilizza solo Dynamics 365 Human Resources. Quali risorse sono disponibili con le informazioni sulle capacità di sviluppo una volta completata la modifica dell'infrastruttura?

Le opzioni di estendibilità Microsoft Power Platform e di Finance and Operations saranno disponibili e potranno essere utilizzate per lo sviluppo. Per ulteriori informazioni, vedi [Sviluppare e personalizzare la home page](../fin-ops-core/dev-itpro/dev-tools/developer-home-page.md).

### <a name="we-have-enabled-features-in-dynamics-365-human-resources-will-these-features-be-enabled-automatically-during-the-migration"></a>Abbiamo abilitato le funzionalità in Dynamics 365 Human Resources. Queste funzionalità verranno abilitate automaticamente durante la migrazione?

L'abilitazione automatica di una funzionalità nella nuova infrastruttura verrà determinata individualmente per ciascuna funzionalità. Queste informazioni saranno incluse nella documentazione della funzionalità.

### <a name="what-happens-to-my-byod-database-during-the-migration"></a>Cosa accade al mio database BYOD durante la migrazione?

Le configurazioni di importazione ed esportazione per il database BYOD verranno migrate nella nuova infrastruttura.

### <a name="what-happens-to-my-azure-data-lake-during-the-migration"></a>Cosa accade al mio Azure Data Lake durante la migrazione?

Qualsiasi esportazione attualmente configurata per Azure Data Lake Storage nelle app Finance and Operations manterrà la stessa configurazione dopo la migrazione.

### <a name="we-are-currently-using-dynamics-ax-2012-will-the-upgrade-tools-that-are-currently-available-be-used-to-upgrade-the-hr-module-in-ax-2012-to-dynamics-365-human-resources"></a>Attualmente stiamo utilizzando Dynamics AX 2012. Gli strumenti di aggiornamento attualmente disponibili verranno utilizzati per aggiornare il modulo HR in AX 2012 a Dynamics 365 Human Resources?

Sì. Dynamics 365 Human Resources sarà incluso nella base di codice e nell'infrastruttura unite per le app Finance and Operations. Un aggiornamento da Dynamics AX 2012 a Dynamics 365 Human Resources utilizzerà lo stesso percorso di aggiornamento e gli stessi strumenti utilizzati per eseguire l'aggiornamento all'ultima versione delle app Finance and Operations.

### <a name="we-use-document-handling-with-dynamics-365-human-resources-what-will-happen-to-the-documents-during-the-migration"></a>Usiamo la gestione dei documenti con Dynamics 365 Human Resources. Cosa accadrà a questi documenti durante la migrazione?

I documenti rimarranno nell'archivio documenti esistente. Verranno rimappati nell'ambiente della nuova infrastruttura.

### <a name="what-happens-to-the-batch-jobs-that-we-have-configured-in-dynamics-365-human-resources-after-the-migration"></a>Cosa succede ai processi batch che abbiamo configurato in Dynamics 365 Human Resources dopo la migrazione?

I processi batch applicabili verranno migrati automaticamente nella nuova infrastruttura.

## <a name="licensing-impact"></a>Impatto sulle licenze

Questa documentazione non sostituisce la documentazione legale che illustra i diritti di utilizzo.

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-its-hr-operations-does-our-licensing-or-cost-change"></a>La mia organizzazione utilizza Dynamics 365 Human Resources per gestire le operazioni HR. La licenza o i costi cambiano?

I clienti che hanno acquistato le licenze Dynamics 365 Human Resources non saranno interessati. Non è prevista la migrazione delle licenze per questi clienti. L'unità di stockkeeping (SKU) sandbox aggiuntiva che era specifica per Human Resources non sarà più applicabile. I clienti possono scegliere di acquistare un sandbox di livello 2 delle app Finance and Operations a un costo leggermente inferiore. I clienti esistenti che hanno acquistato un sandbox Human Resources verranno migrati a un sandbox di livello 2 delle app Finance and Operations senza costi aggiuntivi.

### <a name="my-organization-uses-dynamics-365-human-resources-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-does-my-licensing-or-cost-change"></a>La mia organizzazione utilizza Dynamics 365 Human Resources in Dynamics 365 Finance, Supply Chain Management, Commerce, o Project Operations. La mia licenza o i costi cambiano?

Gli utenti esistenti delle app Dynamics 365 e gli utenti di istanze autonome di Dynamics 365 Finance, Supply Chain Management, Commerce e Project Operations possono accedere a Human Resources come parte delle licenze fino a febbraio 2025 o fino alla scadenza dell'attuale contratto di licenza, a seconda di quale evento si verifica prima. Puoi scegliere di passare alle licenze di Human Resources prima se ottieni un miglior risparmio sui costi. A partire da febbraio 2025, tutti i clienti CSP ed EA esistenti devono abbandonare il modulo HR e acquistare licenze Human Resources per utilizzare le nuove funzionalità che vengono portate nelle app Finance and Operations.

### <a name="my-organization-is-live-with-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-will-we-be-required-to-purchase-an-additional-environment-to-support-the-infrastructure-merge"></a>La mia organizzazione utilizza Dynamics 365 Finance, Supply Chain Management, Commerce, o Project Operations. Ci sarà richiesto di acquistare un ambiente aggiuntivo per supportare l'unione dell'infrastruttura?

Non sono necessari ambienti aggiuntivi per supportare la modifica dell'infrastruttura.

### <a name="where-should-i-go-if-i-have-additional-questions-about-product-licensing"></a>Dove devo rivolgermi se ho ulteriori domande sulla licenza del prodotto?

Se hai domande sulla licenza, puoi trovare maggiori informazioni in [Biz Apps Hub – Prezzi e licenze D365](https://businessapplications.transform.microsoft.com/resources/pricing-and-licensing?tab=grandfathering). Se queste informazioni non risolvono il tuo problema, apri una richiesta con LicenseQ.

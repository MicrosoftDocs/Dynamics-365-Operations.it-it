---
title: Domande frequenti sull'unione dell'infrastruttura Dynamics 365 Human Resources
description: Questo articolo fornisce le risposte alle domande frequenti sull'unione dell'infrastruttura per Microsoft Dynamics 365 Human Resources e le app per la finanza e le operazioni.
author: twheeloc
ms.date: 11/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7325231718d7387450391b16b2866f9a2c05bdc4
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779637"
---
# <a name="dynamics-365-human-resources-infrastructure-merge-faq"></a>Domande frequenti sull'unione dell'infrastruttura Dynamics 365 Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="what-is-dynamics-365-human-resources"></a>Che cosa è Dynamics 365 Human Resources?

Microsoft Dynamics 365 Human Resources fornisce gli strumenti che aiutano i team HR a migliorare l'agilità organizzativa, trasformare l'esperienza dei dipendenti e ottimizzare i programmi HR per creare un ambiente di lavoro in cui le persone possano avere successo e l'attività possa prosperare. Per altre informazioni su Dynamics 365 Human Resources, vedere [Dynamics 365 Human Resources](https://dynamics.microsoft.com/human-resources/overview/).

- **Trasformazione delle esperienze dei dipendenti.** Trattieni i tuoi migliori elementi fornendo gli strumenti ottimali a manager e dipendenti con esperienze self-service connesse che favoriscono l'impegno e la crescita.
- **Ottimizzazione dei programmi HR.** Riduci i costi operativi e crea programmi di gestione di congedi e assenze, orario, benefit e retribuzione incentrati sulle persone.
- **Aumento dell'agilità organizzativa.** Consenti al reparto HR di operare con la destrezza richiesta dall'azienda mediante l'uso di Dataverse e Microsoft Power Platform per centralizzare i dati delle persone ed estendere facilmente Dynamics 365 Human Resources.
- **Scopri le informazioni dettagliate sulla forza lavoro.** Prendi decisioni basate sui dati grazie alla possibilità di analizzare e visualizzare i dati delle persone su dashboard avanzati disponibili su qualsiasi dispositivo.

## <a name="value-and-benefits-of-the-infrastructure-merge"></a>Valore e vantaggi dell'unione dell'infrastruttura

### <a name="what-is-the-dynamics-365-human-resources-infrastructure-merge"></a>Qual è l'unione dell'infrastruttura di Dynamics 365 Human Resources?

Attualmente sono disponibili due set separati di funzionalità HR in due diverse infrastrutture in Dynamics 365:

- **Dynamics 365 Human Resources**: un'app autonoma eseguita su un'infrastruttura indipendente. Quando questa app veniva avviata, l'infrastruttura era separata dalle altre app Dynamics 365 Operations. I nostri clienti usano quest'app per migliorare l'agilità organizzativa, ottimizzare i programmi per le risorse umane, trasformare le esperienze dei dipendenti e fornire informazioni dettagliate sulla forza lavoro
- **Modulo HR**: un set di funzionalità legacy che faceva parte in precedenza dello SKU di licenze di Unified Operations. Il modulo HR viene eseguito sull'infrastruttura di finanza e operazioni, che è lo stesso in tutte le app per le operazioni. Queste app includono Dynamics 365 Finance, Dynamics 365 Project Operations e Dynamics 365 Supply Chain Management. I clienti ricevevano le funzionalità HR nell'ambito di Dynamics 365 Finance o Dynamics 365 Supply Chain Management.

Negli ultimi tre anni, Microsoft non ha aggiunto ulteriori nuove funzionalità o miglioramenti al modulo HR. I nostri investimenti nella roadmap sono invece stati incentrati sull'app Dynamics 365 Human Resources.

Unendo questi due set di funzionalità nella stessa infrastruttura, aiuteremo i clienti a ottenere i seguenti vantaggi:

- Miglioramenti aggiunti a Dynamics 365 Human Resources negli ultimi tre anni, incluse le funzionalità per congedi e assenze, gestione dei benefit e creazione di report migliorati.
- Maggiore estendibilità in Microsoft Power Platform e possibilità di estendere la logica di business per personalizzare le pagine.
- Distribuzione, aggiornamenti e manutenzione migliorate e coerenti in termine di gestione del ciclo di vita delle applicazioni (ALM), servizi per il ciclo di vita, disponibilità geografica e altro ancora.
- Più innovazione tecnologica, grazie all'uso di servizi e strumenti condivisi da parte del nostro team di progettazione, e riduzione dei costi della piattaforma.

Questa transizione interesserà i clienti che al momento usano Dynamics 365 Human Resources o il modulo HR legacy.

## <a name="glossary-of-terms-used-in-this-faq"></a>Glossario dei termini utilizzati in queste domande frequenti

- **Dynamics 365 Human Resources**: il nostro prodotto attuale e futuro che offre funzionalità HR al mercato.
- **Modulo HR**: un set di funzionalità legacy che concesso precedentemente in licenza con l'offerta Unified Operations. Le funzionalità vengono abilitate quando un cliente possiede Dynamics 365 Finance o Dynamics 365 Supply Chain Management.
- **Infrastruttura di finanza e operazioni**: l'architettura di sviluppo usata dal portafoglio per le operazioni, inclusi Dynamics 365 Finance, Dynamics 365 Supply Chain Management e Dynamics 365 Project Operations. Questa è l'infrastruttura che verrà usata d'ora in avanti. In queste domande frequenti, il terme *infrastruttura unita* si riferisce all'ambiente di finanza e operazioni.
- **Infrastruttura di risorse umane**: l'architettura di sviluppo storicamente usata per l'app Dynamics 365 Human Resources. Il progetto di unione dell'infrastruttura porta Dynamics 365 Human Resources nell'infrastruttura di finanza e operazioni. L'infrastruttura autonoma non verrà più supportata.

## <a name="general-questions-about-the-infrastructure-merge"></a>Domande generali sull'unione dell'infrastruttura

### <a name="will-customers-lose-any-features-or-capabilities"></a>I clienti perderanno le funzioni o le funzionalità che usano abitualmente?

Il nostro obiettivo è ridurre al minimo l'impatto di questa transizione sui clienti. Non rimuoveremo funzioni o funzionalità esistenti. Ci sarà parità funzionale tra Dynamics 365 Human Resources e il modulo HR. Nei casi in cui una funzione esiste in entrambe le infrastrutture, verrà usata l'esperienza Dynamics 365 Human Resources.

### <a name="will-the-user-experience-change"></a>L'esperienza dell'utente cambierà?

L'esperienza dell'utente sarà coerente con l'esperienza della piattaforma Dynamics 365 standard. Anche se l'esperienza generale per il dashboard e i menu resterà simile, verrà allineata all'esperienza dell'app Dynamics 365 Finance. Lo spostamento includerà sia moduli che aree di lavoro, la possibilità di impostare dei preferiti e altro ancora. Le aree di lavoro di Dynamics 365 Human Resources, quali **Gestione del personale** e **Persone**, verranno unite nell'infrastruttura di finanza e operazioni. In futuro, verranno fornite nuove funzionalità tramite la gestione delle funzionalità, che permette ai clienti di visualizzare nuove funzionalità e decidere quali usare. Per maggiori informazioni, vedere [Panoramica della gestione delle funzionalità](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e [Documentazione dell'interfaccia utente](../fin-ops-core/fin-ops/get-started/user-interface-elements.md?toc=/dynamics365/human-resources/toc.json).

### <a name="when-will-the-dynamics-365-human-resources-infrastructure-merge-be-completed"></a>Quando verrà completata l'unione dell'infrastruttura Dynamics 365 Human Resources?

L'unione dell'infrastruttura verrà implementata in fasi per garantire i clienti il tempo di pianificare e completare i passaggi necessari. Abbiamo iniziato a implementare le funzionalità nel secondo ciclo di rilascio 2021 di Dynamics. Prevediamo di completare tutte le attività di sviluppo del prodotto per questo progetto entro la fine del secondo ciclo di rilascio 2022. Le tempistiche sono soggette a modifica. Per informazioni aggiornate, vedere [piani di rilascio](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-finance).

### <a name="what-training-and-resources-will-be-available-to-help-with-the-infrastructure-merge"></a>Quale formazione e risorse saranno disponibili per facilitare l'unione dell'infrastruttura?

Forniremo la documentazione per descrivere nei dettagli ogni passaggio del processo di unione dell'infrastruttura. Forniremo ulteriori risorse di formazione, quali video e workshop, laddove necessario per semplificare la transizione per clienti e partner.

### <a name="will-there-be-changes-in-development-capabilities-after-the-infrastructure-merge-is-completed"></a>Ci saranno delle modifiche nelle funzionalità di sviluppo, una volta completata l'unione dell'infrastruttura?

Per altre informazioni sulle funzionalità di sviluppo, vedere [Sviluppo e personalizzazione della home page](../fin-ops-core/dev-itpro/dev-tools/developer-home-page.md).

## <a name="feature-availability-questions"></a>Domande sulla disponibilità delle funzionalità

### <a name="will-the-linkedin-talent-hub-integration-work-on-the-finance-and-operations-infrastructure"></a>L'integrazione LinkedIn Talent Hub continuerà a funzionare nell'infrastruttura di finanza e operazioni?

No, l'integrazione LinkedIn Talent Hub non farà parte dell'infrastruttura unita? Saranno disponibili interfacce di programmazione delle applicazioni (API) pubbliche per creare integrazioni con soluzioni di reclutamento e monitoraggio dei candidati. I clienti che prevedono di usare LinkedIn Talent Hub devono rivolgersi al partner Microsoft per collaborare all'integrazione mediante le API fornite. Per maggiori informazioni sulle API di integrazione di Applicant Tracking System (ATS), vedere [Introduzione all'API di integrazione di Applicant Tracking System](./hr-admin-integration-ats-api-introduction.md).

### <a name="will-the-capabilities-that-are-currently-available-only-in-dynamics-365-human-resources-for-example-leave-management-and-benefits-management-be-available-after-the-merge-is-completed"></a>Le funzionalità attualmente disponibili solo in Dynamics 365 Human Resources (ad esempio, gestione dei congedi e dei benefit) saranno disponibili una volta completata l'unione?

Sì. Tutte le funzionalità delle applicazioni Dynamics 365 Human Resources verranno migrate nell'infrastruttura di finanza e operazioni. Le funzionalità saranno rese disponibili mediante un approccio graduale. Per informazioni aggiornate sulla disponibilità delle funzionalità per l'infrastruttura unita, consultare regolarmente i [piani di rilascio](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-finance).

### <a name="will-ceridian-integrations-with-dynamics-365-human-resources-be-available-after-the-infrastructure-merge-is-completed"></a>Le integrazioni Ceridian con Dynamics 365 Human Resources saranno disponibili una volta completata l'unione dell'infrastruttura?

Ceridian sta attualmente creando un'integrazione V2 con Dynamics 365 Human Resources che sfrutta le API per le retribuzioni. L'integrazione basata su file che esiste attualmente in Dynamics 365 Human Resources non verrà migrata nell'infrastruttura di finanza e operazioni. Per ulteriori informazioni, vedi [Introduzione all'API retribuzioni](./hr-admin-integration-payroll-api-introduction.md).

### <a name="will-applicant-tracking-or-onboardingoffboarding-of-employees-functionality-be-included"></a>Le funzionalità di monitoraggio dei candidati e di onboarding/offboarding dei dipendenti saranno incluse?

Nelle versioni precedenti, abbiamo creato l'API di integrazione di ATS per consentire a partner e clienti di creare integrazioni ATS con Human Resources. Ulteriori funzionalità correlate ad ATS sono state rese disponibili nel primo ciclo del 2022. Continueremo a migliorare queste API nelle versioni future.

La funzionalità HR attualmente esistente nell'infrastruttura di finanza e operazioni include alcune funzionalità di gestione del reclutamento non presenti in Dynamics 365 Human Resources. Una volta completata l'unione dell'infrastruttura, queste funzionalità saranno rese disponibili a tutti i clienti di Human Resources. Questa funzionalità offre funzionalità ATS ridotte. Tuttavia, non prevediamo di ampliare queste funzionalità in futuro. I clienti che richiedono funzionalità avanzate possono sfruttare le integrazioni dei partner ATS. Per maggiori informazioni sulle API di integrazione di ATS, vedere [Introduzione all'API di integrazione di Applicant Tracking System](./hr-admin-integration-ats-api-introduction.md).

### <a name="will-the-dynamics-ax-2012-upgrade-tools-be-used-to-upgrade-the-hr-module-in-ax-2012-to-the-dynamics-365-human-resources-app"></a>Verranno usati gli strumenti di aggiornamento di Dynamics AX 2012 per aggiornare il modulo HR in AX 2012 all'app Dynamics 365 Human Resources?

Sì. L'aggiornamento da Dynamics AX 2012 a Dynamics 365 Human Resources utilizzerà lo stesso percorso di aggiornamento e gli stessi strumenti usati per eseguire l'aggiornamento alla versione più recente di altre app Dynamics 365 for Operations, ad esempio Dynamics 365 Finance o Dynamics 365 Supply Chain Management.

Per ulteriori informazioni sulla migrazione all'infrastruttura di finanza e operazioni, vedere [Domande frequenti sulla migrazione dei clienti Human Resources](./customer-migration.md).

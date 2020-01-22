---
title: Novità e modifiche in Dynamics 365 Talent (11 giugno 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 06/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-06-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: f2ee23733d686480cd4323cab952ae12eceaf142
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897582"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-june-11-2019"></a>Novità e modifiche in Dynamics 365 Talent (11 giugno 2019)

Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

### <a name="search-engine-optimization-for-job-posts"></a>Ottimizzazione del motore di ricerca per annunci di lavoro

Dopo l'attivazione di **Ottimizzazione del motore di ricerca** nell'interfaccia di amministrazione di Dynamics 365 Talent: Attract, Attract indica all'API Google Indexing di effettuare la ricerca per indicizzazione della pagina Web ogni volta che si attiva e si pubblica un nuovo annuncio di lavoro o se ne aggiorna uno esistente. In questo modo, l'annuncio di lavoro sarà visualizzato nei risultati delle ricerca per Google e altri motori di ricerca.

Analogamente, ogni volta che si annulla la pubblicazione di un annuncio di lavoro, Attract informa l'API di indicizzazione, di modo che tale annuncio non sia incluso nei risultati della ricerca.

> [!NOTE]
> I crawler Web non dispongono di un periodo di tempo definito per la ricerca per indicizzazione delle pagine Web o l'aggiornamento dei risultati di ricerca.

## <a name="coming-soon-in-attract"></a>Funzionalità presto disponibili in Attract

### <a name="job-approvals-appear-on-the-home-page"></a>Approvazioni delle mansioni visualizzate nella home page

Le approvazioni sono visualizzate nella sezione **Approvazioni** del dashboard. Gli approvatori possono esaminare le relative approvazioni in **Assegnate all'utente**, in cui è visualizzato l'ID mansione, il titolo della mansione, altri approvatori e la data in cui la mansione è stata assegnata. Gli utenti che inviano una mansione per l'approvazione possono esaminare le mansioni in **Richieste dall'utente** in cui sono visualizzati gli approvatori che devono ancora approvare la mansione inviata.

## <a name="changes-in-onboard"></a>Modifiche in Onboard

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR

Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2337.

### <a name="platform-update-27-for-finance-and-operations"></a>Aggiornamento 27 della piattaforma per Finance and Operations

Per ulteriori dettagli sull'aggiornamento 27 della piattaforma per Finance and Operations, vedere [Funzionalità di anteprima nell'aggiornamento 27 della piattaforma Dynamics 365 Finance and Operations (giugno 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-27).

### <a name="feature-management-workspace-in-talent"></a>Area di lavoro Gestione funzionalità in Talent

L'area di lavoro **Gestione funzionalità** in **Amministrazione sistema** consente di visualizzare, abilitare, disabilitare e programmare funzionalità fornite in ogni versione. Per impostazione predefinita, le nuove funzionalità sono disabilitate. È possibile utilizzare l'area di lavoro **Gestione funzionalità** per attivarle e visualizzare la documentazione correlata.

### <a name="common-data-service-entity-support-for-custom-fields"></a>Support dell'entità Common Data Service per i campi personalizzati

L'entità Agenzia emittente ora supporta i campi personalizzati.

### <a name="new-common-data-service-entities"></a>Nuove entità di Common Data Service

L'entità Gruppo di attività è stata aggiunta.

## <a name="in-preview"></a>In anteprima

### <a name="preview-features-will-be-enabled-only-in-sandbox-environments"></a>Le funzionalità di anteprima verranno attivate solo negli ambienti sandbox

Per ulteriori informazioni su come vengono pubblicate le modifiche, vedere [Eseguire il provisioning di Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

Quando si esegue il provisioning di una nuova istanza di Talent, è possibile indicare se il tipo di istanza è Produzione o Sandbox. Il tipo di istanza Sandbox consente di testare le nuove funzionalità prima dell'utilizzo. Tutte le istanze Talent esistenti verranno aggiornate al tipo di istanza di **produzione**. Se si desidera aggiornare una delle istanze esistenti al tipo di istanza **Sandbox**, contattare il [supporto tecnico](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) per avviare la richiesta di modifica.

### <a name="restrict-the-leave-types-in-time-off-requests"></a>Limitare i tipi di congedo nelle richieste di permessi

Le organizzazioni possono offrire molti tipi di congedo ai dipendenti. Tuttavia, potrebbe non essere appropriato per i dipendenti inviare richieste di permesso per alcuni tipi di congedo. Tali tipi di congedo possono invece essere gestiti dalle risorse umane. In questa versione, è possibile configurare i tipi di congedo per i quali i dipendenti possono inviare richieste di permessi. 

## <a name="coming-soon-in-core-hr"></a>Funzionalità presto disponibili in Core HR

### <a name="view-extended-information-about-report-performance-in-manager-self-service"></a>Visualizzare informazioni estese sulle prestazioni dei report in Responsabile self-service

Una nuova opzione consentirà ai responsabili di visualizzare le prestazioni dei report diretti ed estesi. Attualmente, i responsabili linea possono assegnare e aggiornare obiettivi prestazionali e pubblicare nuove revisioni. Inoltre, i responsabili diretti e i relativi dipendenti possono gestire e aggiornare giornali di registrazione prestazioni per garantire la corretta esecuzione del processo di valutazione delle prestazioni. Una volta questa modifica implementata, i responsabili potranno visualizzare e gestire informazioni relative alle prestazioni per i report estesi oltre che per quelli diretti.

### <a name="print-performance-reviews"></a>Stampare le valutazioni delle prestazioni

Dipendenti, responsabili e risorse umane potranno stampare la valutazione delle prestazioni di un dipendente.

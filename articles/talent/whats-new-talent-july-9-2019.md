---
title: Novità e modifiche in Dynamics 365 Talent (9 luglio 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 07/09/2019
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
ms.search.validFrom: 2019-07-09
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 99a7e6130d45229011a185087d4872fe34b8224a
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897628"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-july-9-2019"></a>Novità e modifiche in Dynamics 365 Talent (9 luglio 2019)

Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Attract.

### <a name="coming-soon-in-attract"></a>Funzionalità presto disponibili in Attract

#### <a name="job-approvals-appear-on-the-home-page"></a>Approvazioni delle mansioni visualizzate nella home page

Le approvazioni sono visualizzate nella sezione **Approvazioni** del dashboard. Gli approvatori possono esaminare le relative approvazioni in **Assegnate all'utente**, in cui è visualizzato l'ID mansione, il titolo della mansione, altri approvatori e la data in cui la mansione è stata assegnata. Gli utenti che inviano una mansione per l'approvazione possono esaminare le mansioni in **Richieste dall'utente** in cui sono visualizzati gli approvatori che devono ancora approvare la mansione inviata.

## <a name="changes-in-onboard"></a>Modifiche in Onboard

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR

Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2374.

### <a name="platform-update-28-for-finance-and-operations"></a>Aggiornamento 28 della piattaforma per Finance and Operations

Per ulteriori dettagli sull'aggiornamento 28 della piattaforma per Finance and Operations, vedere [Funzionalità di anteprima nell'aggiornamento 28 della piattaforma Dynamics 365 Finance and Operations (luglio 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-28).

### <a name="entity-support-for-custom-fields-in-common-data-service"></a>Supporto entità per i campi personalizzati in Common Data Service 

Le seguenti entità supportano campi personalizzati: 

- **Piano di retribuzione fissa**
- **Impostazione punti di riferimento per le retribuzioni**
- **Riga impostazione punti di riferimento per le retribuzioni**
- **Codice di reddito per retribuzione**
- **Periodo retributivo**
- **Evento di retribuzione fissa**
- **Griglia retributiva**

Per visualizzare tutte le entità aggiornate in Talent:

1. Selezionare **Amministrazione sistema**, **Collegamenti**, quindi selezionare **Configurazione Common data service**.
2. Selezionare il menu a discesa **Nome entità CDS**. Tutte le entità elencate sono presenti nella versione più recente. 

###  <a name="full-name-added-to-worker-entity-in-common-data-service"></a>Nome completo aggiunto all'entità Lavoratore in Common Data Service

Il campo **Nome completo** è stato aggiunto all'entità **Lavoratore**.

### <a name="full-time-equivalent-higher-than-10"></a>Equivalente a tempo pieno superiore a 1,0

Un avviso indica se un valore maggiore di 1,0 viene immesso per un dipendente a tempo pieno in una posizione. 

### <a name="a-warning-no-longer-displays-on-the-worker-page-when-there-is-no-future-dated-employment"></a>Non viene più visualizzato un avviso nella pagina Lavoratore quando non è presente un impiego a data futura

Non viene più ricevuto un messaggio indicante la presenza di un futuro impiego quando si naviga alla pagina **Lavoratore** dall'elenco **Dipendenti in uscita** nell'area di lavoro **Gestione dipendente**. 

### <a name="unable-to-delete-a-business-process-in-talent"></a>Impossibile eliminare un processo aziendale in Talent

È ora possibile eliminare i processi aziendali nell'area di lavoro **Processo aziendale**.

### <a name="leave-balance-no-longer-displays-zero-for-plans-with-no-accruals-when-using-balance-as-of-accrual-period"></a>In Saldo di congedo non viene più visualizzato zero per i piani senza ratei quando si utilizza il saldo dal periodo di attribuzione per competenza

I piani impostati senza ratei possono ora visualizzare un saldo.

## <a name="in-preview"></a>In anteprima

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Le funzionalità di anteprima vengono attivate solo nelle istanze sandbox

Quando si esegue il provisioning di una nuova istanza di Talent, è possibile specificare se il tipo di istanza è **Produzione** o **Sandbox**. Le istanze **Sandbox** consentono di testare tle nuove funzionalità prima dell'utilizzo. Tutte le istanze Talent esistenti verranno aggiornate al tipo di istanza di **produzione**. Se si desidera aggiornare una delle istanze esistenti al tipo di istanza **Sandbox**, contattare il [supporto tecnico](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) per avviare la richiesta di modifica.

Per ulteriori informazioni su come vengono pubblicate le modifiche, vedere [Eseguire il provisioning di Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="restrict-leave-types-in-time-off-requests"></a>Limitare i tipi di congedo nelle richieste di permessi

Le organizzazioni possono offrire diversi tipi di congedo differenti ai dipendenti. Tuttavia, potrebbe non essere appropriato per i dipendenti inviare richieste di permesso per alcuni tipi di congedo. Tali tipi di congedo possono invece essere gestiti dalle risorse umane. In questa versione, è possibile configurare i tipi di congedo per i quali i dipendenti possono inviare richieste di permessi. 

## <a name="coming-soon-in-core-hr"></a>Funzionalità presto disponibili in Core HR

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Visualizzare informazioni estese per le prestazioni in Responsabile self-service

Una nuova opzione consentirà ai responsabili di visualizzare le prestazioni dei report diretti ed estesi. Attualmente, i responsabili linea possono assegnare e aggiornare obiettivi prestazionali e pubblicare nuove revisioni, cogestite dai relativi dipendenti. Inoltre, i responsabili diretti e i relativi dipendenti possono gestire e aggiornare giornali di registrazione prestazioni per garantire la corretta esecuzione del processo di valutazione delle prestazioni. Una volta questa modifica implementata, i responsabili potranno visualizzare e gestire informazioni relative alle prestazioni per i report estesi oltre che per quelli diretti. 

### <a name="entities-supporting-custom-fields"></a>Entità che supportano campi personalizzati

Le seguenti entità verranno abilitate al supporto di campi personalizzati in Common Data Service: 

- **Tipo di congedo**
- **Conto bancario del lavoratore**
- **Calendario lavorativo**

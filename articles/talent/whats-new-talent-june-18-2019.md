---
title: Novità e modifiche in Dynamics 365 Talent (18 giugno 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 06/18/2019
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
ms.search.validFrom: 2019-06-18
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 4323496736ddf3e3558f15679789cbc13013720c
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898991"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-june-18-2019"></a>Novità e modifiche in Dynamics 365 Talent (18 giugno 2019)

Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Attract.

## <a name="coming-soon-in-attract"></a>Funzionalità presto disponibili in Attract

### <a name="job-approvals-appear-on-the-home-page"></a>Approvazioni delle mansioni visualizzate nella home page

Le approvazioni sono visualizzate nella sezione **Approvazioni** del dashboard. Gli approvatori possono esaminare le relative approvazioni in **Assegnate all'utente**, in cui è visualizzato l'ID mansione, il titolo della mansione, altri approvatori e la data in cui la mansione è stata assegnata. Gli utenti che inviano una mansione per l'approvazione possono esaminare le mansioni in **Richieste dall'utente** in cui sono visualizzati gli approvatori che devono ancora approvare la mansione inviata.

## <a name="changes-in-onboard"></a>Modifiche in Onboard

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR

Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2347.

### <a name="confirmation-of-course-participants-causes-an-error"></a>La conferma dei partecipanti al corso provoca un errore

La finestra di dialogo per la stampa del report relativo ai partecipanti al corso è stata rimossa. Questo report non è supportato in Talent.

### <a name="the-compensation-section-of-the-transfer-worker-page-isnt-available-in-some-scenarios"></a>La sezione Retribuzione nella pagina Trasferisci lavoratore non è disponibile in alcuni scenari

Questa modifica consente agli utenti di immettere dati relativi alla retribuzione quando riempiono i campi della pagina **Trasferisci lavoratore**.

## <a name="in-preview"></a>In anteprima

### <a name="preview-features-will-be-enabled-only-in-sandbox-environments"></a>Le funzionalità di anteprima verranno attivate solo negli ambienti sandbox

Per ulteriori informazioni su come vengono pubblicate le modifiche, vedere [Eseguire il provisioning di Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

Quando si esegue il provisioning di una nuova istanza di Talent, è possibile indicare se il tipo di istanza è **Produzione** o **Sandbox**. Il tipo di istanza **Sandbox** consente di testare le nuove funzionalità prima dell'utilizzo. Tutte le istanze Talent esistenti verranno aggiornate al tipo di istanza di **produzione**. Se si desidera aggiornare una delle istanze esistenti al tipo di istanza **Sandbox**, contattare il [supporto tecnico](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) per avviare la richiesta di modifica.

### <a name="restrict-the-leave-types-in-time-off-requests"></a>Limitare i tipi di congedo nelle richieste di permessi

Le organizzazioni possono offrire molti tipi di congedo ai dipendenti. Tuttavia, potrebbe non essere appropriato per i dipendenti inviare richieste di permesso per alcuni tipi di congedo. Tali tipi di congedo possono invece essere gestiti dalle risorse umane. In questa versione, è possibile configurare i tipi di congedo per i quali i dipendenti possono inviare richieste di permessi. 

## <a name="coming-soon-in-core-hr"></a>Funzionalità presto disponibili in Core HR

### <a name="common-data-service-entity-support-for-custom-fields"></a>Support dell'entità Common Data Service per i campi personalizzati

Le seguenti entità supporteranno campi personalizzati: Codici di reddito per retribuzione e Punti di riferimento per retribuzione. 

### <a name="new-common-data-service-entities"></a>Nuove entità di Common Data Service

L'entità Codici motivo verrà aggiunta a Common Data Service.

### <a name="view-performance-information-for-direct-and-extended-reports-in-manager-self-service"></a>Visualizzare le informazioni sulle prestazioni per report diretti ed estesi in Responsabile self-service

Una nuova opzione consentirà ai responsabili di visualizzare le prestazioni dei report diretti ed estesi. Attualmente, i responsabili linea possono assegnare e aggiornare obiettivi prestazionali e pubblicare nuove revisioni. Inoltre, i responsabili diretti e i relativi dipendenti possono gestire e aggiornare giornali di registrazione prestazioni per garantire la corretta esecuzione del processo di valutazione delle prestazioni. Una volta questa modifica implementata, i responsabili potranno visualizzare e gestire informazioni relative alle prestazioni per i report estesi oltre che per quelli diretti.

### <a name="print-performance-reviews"></a>Stampare le valutazioni delle prestazioni

Dipendenti, responsabili e risorse umane potranno stampare la valutazione delle prestazioni di un dipendente.

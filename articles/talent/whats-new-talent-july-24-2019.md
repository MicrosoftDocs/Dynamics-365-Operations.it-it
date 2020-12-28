---
title: Novità e modifiche in Dynamics 365 Talent (23 luglio 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 07/23/2019
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
ms.search.validFrom: 2019-07-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 360574d3c8e0b349119e0987f2453a5d5be21e90
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528149"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-july-23-2019"></a>Novità e modifiche in Dynamics 365 Talent (23 luglio 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

### <a name="pdf-renderer-for-candidate-documents"></a>Rendering PDF per i documenti del candidato

Gli utenti di Attract possono ora visualizzare gli allegati PDF per i candidati nel Visualizzatore documento anziché scaricarli.

### <a name="signing-up-for-attract-user-research-group"></a>Iscrizione al gruppo di ricerca utenti di Attract 

Poiché si intende pianificare nuove funzionalità per il prodotto o distribuire funzionalità in anteprima, cerchiamo utenti che ci aiutino in tal senso. Gli utenti interessati possono registrarsi al gruppo di ricerca utenti tramite il collegamento di iscrizione nella nostra app.

### <a name="job-approvals-appear-on-the-home-page"></a>Approvazioni delle mansioni visualizzate nella home page

Le approvazioni sono visualizzate nella sezione **Approvazioni** del dashboard. Gli approvatori possono esaminare le relative approvazioni in **Assegnate all'utente**, in cui è visualizzato l'ID mansione, il titolo della mansione, altri approvatori e la data in cui la mansione è stata assegnata. Gli utenti che inviano una mansione per l'approvazione possono esaminare le mansioni in **Richieste dall'utente** in cui sono visualizzati gli approvatori che devono ancora approvare la mansione inviata.

## <a name="changes-in-onboard"></a>Modifiche in Onboard
Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR
Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2394.

### <a name="entity-support-for-custom-fields-in-common-data-service"></a>Supporto entità per i campi personalizzati in Common Data Service 

In questa versione, **Calendario lavorativo** e **Giorno lavorativo** ora supportano campi personalizzati in Common Data Service.

### <a name="restrict-leave-types-in-time-off-requests"></a>Limitare i tipi di congedo nelle richieste di permessi

Le organizzazioni possono offrire diversi tipi di congedo differenti ai dipendenti. Tuttavia, potrebbe non essere appropriato per i dipendenti inviare richieste di permesso per alcuni tipi di congedo. Tali tipi di congedo possono invece essere gestiti dalle risorse umane. In questa versione, è possibile configurare i tipi di congedo per i quali i dipendenti possono inviare richieste di permessi. 

## <a name="in-preview"></a>In anteprima

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Le funzionalità di anteprima vengono attivate solo nelle istanze sandbox

Quando si esegue il provisioning di una nuova istanza di Talent, è possibile specificare se il tipo di istanza è **Produzione** o **Sandbox**. Le istanze **Sandbox** consentono di testare tle nuove funzionalità prima dell'utilizzo. Tutte le istanze Talent esistenti verranno aggiornate al tipo di istanza di **produzione**. Se si desidera aggiornare una delle istanze esistenti al tipo di istanza **Sandbox**, contattare il [supporto tecnico](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) per avviare la richiesta di modifica.

Per ulteriori informazioni su come vengono pubblicate le modifiche, vedere [Eseguire il provisioning di Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Visualizzare informazioni estese per le prestazioni in Responsabile self-service

Una nuova opzione consentirà ai responsabili di visualizzare le prestazioni dei report diretti ed estesi. Attualmente, i responsabili linea possono assegnare e aggiornare obiettivi prestazionali e pubblicare nuove revisioni, cogestite dai relativi dipendenti. Inoltre, i responsabili diretti e i relativi dipendenti possono gestire e aggiornare giornali di registrazione prestazioni per garantire la corretta esecuzione del processo di valutazione delle prestazioni. Una volta questa modifica implementata, i responsabili potranno visualizzare e gestire informazioni relative alle prestazioni per i report estesi oltre che per quelli diretti. 

## <a name="coming-soon"></a>Presto disponibili

### <a name="region-support-for-canada-and-southeast-asia"></a>Supporto regionale per Canata e Asia sudorientale

Siamo lieti di annunciare che le regioni Canada e Asia sudorientale sono disponibili per Talent dal 1° agosto 2019. Con questa modifica, è possibile creare ambienti nelle regioni del Canada e asiatiche e tutti i dati in Talent verranno conservati solo all'interno di tali regioni. È possibile creare un ambiente in queste nuove regioni selezionando la posizione nella nuova finestra di dialogo Nuovo ambiente e utilizzare l'ambiente per eseguire il provisioning di Talent in LCS come descritto qui [Eseguire il provisioning di Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

La migrazione dei dati dei progetti esistenti da altre regioni verso le regioni del Canada e asiatiche non è supportata. È possibile eseguire il provisioning solo di nuovi progetti alle nuove regioni supportate.

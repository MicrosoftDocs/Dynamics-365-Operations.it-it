---
title: Novità o modifiche in Dynamics 365 for Talent (13 maggio 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 05/13/2019
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
ms.search.validFrom: 2019-05-13
ms.dyn365.ops.version: Talent
ms.openlocfilehash: ffeeb3e2f5279a84c4c060b04fe46836b778f6c5
ms.sourcegitcommit: 1bf6a8b2f872394a4f242f9ff13c67e8e1ae8f65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/03/2019
ms.locfileid: "1856450"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-may-13-2019"></a>Novità o modifiche in Dynamics 365 for Talent (13 maggio 2019)

[!include [banner](includes/banner.md)]

Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 for Talent.

## <a name="coming-soon-in-attract"></a>Funzionalità presto disponibili in Attract

### <a name="job-approvals-on-home-page"></a>Approvazioni di mansioni nella home page

Le approvazioni sono visualizzate nella sezione **Approvazioni** del dashboard. Gli approvatori possono esaminare le relative approvazioni in **Assegnate all'utente**, in cui è visualizzato l'ID mansione, il titolo, altri approvatori e la data assegnata. Gli utenti che inviano una mansione per l'approvazione possono esaminare le mansioni in **Richieste dall'utente** in cui vengono visualizzati gli approvatori che devono ancora approvare la mansione inviata.

## <a name="changes-in-onboard"></a>Modifiche in Onboard

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR

Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2297. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Microsoft Dynamics Lifecycle Services (LCS).

### <a name="indicate-instance-type-when-provisioning-talent"></a>Indicare il tipo di istanza durante il provisioning di Talent

Quando si esegue il provisioning di una nuova istanza di Talent, è possibile indicare se il tipo di istanza è **Produzione** o **Sandbox**, consentendo il test iniziale di nuove funzionalità. Tutte le istanze Talent esistenti verranno aggiornate al tipo di istanza di **produzione**. Se si desidera aggiornare una delle istanze esistenti al tipo di istanza **Sandbox**, contattare il [supporto tecnico](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) per avviare la richiesta di modifica.

### <a name="common-data-service-entity-support-for-custom-fields"></a>Support dell'entità Common Data Service per i campi personalizzati

Nella versione di questa settimana, le seguenti entità di Common Data Service ora supportano i campi personalizzati: Impiego, Frequenza calcolo benefit, Velocità calcolo benefit, Vacanze del calendario di lavoro e Tipo di identificazione.

### <a name="common-data-service-integration-page"></a>Pagina Integrazione di Common Data Service

Questa versione fornisce una nuova opzione in **Amministrazione sistema > Collegamenti > Integrazioni > Configurazione di Common Data Service**. L'opzione **Configurazione di Common Data Service** fornisce a un amministratore o un amministratore della gestione dati flessibilità e informazioni su Common Data Service. Con questa opzione, è possibile attivare o disattivare l'integrazione di Common Data Service con un'istanza di Talent e visualizzare i dettagli di sincronizzazione tra l'istanza di Talent e Common Data Service.

### <a name="import-performance-data-with-final-employee-rating-316710"></a>Importare dati sulle prestazioni con valutazione finale dei dipendenti (316710)

In questa versione, è possibile importare i dati storici della valutazione dei dipendenti. Al campo **FinalEmployeeRatingId** è ora assegnata l'autorizzazione di scrittura.

### <a name="cant-create-worker-address-in-common-data-service-and-sync-it-with-talent-317555"></a>Non è possibile creare l'indirizzo del lavoratore in Common Data Service e sincronizzarlo con Talent (317555)

Questa modifica consente di sincronizzare i dati relativi agli indirizzi creati in Common Data Service con Talent.

## <a name="in-preview"></a>In anteprima

### <a name="new-page-to-validate-position-hierarchy-data"></a>Nuova pagina per convalidare i dati della gerarchia di posizioni

Le risorse umane (HR) e gli amministratori possono convalidare la gerarchia manageriale per tutti i riferimenti circolari che potrebbero essere stati inavvertitamente importati. È possibile accedere a questa nuova pagina da **Amministrazione organizzazione > Collegamenti> Posizioni> Convalida gerarchia posizioni**.

### <a name="specify-reason-codes-on-leave-types"></a>Specificare i codici motivo per i tipi di congedo

Le organizzazioni potrebbero richiedere informazioni aggiuntive per le richieste di permesso. Ora è possibile specificare i codici motivo per i tipi di congedo e consentire ai dipendenti di selezionare un codice motivo nelle relative richieste di permesso.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Richiedere codici motivo per tipi di congedo specifici nelle richieste di permesso

Le organizzazioni potrebbero richiedere codici motivo per determinati tipi di congedo quando i dipendenti inviano richieste di permesso. Questo requisito potrebbe esistere a causa di criteri aziendali o requisiti normativi. È possibile specificare quali tipi di congedo richiedono un codice motivo ed è possibile richiedere ai dipendenti di fornire un codice motivo per il tipo di congedo nelle relative richieste di permesso.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Fornire un elenco di transazioni assenze e congedo per le Risorse umane

La possibilità di tracciare il tempo libero dei dipendenti e analizzare come tale tempo viene calcolato non solo consente alle Risorse umane di rispondere alle domande dei dipendenti, ma anche di garantire premi appropriati per i dipendenti. Ora le Risorse umane hanno una nuova visibilità sulle transazioni (concessioni, accumuli, rettifiche e richieste) in modo da poter determinare i motivi dei saldi permesso.

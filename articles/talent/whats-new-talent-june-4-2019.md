---
title: Novità e modifiche in Dynamics 365 Talent (4 giugno 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 06/04/2019
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
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 97b44ee0d985755b33971c29c1f39561c4138fad
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "2896890"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-june-4-2019"></a>Novità e modifiche in Dynamics 365 Talent (4 giugno 2019)

Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Attract.

## <a name="coming-soon-in-attract"></a>Funzionalità presto disponibili in Attract

### <a name="job-approvals-on-the-home-page"></a>Approvazioni di mansioni nella home page

Le approvazioni sono visualizzate nella sezione **Approvazioni** del dashboard. Gli approvatori possono esaminare le relative approvazioni in **Assegnate all'utente**. In questa sezione viene visualizzato l'ID della mansione, il titolo, gli approvatori e la data in cui la mansione è stata assegnata. Gli utenti che inviano una mansione per l'approvazione possono esaminare le mansioni in **Richieste dall'utente**. In questa sezione sono visualizzati gli approvatori che devono ancora approvare la mansione inviata.

## <a name="changes-in-onboard"></a>Modifiche in Onboard

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR

Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2330.

### <a name="new-page-to-validate-position-hierarchy-data"></a>Nuova pagina per convalidare i dati della gerarchia di posizioni

Le risorse umane e gli amministratori possono convalidare la gerarchia manageriale per tutti i riferimenti circolari che sono stati importati inavvertitamente. È possibile accedere a questa nuova pagina in **Amministrazione organizzazione \> Collegamenti \> Posizioni \> Convalida gerarchia posizioni**.

### <a name="specify-reason-codes-on-leave-types"></a>Specificare i codici motivo per i tipi di congedo

Le organizzazioni potrebbero richiedere informazioni aggiuntive per le richieste di permesso. Ora è possibile specificare i codici motivo per i tipi di congedo e consentire ai dipendenti di selezionare un codice motivo nelle relative richieste di permesso.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Richiedere codici motivo per tipi di congedo specifici nelle richieste di permesso

Le organizzazioni potrebbero richiedere codici motivo per determinati tipi di congedo quando i dipendenti inviano richieste di permesso. Questo requisito potrebbe esistere a causa di criteri aziendali o requisiti normativi. È possibile specificare quali tipi di congedo richiedono un codice motivo ed è possibile richiedere ai dipendenti di fornire un codice motivo per il tipo di congedo nelle relative richieste di permesso.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Fornire un elenco di transazioni assenze e congedo per le Risorse umane

La possibilità di tracciare il tempo libero dei dipendenti e analizzare come tale tempo viene calcolato non solo consente alle Risorse umane di rispondere alle domande dei dipendenti, ma anche di assicurare premi appropriati per i dipendenti. Ora le Risorse umane hanno una nuova visibilità sulle transazioni (concessioni, accumuli, rettifiche e richieste) in modo da poter determinare i motivi dei saldi permesso.

### <a name="deleting-a-record-from-talent-doesnt-remove-the-record-from-common-data-service"></a>L'eliminazione di un record da Talent non rimuove il record da Common Data Service

I record che vengono rimossi da Talent: Core HR sono ora rimossi anche da Common Data Service.

### <a name="variable-compensation-plan-valid-fromto-dates-arent-being-honored"></a>Le date di inizio e di fine valide del piano di retribuzione variabile non sono rispettate

In questa versione, non è possibile iscrivere un dipendente a un piano di retribuzione variabile se la data di inizio è antecedente alla data di inizio del piano o la data di fine è successiva alla data di fine del piano. 

### <a name="performance-review-comments-are-removed-when-users-select-cancel"></a>I commenti sulle valutazioni delle prestazioni vengono rimossi quando gli utenti selezionano Annulla

Questa versione corregge un problema in cui i commenti sulle valutazioni sono rimossi se un utente inizia a modificare un commento ma poi seleziona **Annulla**. 

## <a name="in-preview"></a>In anteprima

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Le funzionalità di anteprima vengono attivate solo nelle istanze sandbox

Quando si esegue il provisioning di una nuova istanza di Talent, è possibile specificare se il tipo di istanza è **Produzione** o **Sandbox**. Le istanze **Sandbox** consentono di testare tle nuove funzionalità prima dell'utilizzo. Tutte le istanze Talent esistenti verranno aggiornate al tipo di istanza di **produzione**. Se si desidera aggiornare una delle istanze esistenti al tipo di istanza **Sandbox**, contattare il [supporto tecnico](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) per avviare la richiesta di modifica.

Per ulteriori informazioni su come vengono pubblicate le modifiche, vedere [Eseguire il provisioning di Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="restrict-leave-types-in-time-off-requests"></a>Limitare i tipi di congedo nelle richieste di permessi

Le organizzazioni possono offrire diversi tipi di congedo differenti ai dipendenti. Tuttavia, potrebbe non essere appropriato per i dipendenti inviare richieste di permesso per alcuni tipi di congedo. Tali tipi di congedo possono invece essere gestiti dalle risorse umane. In questa versione, è possibile configurare i tipi di congedo per i quali i dipendenti possono inviare richieste di permessi. 

## <a name="coming-soon-in-core-hr"></a>Funzionalità presto disponibili in Core HR

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Visualizzare informazioni estese per le prestazioni in Responsabile self-service

Una nuova opzione consentirà ai responsabili di visualizzare le prestazioni dei report diretti ed estesi. Attualmente, i responsabili linea possono assegnare e aggiornare obiettivi prestazionali e pubblicare nuove revisioni, cogestite dai relativi dipendenti. Inoltre, i responsabili diretti e i relativi dipendenti possono gestire e aggiornare giornali di registrazione prestazioni per garantire la corretta esecuzione del processo di valutazione delle prestazioni. Una volta questa modifica implementata, i responsabili potranno visualizzare e gestire informazioni relative alle prestazioni per i report estesi oltre che per quelli diretti. 

### <a name="print-performance-reviews"></a>Stampare le valutazioni delle prestazioni

Dipendenti, responsabili e risorse umane potranno stampare la valutazione delle prestazioni di un dipendente.

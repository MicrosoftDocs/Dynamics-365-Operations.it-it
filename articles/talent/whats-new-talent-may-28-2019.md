---
title: Novità o modifiche in Dynamics 365 Talent (28 maggio 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 05/28/2019
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
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 29e941ddab1b2746ccd74d6e335fec7742d1391e
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529610"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-may-28-2019"></a>Novità o modifiche in Dynamics 365 Talent (28 maggio 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract
Questa versione include correzioni di bug minori per Dynamics 365 Talent: Attract.

## <a name="coming-soon-in-attract"></a>Funzionalità presto disponibili in Attract

### <a name="job-approvals-on-home-page"></a>Approvazioni di mansioni nella home page

Le approvazioni sono visualizzate nella sezione **Approvazioni** del dashboard. Gli approvatori possono esaminare le relative approvazioni in **Assegnate all'utente**, in cui è visualizzato l'ID mansione, il titolo, altri approvatori e la data assegnata. Gli utenti che inviano una mansione per l'approvazione possono esaminare le mansioni in **Richieste dall'utente** in cui vengono visualizzati gli approvatori che devono ancora approvare la mansione inviata.

## <a name="changes-in-onboard"></a>Modifiche in Onboard
Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR
Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2319.

### <a name="common-data-service-entity-support-for-custom-fields"></a>Support dell'entità Common Data Service per i campi personalizzati

In questa versione, le seguenti entità Common Data Service ora supportano campi personalizzati: Dettagli di tasso di calc di benefit, Riga vacanze del calendario di lavoro e Impiego.

### <a name="copy-position-now-includes-payroll-details"></a>Copia posizione ora include i dettagli delle retribuzioni
Quando si utilizza **Copia posizione** e si selezionano tutte le opzioni, le informazioni sui dettagli delle retribuzioni sono ora incluse nelle informazioni della copia. 

## <a name="in-preview-in-core-hr"></a>In anteprima di Core HR

### <a name="restrict-the-leave-types-in-time-off-requests"></a>Limitare i tipi di congedo nelle richieste di permessi

Le organizzazioni possono offrire diversi tipi di congedo differenti ai dipendenti. Alcuni di questi tipi di congedo potrebbero non essere appropriati per inviare richieste di permesso e sono invece gestiti dalle risorse umane (HR). Con questa versione, è possibile configurare i tipi di congedo per i quali i dipendenti possono inviare richieste di permessi. 

### <a name="new-page-to-validate-position-hierarchy-data"></a>Nuova pagina per convalidare i dati della gerarchia di posizioni

Le risorse umane (HR) e gli amministratori possono convalidare la gerarchia manageriale per tutti i riferimenti circolari che potrebbero essere stati importati inavvertitamente. È possibile accedere a questa nuova pagina da **Amministrazione organizzazione > Collegamenti> Posizioni> Convalida gerarchia posizioni**.

### <a name="specify-reason-codes-on-leave-types"></a>Specificare i codici motivo per i tipi di congedo

Le organizzazioni potrebbero richiedere informazioni aggiuntive per le richieste di permesso. Ora è possibile specificare i codici motivo per i tipi di congedo e consentire ai dipendenti di selezionare un codice motivo nelle relative richieste di permesso.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Richiedere codici motivo per tipi di congedo specifici nelle richieste di permesso

Le organizzazioni potrebbero richiedere codici motivo per determinati tipi di congedo quando i dipendenti inviano richieste di permesso. Questo requisito potrebbe esistere a causa di criteri aziendali o requisiti normativi. È possibile specificare quali tipi di congedo richiedono un codice motivo ed è possibile richiedere ai dipendenti di fornire un codice motivo per il tipo di congedo nelle relative richieste di permesso.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Fornire un elenco di transazioni assenze e congedo per le Risorse umane

La possibilità di tracciare il tempo libero dei dipendenti e analizzare come tale tempo viene calcolato non solo consente alle Risorse umane di rispondere alle domande dei dipendenti, ma anche di garantire premi appropriati per i dipendenti. Ora le Risorse umane hanno una nuova visibilità sulle transazioni (concessioni, accumuli, rettifiche e richieste) in modo da poter determinare i motivi dei saldi permesso.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
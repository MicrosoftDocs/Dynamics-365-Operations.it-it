---
title: Novità o modifiche in Dynamics 365 for Talent (10 settembre 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 9/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-09-10
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 0aadecd5b37759492f7895ccfda1a777793a08b3
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3006243"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-september-10-2019"></a>Novità o modifiche in Dynamics 365 for Talent (10 settembre 2019)

Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

### <a name="candidate-e-mail-login"></a>Accesso del candidato tramite posta elettronica

I candidati possono ora utilizzare qualsiasi indirizzo e-mail per creare un account e accedere a un sito di carriera Talent per fare domanda per un lavoro e cercare lo stato delle domande effettuate. Questo in aggiunta a poter già accedere al sito della carriera di Talent utilizzando l'account social o le credenziali dell'organizzazione.

### <a name="job-activation-and-posting"></a>Attivazione e registrazione del lavoro

Sono state apportate alcune modifiche all'attivazione e alla registrazione dei processi. È necessario attivare i lavori prima di pubblicarli sul sito della carriera di Talent o su qualsiasi bacheca di lavoro esterna, tra cui LinkedIn o Broadbean.

## <a name="changes-in-onboard"></a>Modifiche in Onboard

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR

Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2482. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Microsoft Dynamics Lifecycle Services (LCS).

### <a name="you-can-enable-preview-features-in-sandbox-and-trial-environments"></a>È possibile attivare le funzionalità di anteprima negli ambienti Sandbox e di prova

Quando si esegue il provisioning di una nuova istanza di Talent, è possibile specificare se il tipo di istanza è Produzione o Sandbox. Le istanze Sandbox consentono di testare tle nuove funzionalità prima dell'utilizzo. Se si desidera aggiornare una delle istanze esistenti al tipo di istanza Sandbox, contattare il supporto tecnico per avviare la richiesta di modifica.

Per ulteriori informazioni su come vengono pubblicate le modifiche, vedere [Eseguire il provisioning di Talent](./provisioning-talent.md).

### <a name="platform-update-29"></a>Update 29 della piattaforma

Per ulteriori dettagli sull'aggiornamento 29 della piattaforma, vedere [Funzionalità di anteprima nell'aggiornamento 29 della piattaforma Dynamics 365 for Finance and Operations (ottobre 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-29).

### <a name="new-job-base-entity-available-in-data-management-framework-347202"></a>Nuova entità base lavoro disponibile nel framework di gestione dati (347202)

Con questa versione, è disponibile una nuova entità javoro di base per l'importazione/esportazione dei dati. 

### <a name="worker-advanced-security-policy-incorrectly-displays-positions-in-position-hierarchy-354868"></a>I criteri di sicurezza avanzata del lavoratore visualizzano erroneamente le posizioni nella Gerarchia posizioni (354868)

Con questa versione, le posizioni non vengono più visualizzate aperte con un lavoratore "vuoto" quando gli utenti hanno accesso limitato.

### <a name="job-form-close-box-wont-close-form-in-certain-situations-342467"></a>La casella di chiusura del modulo di lavoro non chiude il modulo in determinate situazioni (342467)

Questa versione include una modifica che consente la chiusura del modulo lavoro in tutti gli scenari.

### <a name="new-case-on-employee-record-is-locked-for-human-resources-manager-role-337111"></a>Il nuovo caso nel record dipendente è bloccato per il ruolo di responsabile delle risorse umane (337111)

Con questa modifica, il modulo di gestione del caso non è più bloccato quando vi si accede dal modulo del dipendente.

### <a name="employment-end-date-always-defaults-to-235959-351492"></a>La data di fine del rapporto di lavoro è sempre predefinita su 23:59:59 (351492)

Con questa modifica, è possibile cambiare la data di assunzione in un orario diverso dalle 23:59:59 quando si termina manualmente un'occupazione.

### <a name="unable-to-set-up-expiration-date-on-an-earning-code-through-data-management-336604"></a>Impossibile impostare la data della scadenza di un codice di reddito tramite la gestione dei dati (336604)

In questa versione, è possibile impostare codici di reddito che scadono attraverso l'entità **PayrollWorkerPositionEarningCodeEntity**.

### <a name="employee-development-analytic-report-doesnt-display-data-348737"></a>Il report analitico di sviluppo dipendente non visualizza i dati (348737)

Nella versione di questa settimana, l'analisi delle competenze del dipendente è stata aggiornata per fornire report accurati.

### <a name="terms-of-employment-datetime-dont-default-to-beginning-of-day-349101"></a>La data/ora delle condizioni di impiego non si imposta automaticamente all'inizio del giorno (349101)

Con questa modifica, la data/ora di inizio ora passano automaticamente all'inizio della giornata e la data/ora di fine passano alla fine della giornata.

### <a name="changing-the-employment-end-date-on-worker-action-form-displays-an-error-354092"></a>La modifica della data di fine dell'impiego nel modulo di azione del lavoratore visualizza un errore (354092) 

Questa modifica corregge un problema relativo alla modifica della data di fine del rapporto di lavoro come parte dell'azione del lavoratore.

### <a name="applying-onboarding-checklists-across-companies-338433"></a>Applicazione di liste di controllo per l'inserimento tra le società (338433)

Questa versione ora offre la possibilità di applicare liste di controllo per i dipendenti che sono impiegati in persone giuridiche diverse dalla persona giuridica che ha effettuato l'accesso.

## <a name="in-preview"></a>In anteprima

### <a name="streamlined-employee-entry-and-navigation"></a>Inserimento e navigazione dei dipendenti semplificati

Questa funzionalità è ora disponibile negli ambienti sandbox. Per attivare questa funzionalità, passare ad **Amministrazione sistema > Collegamenti > Impostazioni > Parametri di sistema > Funzionalità di anteprima**. Selezionare **Navigazione e modulo lavoratore avanzati**. In questo modo le modifiche saranno valide per tutti gli utenti. È possibile disattivare questa opzione in qualsiasi momento.

Per ulteriori informazioni, vedere [Inserimento e navigazione dei dipendenti semplificati](./streamlined-employee-entry.md).

---
title: Novità e modifiche in Dynamics 365 Talent (16 luglio 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 07/16/2019
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
ms.search.validFrom: 2019-07-16
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6dce39bc529bf6dd6079ed900af12510c0773f9a
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "2899084"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-july-16-2019"></a>Novità e modifiche in Dynamics 365 Talent (16 luglio 2019)

Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract
Questa versione include correzioni di bug minori per Dynamics 365 Talent: Attract.

### <a name="coming-soon-in-attract"></a>Funzionalità presto disponibili in Attract
#### <a name="job-approvals-appear-on-the-home-page"></a>Approvazioni delle mansioni visualizzate nella home page

Le approvazioni sono visualizzate nella sezione **Approvazioni** del dashboard. Gli approvatori possono esaminare le relative approvazioni in **Assegnate all'utente**, in cui è visualizzato l'ID mansione, il titolo della mansione, altri approvatori e la data in cui la mansione è stata assegnata. Gli utenti che inviano una mansione per l'approvazione possono esaminare le mansioni in **Richieste dall'utente** in cui sono visualizzati gli approvatori che devono ancora approvare la mansione inviata.

## <a name="changes-in-onboard"></a>Modifiche in Onboard
Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR
Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2390.

### <a name="common-data-service-entities-that-now-support-custom-fields"></a>Entità in Common Data Service che ora supportano campi personalizzati

- BusinessProcessCalendar                     
- BusinessProcessGroupAssignment         
- BusinessProcessStage                          
- BusinessProcessTemplateHeader          
- BusinessProcessTemplateTask            
- HcmBenefitOption                              
- HcmBenefitType                                  
- HcmCompensationGrid                            
- HcmCompensationLevel                          
- HcmCompensationPayFrequency                 
- HcmCompensationReferencePointSetup        
- HcmCompensationReferencePointSetupLine 
- HcmCompensationRegion                     
- HcmCompFixedPlanTable                     
- HcmEmployment                                
- HcmEthnicOrigin                                
- HcmFixedCompensationEvent                 
- HcmJob                                           
- HcmJobFunction
- HcmJobType
- HcmLanguageCode
- HcmPayrollCalculationFrequency
- HcmPosition
- HcmPositionType
- HcmSkillType
- HcmVeteranStatus
- HcmWorkCalendarHoliday
- HcmWorkCalendarHolidayLine
- HcmWorker
- HcmWorkerPersonalDetail
- LeaveType
- OMDepartment
- OMLegalEntity
- PayCycle
- PayPeriod
- PayrollBenefitCalculationRate
- PayrollBenefitCalculationRateDetail
- PayrollEarningCode

### <a name="unable-to-see-goals-and-reviews-in-manager-self-service"></a>Impossibile vedere gli obiettivi e le revisioni in responsabile self-service

Le modifiche di questa settimana consentono di visualizzare e modificare gli obiettivi e le revisioni per responsabili di livello non direttamente superiore in Responsabile self-service.

### <a name="goal-form-cannot-be-closed-after-a-user-edits-any-goal-field"></a>Non è possibile chiudere il modulo degli obiettivi dopo che un utente modifica un campo qualsiasi degli obiettivi

Questa versione corregge un problema in cui il modulo degli obiettivi non si chiude quando si seleziona **Chiudi**.

### <a name="creating-new-goals-and-saving-displays-error"></a>La creazione di nuovi obiettivi con salvataggio visualizza un errore

Questa versione corregge un problema quando si salvano gli obiettivi in dipendente self-service e responsabile self-service.

### <a name="unable-to-add-a-field-to-position-details"></a>Impossibile aggiungere un campo nei dettagli della posizione 

Questa versione supporta i campi personalizzati nei dettagli della posizione.
 
### <a name="unable-to-set-up-expiring-date-on-the-earning-code-through-data-management"></a>Impossibile impostare la data della scadenza del codice di reddito tramite la gestione dei dati

Le modifiche consentono ora di impostare le date di scadenza sui codici di reddito nella gestione dei dati.

### <a name="new-custom-fields-dont-sync-quickly-enough"></a>I nuovi campi personalizzati non vengono sincronizzati con sufficiente rapidità

Le prestazioni della sincronizzazione dei campi personalizzati in Common Data Service è stata migliorata nella versione di questa settimana.

### <a name="entity-export-to-database-jobs-fail-with-error-message-format-of-the-initialization-string-does-not-conform-to-specification-starting-at-index-0"></a>I processi di esportazione di entità nei database non generano un messaggio di errore: "Il formato di stringa per l'inizializzazione non è conforme con le specifiche a partire dall'elemento con indice 0".

Questa versione corregge il problema dei processi batch del database che hanno esito negativo. Per aggiornare manualmente:

1. Passare a **Gestione dati**.
2. Selezionare **Configura esportazione entità in database**.
3. Immettere nuovamente la stringa di connessione al database di destinazione e selezionare **Salva**.

### <a name="smtp-email-configuration-suddenly-fails-with-error-message-the-smtp-server-requires-a-secure-connection-or-the-client-was-not-authenticated"></a>La configurazione dell'e-mail SMTP termina all'improvviso con un messaggio di errore: "Il server SMTP richiede una connessione protetta oppure il client non è stato autenticato."

Questa versione corregge la configurazione del messaggio di posta elettronica SMTP che ha un improvviso esito negativo. Per aggiornare manualmente:

1. Passare a **Amministrazione sistema**.
2. Selezionare **Parametri posta elettronica**.
3. Selezionare **Impostazioni SMTP**. 
4. Immettere di nuovo nome utente e password utilizzati per il server SMTP e selezionare **Salva**.

## <a name="in-preview"></a>In anteprima

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Le funzionalità di anteprima vengono attivate solo nelle istanze sandbox

Quando si esegue il provisioning di una nuova istanza di Talent, è possibile specificare se il tipo di istanza è **Produzione** o **Sandbox**. Le istanze **Sandbox** consentono di testare tle nuove funzionalità prima dell'utilizzo. Tutte le istanze Talent esistenti verranno aggiornate al tipo di istanza di **produzione**. Se si desidera aggiornare una delle istanze esistenti al tipo di istanza **Sandbox**, contattare il [supporto tecnico](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) per avviare la richiesta di modifica.

Per ulteriori informazioni su come vengono pubblicate le modifiche, vedere [Eseguire il provisioning di Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="restrict-leave-types-in-time-off-requests"></a>Limitare i tipi di congedo nelle richieste di permessi

Le organizzazioni possono offrire diversi tipi di congedo differenti ai dipendenti. Tuttavia, potrebbe non essere appropriato per i dipendenti inviare richieste di permesso per alcuni tipi di congedo. Tali tipi di congedo possono invece essere gestiti dalle risorse umane. In questa versione, è possibile configurare i tipi di congedo per i quali i dipendenti possono inviare richieste di permessi. 

### <a name="view-performance-information-for-direct-and-extended-reports-in-manager-self-service"></a>Visualizzare le informazioni sulle prestazioni per report diretti ed estesi in Responsabile self-service

Una nuova opzione consentirà ai responsabili di visualizzare le prestazioni dei report diretti ed estesi. Attualmente, i responsabili linea possono assegnare e aggiornare obiettivi prestazionali e pubblicare nuove revisioni. Inoltre, i responsabili diretti e i relativi dipendenti possono gestire e aggiornare giornali di registrazione prestazioni per garantire la corretta esecuzione del processo di valutazione delle prestazioni. Una volta questa modifica implementata, i responsabili potranno visualizzare e gestire informazioni relative alle prestazioni per i report estesi oltre che per quelli diretti.

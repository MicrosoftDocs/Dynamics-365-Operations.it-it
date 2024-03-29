---
title: Novità e modifiche in Dynamics 365 Human Resources (08 luglio 2020)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources all'8 luglio 2020.
author: andreabichsel
ms.date: 07/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c07646b70d07fbcd6f5aac897f79df7d159266af
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848138"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-8-2020"></a>Novità e modifiche in Dynamics 365 Human Resources (8 luglio 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Questo articolo descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources. Le modifiche si applicano alla build 8.1.3382. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in LCS per riferimento.

## <a name="database-logging"></a>Registrazione database

La registrazione del database consente di determinare quali tabelle e quali campi monitorare. Inoltre, consente di determinare gli eventi che dovrebbero attivare il rilevamento delle modifiche. Usare le funzionalità di registrazione del database per visualizzare tali modifiche nel tempo. Per ulteriori informazioni, vedi [Configurare e gestire la registrazione del database](hr-admin-database-logging.md).

## <a name="configure-the-name-of-employee-self-service"></a>Configurare il nome dell'area di lavoro Self-service dipendenti

In **Parametri Risorse umane**, è ora possibile cambiare il nome dell'area di lavoro **Self-service dipendenti** in **Self-service**. Per ulteriori informazioni, vedere [Cambiare il nome dell'area di lavoro Self-service dipendenti](hr-employee-self-service-workspace-name.md)

## <a name="benefits-management-open-enrollment-access-outside-of-period"></a>Accesso all'iscrizione aperta in Gestione benefit al di fuori del periodo di iscrizione

Questa versione corregge un bug che consentiva ai dipendenti di accedere all'iscrizione aperta dei benefit al di fuori del periodo di iscrizione o senza un evento reale. Di conseguenza, se è necessario eseguire una demo dell'iscrizione aperta in Self-service dipendenti, è necessario impostare le date di iscrizione aperta sulla data odierna o una data precedente per renderla accessibile. È possibile modificare questa impostazione in **Gestione benefit > Periodi di regole e opzioni**.

## <a name="email-employee-enrollment-confirmation"></a>Email di conferma dell'iscrizione dei dipendenti

Ora è possibile inviare e-mail ai dipendenti dopo che questi hanno completato la selezione dei benefit. È possibile inviare un messaggio predefinito o utilizzare un modello di posta elettronica dell'organizzazione. Queste impostazioni sono in **Parametri Risorse umane > Gestione benefit**.

## <a name="canceled-leave-still-appears-in-upcoming-time-off-on-people-workspace-441358"></a>Il congedo annullato appare ancora in Tempo libero imminente nell'area di lavoro Persone (441358)

Il congedo annullato non è più visualizzato come tempo libero imminente nelle schede di congedo nell'area di lavoro **Persone**.

## <a name="unable-to-use-the-department-entity-property-in-the-positionv2-entity-456486"></a>Impossibile utilizzare la proprietà dell'entità reparto nell'entità PositionV2 (456486)

Ora è possibile aggiungere un reparto senza creare una relazione duplicata.

## <a name="payrollworkerenrolledbenefitdetailentity-should-only-use-calculated-field-for-retirement-plans-459779"></a>PayrollWorkerEnrolledBenefitDetailEntity deve utilizzare il campo calcolato solo per i piani pensionistici (459779)

Quando si esporta l'entità **PayrollWorkerEnrolledBenefitDetailEntity**, l'esportazione determina se deve utilizzare un campo calcolato in base a una tabella di tariffe o utilizzare il campo **ContributionAmountCur** nella tabella di supporto. La logica utilizzata dall'entità data utilizza la tabella delle tariffe in situazioni in cui l'applicazione normalmente non l'utilizza. Questa logica fa sì che le esportazioni delle entità restituiscano un valore zero per questa colonna, poiché non esiste una tabella delle tariffe di calcolo e il prodotto non consente al cliente di specificarne una.
 
## <a name="confusing-translations-in-czech-language-in-personnel-management-and-employee-self-service-400276"></a>Traduzioni confuse in lingua ceca in Gestione dipendente e Self-service dipendenti (400276)

Questa versione corregge le traduzioni di **Directory società**, **Prossimo corso registrato**, **Processo** e **Posizione**.
 
## <a name="the-workcalendaremployment-table-doesnt-have-the-created-and-modified-system-fields-enabled-460171"></a>La tabella WorkCalendarEmployment non ha i campi di sistema creati e modificati abilitati (460171)

I campi di sistema creati e modificati sono ora abilitati nella tabella **WorkCalendarEmployment** in Risorse umane.
 
## <a name="null-reference-exception-for-hire-and-add-details-for-future-employee-455475"></a>Eccezione di riferimento null per Assumi e aggiungi dettagli per un futuro dipendente (455475)

Questa versione corregge un errore (riferimento null) nella voce di dipendente semplificata quando si assume un dipendente utilizzando l'opzione **Assumi e aggiungi dettagli**.

## <a name="changes-made-in-the-dataverse-worker-entity-dont-reflect-in-human-resources-455652"></a>Le modifiche apportate all'entità Lavoratore di Dataverse non sono riflesse in Risorse umane (455652)

Le modifiche apportate ai seguenti campi nell'entità **Lavoratore** in Dataverse ora saranno visualizzate in Risorse umane:

- **Lavora da casa**
- **Data di anzianità**
- **Data di ricorrenza annuale**
- **Data di assunzione originale**

## <a name="correct-compensation-level-doesnt-default-based-on-the-job-assigned-to-the-position-394136"></a>L'impostazione predefinita del livello di compensazione corretto non viene selezionata in base al lavoro assegnato alla posizione (394136)

Con questa modifica, il livello di compensazione corretto viene impostato automaticamente in base ai record **Data valida** per **Dettagli posizioni** e **Data d'inizio** dell'**Assegnazione del piano di compensazione**.

## <a name="in-preview"></a>In anteprima

## <a name="mandatory-fields"></a>Campi obbligatori 

Ora puoi rendere obbligatori i campi utilizzando le funzionalità di personalizzazione di Human Resources. Questa funzionalità richiede **Visualizzazioni salvate**.

## <a name="human-resources-application-in-teams"></a>Applicazione Human Resources in Teams

I dipendenti possono visualizzare i congedi e richiederli in Microsoft Teams. Possono interagire con un bot per creare richieste di congedo. Per ulteriori informazioni, vedere [App Human Resources in Teams](./hr-admin-teams-leave-app.md). 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Entità Data Management Framework per la gestione di benefit
 
Le entità di gestione di benefit sono in fase di rilascio. Le entità DMF consentono di importare ed esportare dati per configurare facilmente la gestione dei benefit. Sarà disponibile un modello di gestione dei benefit per spostare i dati. Il modello esporta e importa i dati in modo in modo sequenziale per rispettare le dipendenze dei dati.

## <a name="buy-and-sell-leave"></a>Acquista e vendi congedo 

Alcune organizzazioni offrono un benefit che consente ai dipendenti di acquistare o vendere congedi. Questo processo è spesso gestito manualmente. Questa funzione automatizza la gestione dei criteri e delle richieste per il dipartimento Risorse umane. Semplifica il processo di gestione delle ferie e aiuta a eliminare gli errori. Per ulteriori informazioni, vedere:

- [Gestire i criteri di acquisto e vendita congedo](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Acquista e vendi congedo](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a>Lascia l'attribuzione per una singola azienda o un singolo piano

I clienti possono elaborare attribuzioni per una singola azienda o un singolo piano di ferie e assenze. Questa capacità fornisce chiarezza per il processo di maturazione per i clienti con diversi anni di ferie o politiche di maturazione delle ferie. Per ulteriori informazioni, vedi [Accumulare congedi per società o per piano di congedo](hr-leave-and-absence-accrue.md).

## <a name="add-attachments-to-time-off-requests"></a>Aggiungi allegati alle richieste di ferie

La possibilità di aggiungere allegati alle richieste di ferie approvate è fondamentale nell'attuale ambiente COVID-19. I dipendenti possono ora aggiungere questi allegati. Hanno anche maggiori informazioni dettagliate su come vengono effettuati gli aggiornamenti per lasciare le richieste. Per ulteriori informazioni, vedi [Aggiungi un allegato a una richiesta esistente](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).

## <a name="add-reason-code-to-accrual-suspensions"></a>Aggiungi il codice motivo alle sospensioni degli accumuli 

Codici motivo sono stati aggiunti alla sospensione degli accumuli.

## <a name="carry-forward-rules"></a>Regole di riporto 

È possibile specificare un tipo di congedo riporto per i saldi del riporto in cui vengono trasferiti le rettifiche di riporto. Ad esempio, se un dipendente riporta 10 giorni, è possibile scegliere un tipo di congedo diverso per quei 10 giorni. Per ulteriori informazioni, vedere [Configurare i tipi di congedo e assenza](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types"></a>Sospendi l'accumulo dei congedi per determinati tipi di congedo

Puoi creare una regola per sospendere gli accumuli dei congedi per i dipendenti con richieste di congedo inserite per congedi non retribuiti. Il congedo non retribuito può essere un tipo, ma non è necessario che lo sia. È possibile sospendere qualsiasi congedo in base a un altro tipo di congedo.

## <a name="dmf-entity-available-for-accrual-suspensions"></a>Entità DMF disponibile per le sospensioni degli accumuli 

Un'entità DMF è ora disponibile per le sospensioni degli accumuli.

## <a name="coming-soon"></a>Presto disponibili

## <a name="checklist-entities-included-in-dataverse"></a>Elenco di controllo entità incluso in Dataverse

Le entità dell'elenco di controllo per i processi di onboarding, offboarding, trasferimenti e aziendali saranno presto disponibili in Dataverse.

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
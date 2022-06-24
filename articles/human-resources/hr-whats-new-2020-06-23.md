---
title: Novità e modifiche in Dynamics 365 Human Resources (25 giugno 2020)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 23 giugno 2020.
author: andreabichsel
ms.date: 06/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7fe8b685a2b492fe5ad23b410f6a99d81991e98a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904103"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-23-2020"></a>Novità e modifiche in Dynamics 365 Human Resources (23 giugno 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Questo articolo descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources. Le modifiche si applicano alla build 8.1.3347. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in LCS per riferimento.

## <a name="when-an-enrollment-is-expired-for-a-terminated-employee-the-leave-type-balance-and-amount-are-all-cleared-in-the-leave-enrollment-form-444867"></a>Alla scadenza di un'iscrizione per un dipendente licenziato, il tipo di congedo, il saldo e l'importo vengono cancellati nel modulo di iscrizione congedo (444867)

I valori in **Tipo di congedo**, **Saldo** e **Importo** vengono ora mantenuti anziché cancellati dopo aver effettuato questa selezione.

## <a name="incorrect-forecasted-balance-when-new-feature-leave-accrual-for-a-single-company-or-a-single-plan-is-enabled-456553"></a>Saldo previsto errato quando è abilitata la nuova funzionalità (accumulo congedo per una singola società o un singolo piano) (456553)

Il saldo previsto corretto viene ora visualizzato quanto l'accumulo congedo per una singola società o un singolo piano è stato abilitato.

## <a name="entities-with-relations-that-result-in-duplicate-navigation-properties-456486"></a>Entità con relazioni che generano proprietà di navigazione duplicate (456486)

Questa versione corregge un problema con le proprietà di navigazione (relazione) di più entità. Vengono rilevate relazioni duplicate. Questi scenari sono stati tutti corretti.
 
## <a name="cross-company-comments-on-performance-review-455536"></a>Commenti interaziendali sulla revisione delle prestazioni (455536)

I commenti interaziendali sono ora visibili sulle revisioni delle prestazioni con questa correzione. Questa modifica corregge la visualizzazione dei commenti dei revisori inseriti in diverse società per la stessa revisione delle prestazioni.
 
## <a name="inconsistency-in-showing-compensation-management-data-432562"></a>Incoerenza nella visualizzazione dei dati di gestione della retribuzione (432562)

Una visualizzazione coerente dei dati di retribuzione è ora mantenuta in Responsabile self-service. A seconda di come passi **Dettagli retribuzione** del lavoratore, i dati di retribuzione ora vengono visualizzati in modo coerente per i responsabili.
 
## <a name="fixed-compensation-plans-effective-date-defaults-to-todays-date-411994"></a>La data effettiva del piano di retribuzione è impostata in modo predefinito sulla data odierna (411994)

La data di inizio della retribuzione è basata basa ora sulla data di inizio della posizione assegnata al dipendente.

## <a name="leave-and-absence-form-enable-half-day-definition-is-disabled-when-form-opens-452607"></a>L'opzione Abilita la definizione di mezza giornata del modulo di congedo e assenza è disabilitata all'apertura del modulo (452607)

Con questa modifica, **Abilita la definizione di mezza giornata** sarà abilitata fino a quando non saranno presenti nuove transazioni di congedo. 

## <a name="unable-to-publish-to-hcmdiscussionentity-via-excel-totalratingscore-field-error-453899"></a>Impossibile pubblicare su HcmDiscussionEntity tramite Excel; errore del campo TotalRatingScore (453899)

Ora puoi aggiornare il campo **TotalRatingScore** utilizzando **HCMDiscussionEntity** nella finestra di progettazione delle cartelle di lavoro di Excel.

## <a name="in-preview"></a>In anteprima

## <a name="database-logging"></a>Registrazione database

La registrazione del database consente di determinare quali tabelle e quali campi monitorare. Inoltre, consente di determinare gli eventi che dovrebbero attivare il rilevamento delle modifiche. Usare le funzionalità di registrazione del database per visualizzare tali modifiche nel tempo. Per ulteriori informazioni, vedi [Configurare e gestire la registrazione del database](hr-admin-database-logging.md).

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

I clienti possono elaborare attribuzioni per una singola azienda o un singolo piano di ferie e assenze. Questa capacità fornisce chiarezza nel processo di maturazione per i clienti con diversi anni di ferie o politiche di maturazione delle ferie. Per ulteriori informazioni, vedi [Accumulare congedi per società o per piano di congedo](hr-leave-and-absence-accrue.md).

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

## <a name="configure-the-name-of-employee-self-service"></a>Configurare il nome del self-service dipendenti

Una nuova opzione sarà disponibile nei **parametri Risorse umane** per aggiornare il nome dell'area di lavoro Self-service dipendenti in Self-service.

## <a name="checklist-entities-included-in-dataverse"></a>Elenco di controllo entità incluso in Dataverse

Le entità dell'elenco di controllo per i processi di onboarding, offboarding, trasferimenti e aziendali saranno presto disponibili in Dataverse.

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
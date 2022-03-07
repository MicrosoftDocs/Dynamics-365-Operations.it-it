---
title: Novità e modifiche in Dynamics 365 Human Resources (23 luglio 2020)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 23 luglio 2020.
author: andreabichsel
ms.date: 07/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-07-23
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 615d18865be20bfdce76d1f39ea73b220c171a8794c01b1ddfe11496fc2a658b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6761904"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-23-2020"></a>Novità e modifiche in Dynamics 365 Human Resources (23 luglio 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources. Le modifiche si applicano alla build 8.1.3416. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in LCS per riferimento.

## <a name="deleting-financial-dimensions-on-a-position-doesnt-work-as-expected-445476"></a>L'eliminazione di dimensioni finanziarie in una posizione non funziona come previsto (445476)

La rimozione di dimensioni da una posizione ora rimuove quelle stesse posizioni da Dataverse.

## <a name="positions-not-in-hierarchy-show-inactive-positions-397257"></a>Le posizioni non in gerarchia mostrano posizioni inattive (397257)

Le posizioni che sono inattive (hanno una durata scaduta) non vengono più visualizzate nella gerarchia delle posizioni come **Posizioni non in gerarchia**. 

## <a name="validation-occurring-between-leaveenrollmententity-and-hcmworkerentity-on-data-management-framework-dmf-import-causes-slow-data-loads-442324"></a>La convalida che si verifica tra LeaveEnrollmentEntity e HcmWorkerEntity sull'importazione DMF (Data Management Framework) causa un caricamento dei dati lento (442324)

Le modifiche in questa versione aumentano le prestazioni di **LeaveEnrollmentEntity**.

## <a name="unable-to-personalize-in-organization-administration-447490"></a>Impossibile personalizzare nell'amministrazione dell'organizzazione (447490)

Con questa modifica, ora è possibile personalizzare i collegamenti in **Amministrazione organizzazione**.

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

## <a name="platform-changes"></a>Modifiche della piattaforma

Platform Update 10.0.12 (36)

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
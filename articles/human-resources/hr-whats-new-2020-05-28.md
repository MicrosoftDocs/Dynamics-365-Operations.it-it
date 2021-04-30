---
title: Novità o modifiche in Dynamics 365 Human Resources (28 maggio 2020)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 28 maggio 2020.
author: andreabichsel
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 79026c6047f3a10366ef3b22d74caee13b371b66
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891963"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-28-2020"></a>Novità o modifiche in Dynamics 365 Human Resources (28 maggio 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources. Le modifiche si applicano alla build 8.1.3287. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in LCS per riferimento.

## <a name="leaverequest-entity-doesnt-work-when-you-enable-multiple-types-per-leave-plan-447498"></a>L'entità LeaveRequest non funziona quando si abilitano più tipi per piano di congedo (447498)

Con questa modifica, **LeaveEnrollmentV2Entity** è ora disponibile per correggere l'errore che si verifica quando si abilitano più tipi di congedo.

## <a name="batch-contention-reduction-feature-preview-446619"></a>Funzionalità di riduzione di conflitti nei batch (anteprima) (446619)

Quando si abilita questa funzione, è possibile che si abbia una riduzione nel blocco delle tabelle di framework dei batch durante la selezione di attività e il completamento di processi.

## <a name="updateconflict-while-saving-worker-prevents-editing-a-record-in-people-427915"></a>L'utilizzo di UpdateConflict durante il salvataggio del lavoratore impedisce la modifica di un record in Persone (427915)

Questa modifica corregge un errore durante l'aggiunta di un nuovo lavoratore, l'aggiornamento delle informazioni relative all'indirizzo e la modifica della lingua preferita. In questo scenario, viene visualizzato un errore indicante che il record non è stato aggiornato. 

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-to-resubmit-425407"></a>Impossibile aggiungere un allegato a una richiesta di congedo approvata (425407)

Questa modifica ora consente di aggiungere allegati alle richieste di congedo approvate.

## <a name="user-can-enter-compensation-for-an-employee-in-a-different-legal-entity-form-409529"></a>L'utente può inserire una retribuzione per un dipendente in un modulo persona giuridica differente (409529)

Questa modifica disabilita le opzioni di retribuzione per impedire l'immissione accidentale di record di retribuzione per la persona giuridica errata.

## <a name="error-when-you-transfer-an-employee-and-the-worker-position-assignment-date-is-before-the-position-duration-429402"></a>Errore durante il trasferimento di un dipendente e la data di assegnazione della posizione del lavoratore è precedente alla durata della posizione (429402)

I messaggi di errore durante il trasferimento di un dipendente in questo scenario sono stati aggiornati per descrivere meglio le modifiche necessarie per correggere il problema.

## <a name="attachments-capabilities-in-employee-self-service-benefits-enrollment"></a>Funzionalità relative agli allegati nell'iscrizione ai benefit in Self-service dipendenti
 
Ora è possibile aggiungere allegati durante il processo di iscrizione ai benefit per ciascun piano a cui si iscrive il dipendente. È quindi possibile visualizzare gli allegati nel modulo **Benefit a cui è iscritto il lavoratore**.

## <a name="in-preview"></a>In anteprima

## <a name="human-resources-application-in-teams"></a>Applicazione Human Resources in Teams

I dipendenti possono visualizzare i congedi e richiederli in Microsoft Teams. Possono interagire con un bot per creare richieste di congedo. Per ulteriori informazioni, vedere [App Human Resources in Teams](./hr-admin-teams-leave-app.md). 

## <a name="leave-suspension"></a>Sospensione del congedo

In Human Resources è possibile sospendere le ferie e le assenze per un dipendente. La sospensione del congedo e interrompe la maturazione delle ferie per i tipi di congedi selezionati. Se la sospensione si verifica dopo l'elaborazione della maturazione, la sospensione delle ferie crea una rettifica proporzionale del saldo delle ferie del dipendente. Per ulteriori informazioni, vedere [Sospendere il congedo](hr-leave-and-absence-suspend-leave.md).

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a>Aggiornamento dell'esperienza utente per indicare che l'accumulo è sospeso (429550)

L'esperienza utente ora indica che l'accumulo è stato sospeso per un piano.

## <a name="coming-soon"></a>Presto disponibili

## <a name="database-logging-in-preview-in-june"></a>Registrazione di database (in anteprima a giugno)

La funzione di registrazione di database consente di determinare quale tabella e quali campi devono essere monitorati. Inoltre, consente di determinare gli eventi che dovrebbero attivare il rilevamento delle modifiche. Sono disponibili funzionalità di richiesta di informazioni per vedere queste modifiche nel tempo.

## <a name="buy-and-sell-leave-in-preview-june-1"></a>Acquisto e vendita di congedi (in anteprima il 1 giugno)

Alcune organizzazioni offrono un benefit che consente ai dipendenti di acquistare o vendere congedi. Questo processo è spesso gestito manualmente. Questa funzionalità offre un modo più automatizzato di gestire i criteri e le richieste per il dipartimento Risorse umane e semplifica il processo di gestione dei congedi eliminando gli errori. Per ulteriori informazioni, vedere:

- [Gestire i criteri di acquisto e vendita congedo](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Acquista e vendi congedo](hr-employee-self-service-buy-sell-leave.md)

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Entità Data Management Framework per la gestione di benefit
 
Le entità di gestione di benefit sono in fase di rilascio. Le entità Data Management Framework consentono di importare ed esportare dati per configurare facilmente la gestione dei benefit. Sarà inoltre disponibile un modello di gestione dei benefit per spostare i dati. Il modello esporta e importa i dati in modo sequenziale per rispettare le dipendenze dei dati.

## <a name="add-reason-code-to-accrual-suspensions-june-1"></a>Aggiunta di codici motivo alle sospensioni degli accumuli (1 giugno)

Codici motivo sono stati aggiunti alla sospensione degli accumuli.

## <a name="carry-forward-rules-june-1"></a>Regole di riporto (1 giugno)

È possibile specificare un tipo di congedo riporto per i saldi del riporto in cui vengono trasferiti le rettifiche di riporto. Ad esempio, se un dipendente riporta 10 giorni, è possibile scegliere un tipo di congedo diverso per quei 10 giorni. Per ulteriori informazioni, vedere [Configurare i tipi di congedo e assenza](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types-june-1"></a>Sospensione dell'accumulo dei congedi per determinati tipi di congedo (1 giugno)

In questa versione le risorse umane possono creare una regola per sospendere gli accumuli dei congedi per i dipendenti con richieste di congedo inserite per congedi non retribuiti. Il congedo non retribuito può essere un tipo, ma non è necessario che lo sia. È possibile sospendere qualsiasi congedo in base a un altro tipo di congedo.

## <a name="dmf-entity-available-for-accrual-suspensions-june-1"></a>Entità DMF disponibile per le sospensioni degli accumuli (1 giugno)

Un'entità DMF è ora disponibile per le sospensioni degli accumuli.

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
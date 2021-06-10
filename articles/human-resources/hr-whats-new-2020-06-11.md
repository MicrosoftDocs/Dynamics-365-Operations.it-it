---
title: Novità e modifiche in Dynamics 365 Human Resources (11 giugno 2020)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources all'11 giugno 2020.
author: andreabichsel
ms.date: 06/16/2020
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
ms.search.validFrom: 2020-06-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e6b0bb1c6d00cdd816534caddd83a71f2f0a3cc3
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054310"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-11-2020"></a>Novità e modifiche in Dynamics 365 Human Resources (11 giugno 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources. Le modifiche si applicano alla build 8.1.3316. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in LCS per riferimento.

## <a name="streamlined-employee-form-sometimes-causes-child-form-close-x-buttons-to-stop-working-442369"></a>Il modulo semplificato per i dipendenti a volte interrompe il funzionamento dei pulsanti di chiusura (X) del modulo figlio (442369)

Quando il nuovo modulo **Lavoratore** è stato abilitato, il pulsante di chiusura (**X**) occasionalmente non funzionava sui moduli figlio. Questo problema era intermittente. Puoi chiudere il modulo dopo essere uscito e tornare in un secondo momento. Ad esempio, puoi selezionare una voce di menu a sinistra e tornare indietro al modulo **Lavoratore**, quindi chiudilo. Questa versione risolverà questo problema. 

## <a name="the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-a-parent-relationship-type"></a>L'entità del contatto personale del lavoratore non esporta i contatti personali con un tipo di relazione principale

Con questa versione, l'entità **Contatto personale del lavoratore** esporta tutti i tipi di relazione.

## <a name="the-hcmpositionworkerassignmentv2entity-should-be-part-of-the-ceridian-payroll-integration-package-by-default-448506"></a>HcmPositionWorkerAssignmentV2Entity dovrebbe essere parte del pacchetto di integrazione delle buste paga di Ceridian per impostazione predefinita (448506)

Con questa modifica, **HcmPositionWorkerAssignmentV2Entity** è incluso nel pacchetto di integrazione delle buste paga di Ceridian.

## <a name="in-preview"></a>In anteprima

## <a name="database-logging"></a>Registrazione database

La funzione di registrazione del database consente di determinare quali tabelle e quali campi monitorare. Inoltre, consente di determinare gli eventi che dovrebbero attivare il rilevamento delle modifiche. Usare le funzionalità di registrazione del database per visualizzare tali modifiche nel tempo. Per ulteriori informazioni, vedi [Configurare e gestire la registrazione del database](hr-admin-database-logging.md).

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

## <a name="new-platform-capabilities"></a>Nuove funzionalità della piattaforma 

Sarai in grado di rendere i campi obbligatori utilizzando la personalizzazione. Questa funzione ti richiederà di abilitare **Visualizzazioni salvate**.

## <a name="configure-the-name-of-employee-self-service"></a>Configurare il nome del self-service dipendenti

Una nuova opzione sarà disponibile nei parametri Risorse umane per aggiornare il nome dell'area di lavoro Self-service dipendenti in Self-service. 

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
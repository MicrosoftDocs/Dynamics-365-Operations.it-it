---
title: Novità e modifiche in Dynamics 365 Human Resources (06 agosto 2020)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 6 agosto 2020.
author: andreabichsel
manager: tfehr
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-08-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 235af2d4d10687e9d7d7676c29c95428eab99b0a
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467725"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-06-2020"></a>Novità e modifiche in Dynamics 365 Human Resources (06 agosto 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources. Le modifiche si applicano alla build 8.1.3444. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in LCS per riferimento.

## <a name="platform-update-1001236-is-now-available"></a>L'aggiornamento 10.0.12(36) della piattaforma è ora disponibile

Per ulteriori informazioni, vedi [Aggiornamenti della piattaforma per la versione 10.0.12 delle app Finance and Operations (agosto 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-10-0-12).

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Entità Data Management Framework per la gestione di benefit
 
Le entità di gestione di benefit sono in fase di rilascio. Le entità DMF consentono di importare ed esportare dati per configurare facilmente la gestione dei benefit. Sarà disponibile un modello di gestione dei benefit per spostare i dati. Il modello esporta e importa i dati in modo in modo sequenziale per rispettare le dipendenze dei dati. Per ulteriori informazioni, vedere:

- [Supporto dell'entità DMF](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/dmf-entity-support) nel piano della prima ondata di rilascio di Dynamics 365 2020
- [Panoramica della gestione dati](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities-data-packages)


## <a name="claire-creates-a-workflow-for-buying-and-selling-leave-requests-446557"></a>Claire crea un flusso di lavoro per l'acquisto e la vendita di richieste di congedo (446557)

Per ulteriori informazioni, vedere:

- [Consentire ai dipendenti di acquistare e vendere congedi](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/allow-employees-buy-sell-leave) nel piano della seconda ondata di rilascio di Dynamics 365 2020
- [Gestire i criteri di acquisto e vendita congedo](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-manage-buy-and-sell-leave-policies)
- [Acquista e vendi congedo](https://docs.microsoft.com/dynamics365/human-resources/hr-employee-self-service-buy-sell-leave)


## <a name="worker-postal-addresses-v2-entity-has-access-across-legal-entities-with-restricted-access-459126"></a>L'entità V2 degli indirizzi postali dei lavoratori ha accesso a tutte le persone giuridiche con accesso limitato (459126)

Con questa modifica, l'entità **Indirizzo postale del lavoratore V2** eseguirà la limitazione in base all'accesso della persona giuridica concesso all'utente.

## <a name="workflow-email-hyperlink-fails-to-open-relevant-reviews-437398"></a>Il collegamento ipertestuale nell'e-mail del flusso di lavoro non riesce ad aprire le revisioni pertinenti (437398)

Quando si utilizza il segnaposto per aprire una revisione delle prestazioni nel flusso di lavoro di revisione, il collegamento ipertestuale generato nell'e-mail ora apre il record selezionato.

## <a name="new-entities-for-buying-and-selling-leave-473180"></a>Nuove entità per l'acquisto e la vendita di congedi (473180)

Le entità del framework di gestione dei dati sono ora disponibili per l'acquisto e la vendita di congedi. Per ulteriori informazioni, vedere [Panoramica della gestione dati](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities-data-packages).

## <a name="when-viewing-record-information-and-using-advanced-filters-a-user-could-gain-access-to-other-employees-records-472490"></a>Durante la visualizzazione delle informazioni sui record e l'utilizzo di filtri avanzati, un utente potrebbe ottenere l'accesso ai record di altri dipendenti (472490)

Con questa modifica, gli utenti di Self-service dipendenti possono accedere ai propri record solo durante l'utilizzo di un dipendente self service. La visualizzazione delle informazioni sui record durante la modifica dell'opzione di filtro non espone più dati aggiuntivi.

## <a name="personnel-management-analytics-include-exited-worker-records-382893"></a>L'analisi della gestione del personale include i record dei lavoratori che hanno lasciato la società (382893)

Con questa versione, l'analisi della gestione del personale ora include solo i lavoratori attivi. 
 
## <a name="unable-to-process-a-merit-increase-for-an-employee-473125"></a>Impossibile elaborare un aumento di merito per un dipendente (473125)

Questa modifica consente di inserire aumenti di merito quando si modifica la data di validità del nuovo aumento di merito.

## <a name="review-workflow-can-be-started-more-than-once-467541"></a>Il flusso di lavoro di revisione può essere avviato più di una volta (467541)

Con questa modifica, è possibile avviare il flusso di lavoro di revisione delle prestazioni solo una volta. Lo stato del responsabile non mostra più l'opzione per iniziare la revisione.

## <a name="leave-request-work-flow-ends-in-error-when-canceling-an-approved-leave-request-472063"></a>Il flusso di lavoro della richiesta di congedo termina con un errore quando si annulla una richiesta di congedo approvata (472063)

In questa versione, quando si annulla una richiesta di congedo approvata, lo stato della richiesta non rimane più approvato e il flusso di lavoro continuerà.

## <a name="system-suggests-exited-workers-when-creating-a-new-review-form-the-template-460624"></a>Il sistema suggerisce lavoratori che hanno lasciato la società quando si crea una nuova revisione dal modello (460624)

Con questa modifica, i lavoratori che hanno lasciato la società sono più disponibili durante la creazione di nuove revisioni da un modello. Non è possibile creare recensioni per i dipendenti che non rientrano nelle date del loro impiego.

## <a name="position-hierarchy-circular-reference-detection-415879"></a>Rilevamento del riferimento circolare della gerarchia di posizione (415879)

Con questa modifica, il rilevamento del riferimento circolare della gerarchia di posizione è limitato a un singolo punto nel tempo. È possibile eseguire il rilevamento dei riferimenti circolari per date diverse per verificare che la struttura dei rapporti non abbia riferimenti circolari.

## <a name="buy-and-sell-leave"></a>Acquista e vendi congedo 

Alcune organizzazioni offrono un benefit che consente ai dipendenti di acquistare o vendere congedi. Questo processo è spesso gestito manualmente. Questa funzione automatizza la gestione dei criteri e delle richieste per il dipartimento Risorse umane. Semplifica il processo di gestione delle ferie e aiuta a eliminare gli errori. Per ulteriori informazioni, vedere:

- [Consentire ai dipendenti di acquistare e vendere congedi](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/allow-employees-buy-sell-leave) nel piano della seconda ondata di rilascio di Dynamics 365 2020
- [Gestire i criteri di acquisto e vendita congedo](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-manage-buy-and-sell-leave-policies)
- [Acquista e vendi congedo](https://docs.microsoft.com/dynamics365/human-resources/hr-employee-self-service-buy-sell-leave)

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

## <a name="in-preview"></a>In anteprima

### <a name="mandatory-fields"></a>Campi obbligatori

È ora possibile rendere obbligatori i campi utilizzando le funzionalità di personalizzazione di Human Resources. Questa funzionalità richiede **Visualizzazioni salvate**. Per ulteriori informazioni sulle visualizzazioni salvate, vedere:

- [Visualizzazioni salvate - disponibilità generale](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability) nel piano della seconda ondata di rilascio di Dynamics 365 2020
- [Creare moduli che utilizzano interamente visualizzazioni salvate](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/user-interface/understanding-saved-views)

### <a name="human-resources-application-in-teams"></a>Applicazione Human Resources in Teams

I dipendenti possono visualizzare i congedi e richiederli in Microsoft Teams. Possono interagire con un bot per creare richieste di congedo. Per ulteriori informazioni, vedere:

- [Esperienza di congedo e assenza dei dipendenti in Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) nel piano della prima ondata di rilascio di Dynamics 365 2020
- [App Human Resources in Teams](https://go.microsoft.com/fwlink/?linkid=2127841)

### <a name="dmf-entity-available-for-accrual-suspensions"></a>Entità DMF disponibile per le sospensioni degli accumuli

Un'entità DMF è ora disponibile per le sospensioni degli accumuli.

## <a name="coming-soon"></a>Presto disponibili

## <a name="checklist-entities-included-in-dataverse"></a>Elenco di controllo entità incluso in Dataverse

Le entità dell'elenco di controllo per i processi di onboarding, offboarding, trasferimenti e aziendali saranno presto disponibili in Dataverse.

## <a name="known-issues"></a>Problemi noti

L'area di lavoro **Gestione funzionalità** potrebbe visualizzare funzioni disabilitate come funzioni di anteprima quando sono generalmente disponibili. Di seguito è riportato un elenco di funzionalità generalmente disponibili che mostrano uno stato errato. 

1.  Gestione benefit
2.  Gestione casi
3.  Registrazione database (controllo)
4.  Accumulo per congedo di una singola società o un singolo piano
5.  Sospensione accumuli per congedo e assenza
6.  Codice motivo rettifica saldo e commento
7.  Acquista e vendi congedo
8.  Calendario di congedi e assenze
9.  Regole di riporto per congedo
10. Controllo accumulo per congedo
11. Eliminazione accumuli per congedo
12. Arrotondamento accumulo per congedo
13. Configura più tipi di congedo in un piano di congedo singolo
14. Aggiornamento del permesso migliorato
15. Utilizza l'equivalenza a tempo pieno del dipendente per gli accumuli
16. Visualizzazione retribuzione interaziendale
17. Stampare le valutazioni delle prestazioni
18. Correzioni giorni festivi accumulo per congedo

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
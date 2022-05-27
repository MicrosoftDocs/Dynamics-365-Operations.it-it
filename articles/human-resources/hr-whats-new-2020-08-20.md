---
title: Novità e modifiche in Dynamics 365 Human Resources (20 agosto 2020)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 20 agosto 2020.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b6a3953c0c8474ae67667176c21d065c6b94c6ab
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8688405"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-20-2020"></a>Novità e modifiche in Dynamics 365 Human Resources (20 agosto 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources. Le modifiche si applicano alla build 8.1.3478. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Lifecycle Services (LCS) per riferimento.

## <a name="show-upcoming-and-pending-leave-of-absence-information-to-cards-in-people-workspace"></a>Mostrare le informazioni sui congedi imminenti e in sospeso nelle schede dell'area di lavoro Persone

Le opzioni di richiesta di congedo in sospeso e imminente sono ora disponibili nelle schede Congedo e assenza nell'area di lavoro **Persone**.

## <a name="private-field-isnt-yes-by-default-for-employee-role-in-employee-self-service-477106"></a>Il campo privato non è Sì per impostazione predefinita per il ruolo dipendente in Self-service dipendenti (477106)

Il campo **Privato** ora è impostato su **Sì** quando i dipendenti aggiungono nuovi record di indirizzi tramite la pagina **Informazione personale** in Self-service dipendenti. 

## <a name="candidates-to-hire-fasttab-in-personnel-management-shows-an-incorrect-count-of-candidates-470110"></a>La scheda dettaglio Candidati da assumere nella gestione del personale mostra un conteggio errato dei candidati (470110)

La pagina **Gestione personale** ora mostra accuratamente il numero di candidati da assumere. 

## <a name="cant-enter-sickness-for-terminated-employee-when-accrual-is-set-to-zero-446195"></a>Impossibile inserire la malattia per il dipendente licenziato quando l'accumulo è impostato su zero (446195)

Le transazioni di congedo sono ora consentite per i dipendenti licenziati in futuro e l'accumulo è impostato su zero. Le transazioni di congedo possono essere inserite fino alla data di licenziamento del dipendente. 

## <a name="adding-custom-fields-to-the-new-worker-form-disables-the-fields-in-the-action-pane-for-manage-leave-473314"></a>L'aggiunta di campi personalizzati al nuovo modulo Lavoratore disabilita i campi nel riquadro azioni per Gestisci congedo (473314)

Le opzioni del riquadro azioni sul nuovo modulo **Lavoratore** in **Gestisci congedo** non saranno più disabilitate se i campi personalizzati vengono aggiunti al nuovo modulo **Lavoratore**.

## <a name="making-the-leave-comment-field-mandatory-allows-a-leave-request-to-be-submitted-when-no-comment-is-entered-473543"></a>Rendere obbligatorio il campo per il commento consente di inviare una richiesta di congedo quando non viene inserito alcun commento (473543)

I campi dei commenti ora possono essere obbligatori e le richieste di congedo rispettano questa impostazione. I campi obbligatori sono una funzione di anteprima.

### <a name="dmf-entity-available-for-accrual-suspensions"></a>Entità DMF disponibile per le sospensioni degli accumuli

Un'entità DMF è ora disponibile per le sospensioni degli accumuli.

## <a name="in-preview"></a>In anteprima

### <a name="mandatory-fields"></a>Campi obbligatori

È ora possibile rendere obbligatori i campi utilizzando le funzionalità di personalizzazione di Human Resources. Questa funzionalità richiede **Visualizzazioni salvate**. Per ulteriori informazioni sulle visualizzazioni salvate, vedere:

- [Visualizzazioni salvate - disponibilità generale](/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability) nel piano della seconda ondata di rilascio di Dynamics 365 2020
- [Creare moduli che utilizzano interamente visualizzazioni salvate](../fin-ops-core/dev-itpro/user-interface/understanding-saved-views.md)

### <a name="human-resources-application-in-teams"></a>Applicazione Human Resources in Teams

I dipendenti possono visualizzare i congedi e richiederli in Microsoft Teams. Possono interagire con un bot per creare richieste di congedo. Per ulteriori informazioni, vedere:

- [Esperienza di congedo e assenza dei dipendenti in Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) nel piano della prima ondata di rilascio di Dynamics 365 2020
- [App Human Resources in Teams](./hr-admin-teams-leave-app.md)

## <a name="coming-soon"></a>Presto disponibili

### <a name="human-resources-app-in-teams-preview-features"></a>Funzioni di anteprima dell'app Human Resources in Teams
 
-  **Notifiche**: i mittenti e gli approvatori delle richieste di permesso verranno informati nell'app Human Resources in Teams. Gli approvatori potranno approvare o rifiutare le richieste di permesso e i mittenti riceveranno una notifica se la richiesta è stata approvata o rifiutata.
 
- **Calendario permessi del responsabile**: i responsabili potranno vedere i permessi approvati e in sospeso per i loro diretti subalterni in una visualizzazione calendario. Questa visualizzazione fornisce una facile comprensione di quando i membri del team non sono al lavoro.

### <a name="checklist-entities-included-in-dataverse"></a>Elenco di controllo entità incluso in Dataverse

Le entità dell'elenco di controllo per i processi di onboarding, offboarding, trasferimenti e aziendali saranno presto disponibili in Dataverse.

## <a name="known-issues"></a>Problemi noti

L'area di lavoro **Gestione funzionalità** potrebbe visualizzare funzioni disabilitate come funzioni di anteprima quando sono generalmente disponibili. Di seguito è riportato un elenco di funzionalità generalmente disponibili che mostrano uno stato errato. 

- Gestione benefit
- Gestione casi
- Registrazione database (controllo)
- Accumulo per congedo di una singola società o un singolo piano
- Sospensione accumuli per congedo e assenza
- Codice motivo rettifica saldo e commento
- Acquista e vendi congedo
- Calendario di congedi e assenze
- Regole di riporto per congedo
- Controllo accumulo per congedo
- Eliminazione accumuli per congedo
- Arrotondamento accumulo per congedo
- Configura più tipi di congedo in un piano di congedo singolo
- Aggiornamento del permesso migliorato
- Utilizza l'equivalenza a tempo pieno del dipendente per gli accumuli
- Visualizzazione retribuzione interaziendale
- Stampare le valutazioni delle prestazioni
- Correzioni giorni festivi accumulo per congedo

### <a name="benefit-plan-employee-entity"></a>Entità dipendente del piano di benefit 

Abbiamo recentemente scoperto due problemi riguardanti l'entità **BenefitsPlanEmployee**. Quando si importano le iscrizioni dei lavoratori, il **Codice di copertura** e il **Codice tipo piano** vengono impostati in modo errato. Questo problema causa la visualizzazione errata dei piani di benefit per i dipendenti nel modulo **Piano di benefit del lavoratore** e nel modulo **Iscrizione aperta** in Self-service dipendente. Questo problema può anche influire sulla capacità del dipendente di selezionare i piani in Self-service dipendente. Al momento non c'è una soluzione alternativa. Consideriamo questo come una soluzione ad alta priorità e implementeremo la correzione nella prossima versione.

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
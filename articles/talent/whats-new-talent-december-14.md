---
title: Novità o modifiche in Dynamics 365 for Talent Core HR (14 dicembre 2018)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 12/14/2018
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
ms.search.validFrom: 2018-12-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 7d2866923efd7f115ad5290f35ed4fcac5e47573
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "304926"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-december-14-2018"></a>Novità o modifiche in Dynamics 365 for Talent Core HR (14 dicembre 2018)

[!include [banner](includes/banner.md)]

**Build 8.1.2085**

Questo argomento descrive le funzionalità nuove o modificate di Core HR.

## <a name="changes"></a>Modifiche

### <a name="us---aca-affordable-care-act-support-for-tax-year-2018-1095-b-and-1095-c-forms"></a>Supporto ACA (Affordable Care Act) per l'anno fiscale 2018 - Moduli 1095-B and 1095-C

Ogni anno, i datori di lavoro ALE (Applicable Large Employers) devono fornire a ogni dipendente a tempo pieno un modulo 1095-C. Inoltre, se il datore di lavoro fornisce una copertura autoassicurata, deve fornire il modulo 1095-C (se è un datore di lavoro ALE) e il modulo 1095-B (se ha pochi dipendenti) a qualsiasi dipendente, a tempo pieno o a tempo parziale, coperto da un piano di assistenza sanitaria. Questa funzionalità fornisce moduli 1095-C e 1095-B stampabili.

### <a name="during-import-submittedbypersonid-field-on-hcmperfjournalentity-is-ignored"></a>Durante l'importazione il campo SubmittedByPersonId in HcmPerfJournalEntity viene ignorato

Durante l'importazione/esportazione delle voci del giornale di registrazione delle prestazioni, il campo **Inviato da** viene ignorato. Con questa modifica, il valore **importato/esportato** rifletterà il valore della tabella durante l'esportazione; durante l'importazione, il sistema verrà aggiornato con il valore fornito nel file di importazione.

### <a name="analytics-tab-on-leave-and-absence-workspace-displays-openconnectionerror-error-for-non-system-admin-roles"></a>La scheda Analisi nell'area di lavoro "Congedo e assenza" visualizza l'errore "OpenConnectionError" per i ruoli di amministratore non di sistema

Con questo aggiornamento, non verrà generato alcun errore quando si apre la scheda **Analisi** nell'area di lavoro **Congedo e assenza**.

### <a name="employee-self-service-position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a>In Dipendente self-service il drill-down della gerarchia delle posizioni non riesce a richiamare il nodo padre

È stata apportata una modifica per correggere l'errore "Richiamo del nodo padre non riuscito" quando la gerarchia delle posizioni viene personalizzata per essere visualizzata in un'area di lavoro esistente e una posizione è selezionata nella gerarchia.  

### <a name="must-be-system-admin-to-see-the-payroll-tab-in-the-position-page"></a>È necessario essere un amministratore di sistema per visualizzare la scheda Retribuzioni nella pagina Posizione

È stata apportata una modifica per includere gli elementi di protezione corretti nel privilegio esistente: "Gestisci i dettagli di lavoratori e posizioni per la retribuzione". Con questa modifica, per impostazione predefinita, l'amministratore delle retribuzioni potrà accedere ai campi Retribuzioni nella pagina Posizione.

### <a name="error-when-submitting-performance-review-to-manager-and-the-reviewsperfperiod-placeholder-is-used-in-the-submission-instructions"></a>Errore durante l'invio della revisione delle prestazioni al responsabile e il segnaposto %Reviews.PerfPeriod% è utilizzato nelle istruzioni di invio

È stata apportata una modifica che corregge l'errore "Riferimento null" quando si utilizza il segnaposto %Reviews.PerfPeriod% nelle istruzioni di invio.

### <a name="workforce-power-bi-report-shows-error-when-worker-seniority-date-is-a-leap-day"></a>Il report Power BI sulla forza lavoro presenta un errore quando la data di anzianità del lavoratore è un giorno bisesto

Con questa modifica, i giorni bisesti sono ora supportati in Power BI.

### <a name="integration-between-core-hr-and-attract"></a>Integrazione tra Core HR e Attract

È stata apportata una modifica per aggiornare l'integrazione tra Core HR e Attract in relazione ai candidati da assumere. Affinché i candidati da assumere siano visibili nell'area di lavoro **Gestione personale**, vengono utilizzate le seguenti entità CDS per Apps (CDS 2.0):

Domanda di lavoro
- Motivo dello stato deve essere impostato su Offerta accettata
-   Fornisce Candidato e Posizione aperta

Candidato
-   Fornisce Informazioni sul candidato

Posizione aperta
-   Fornisce ID posizione aperta e Partecipanti posizione aperta

Partecipanti posizione aperta
-   Fornisce Responsabile assunzioni

Quando un candidato è aggiunto a Gestione personale, può anche essere chiuso utilizzando una nuova opzione disponibile nella scheda del candidato.

## <a name="coming-soon"></a>Presto disponibili

### <a name="leave-and-absence-future-leave-and-forecasting-leave-balances"></a>Congedo e assenza: saldi congedo futuri e previsione di saldi congedo

A seguito delle modifiche apportate per consentire ai dipendenti di prevedere i permessi e richiedere richieste di permessi futuri senza alterare i relativi saldi permesso correnti, anche la modalità di visualizzazione dei saldi permesso risulterà modificata. 

Il saldo disponibile attualmente visualizzato è la quantità di permessi disponibile per le richieste inclusi gli accumuli fino alla data odierna e tutte le richieste di congedo approvate. 

Al rilascio della funzionalità di previsione, il saldo visualizzato sarà il saldo permessi corrente inclusi gli accumuli e le richieste fino alla data odierna. Dipendenti e responsabili vedranno questi saldi aggiornati in responsabile e dipendente self service nella scheda **Tempo libero** e nella finestra **Saldi permessi**. I responsabili risorse umane vedranno questi saldi aggiornati nell'area di lavoro **Persone** e nella finestra **Piani di congedo assegnati del dipendente**.

## <a name="known-issue"></a>Problema noto

### <a name="mapping-errors-in-the-integration-with-finance-and-operations"></a>Errori di mapping nell'integrazione con Finance and Operations

I seguenti problemi sono stati identificati nel modello corrente per l'integrazione di Talent con Dynamics 365 for Finance and Operations. Un nuovo modello verrà pubblicato a breve e applicato a tutti i nuovi progetti di integrazione creati. Per i progetti di integrazione esistenti, i mapping di attività possono essere aggiornati. Consultare la tabella seguente per i mapping aggiornati. 

>[!NOTE]
> L'attività di assegnazione del processo padre Posizioni lavorative a Posizioni non integra dati. Questo problema è attualmente in fase di risoluzione. Non esiste alcuna soluzione alternativa nel mapping corrente. 

L'attività Reparti a Unità operativa necessita l'aggiornamento dei mapping seguenti.

| Campo origine esistente          | Campo nuova origine |
| -------------------------------|------------------|
| cdm_description (Descrizione)  | cdm_name (Nome)  |

È necessario aggiungere anche un ulteriore mapping. Selezionare l'ultimo campo **Nessuno** per aggiungere il mapping successivo.

| Campo di origine                   | Campo di destinazione    |
| -------------------------------|----------------------|
| cdm_description (Descrizione)  | NAMEALIAS (NAMEALIAS)|

I mapping aggiornati devono essere simili all'immagine seguente.

![Attività Reparti a Unità operative](./media/DepartmentMapping.png)


L'attività Mansioni a Dettagli mansione necessita l'aggiornamento dei mapping seguenti.

| Campo origine esistente          | Campo nuova origine                   |
| -------------------------------|------------------------------------|
| cdm_name (Nome)                | cdm_description (Descrizione)      |
| cdm_name (Descrizione)         | cdm_jobdescription(Descrizione mansione)|


I mapping aggiornati devono essere simili all'immagine seguente.

![Attività Mansioni a Dettagli mansione](./media/JobMapping.png)

L'attività Lavoratori a Lavoro necessita l'aggiornamento dei mapping seguenti.

| Campo origine esistente                 | Campo nuova origine                               |
| --------------------------------------|------------------------------------------------|
| cdm_emailaddress1 (Indirizzo di posta elettronica 1)   | cdm_primaryemailaddress (Indirizzo di posta elettronica principale) |
| cdm_telephone1 (Telefono 1)          | cdm_primarytelephone (Telefono principale)       |

Anche la trasformazione del campo Sesso deve essere aggiornata. Selezionare il tipo di mappa **fn** (funzione) per Sesso e aggiornare i mapping dei valori seguenti.

| Valore CDS                   | Valore Finance and Operations                     |
| ----------------------------|--------------------------------------------------|
| 75440000                    | Maschio                                             |
| 75440001                    | Femmina                                           |
| 75440002                    | Nessuna priorità                                             | 
| 75440003                    | NonSpecific                                      |

I mapping aggiornati devono essere simili all'immagine seguente.

![Attività Lavoratori a Lavoratore.](./media/WorkerMapping.png)

![Trasformazione del campo Sesso](./media/WorkerTransform.png)

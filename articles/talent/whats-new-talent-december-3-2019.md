---
title: Novità o modifiche in Dynamics 365 Talent (3 dicembre 2019)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 12/03/2019
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
ms.search.validFrom: 2019-12-03
ms.dyn365.ops.version: Talent
ms.openlocfilehash: bf1ad4ca2e0ab18aaa35a7410d80a54e7a2160ce
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528695"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-december-3-2019"></a>Novità o modifiche in Dynamics 365 Talent (3 dicembre 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo articolo descrive le funzionalità nuove o modificate in Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifiche in Onboard

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR

Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2646. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Microsoft Dynamics Lifecycle Services (LCS).

### <a name="feature-management-workspace"></a>Area di lavoro Gestione funzionalità

L'area di lavoro **Gestione funzionalità** fornisce l'elenco delle funzionalità offerte in ciascuna versione. Per impostazione predefinita, le nuove funzionalità sono disabilitate. È possibile utilizzare l'area di lavoro per accendere alle funzionalità e visualizzare la documentazione correlata. Per ulteriori informazioni sulla gestione funzionalità, vedere [Panoramica della gestione funzionalità](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Tutte le nuove funzionalità rimangono in anteprima per almeno 30 giorni e in genere per 30-60 giorni. Le principali funzionalità sono generalmente disponibili in ottobre e aprile di ogni anno successivo al periodo di anteprima. Non appena nuove funzioni sono presenti nell'area di lavoro **Gestione funzionalità**, è possibile attivarle. Alcune funzionalità possono essere attive per impostazione predefinita.
 
Talvolta, una funzionalità integrale viene attivata per impostazione predefinita e non può essere disattivata, ad esempio l'area di lavoro **Gestione funzionalità**.
 
Una volta che una funzionalità è generalmente disponibile, può essere attivata o disattivata negli ambienti di produzione. L'area di lavoro **Gestione funzionalità** indica quando una funzionalità di anteprima diventa obbligatoria. Questa data è in genere il 1° ottobre o il 1° aprile in base ai piani di rilascio semestrali. Non è possibile disattivare le funzionalità obbligatorie. Finché non diventa obbligatoria, è possibile attivare e disattivare una funzionalità in tutti gli ambienti.

### <a name="add-automatic-scheduling-of-batch-job-history-cleanup-332528"></a>Aggiungere la pianificazione automatica della pulizia di Storico processi batch (332528)

Con questa modifica, **Storico processi batch** viene eseguito ogni notte e rimuove gli elementi della cronologia dei processi batch più vecchi di 30 giorni.

### <a name="talent-doesnt-respond-in-worker-actions-when-identification-number-length-doesnt-match-the-identification-type-390971"></a>Talent non risponde nelle azioni del lavoratore quando la lunghezza del numero di identificazione non corrisponde al tipo di identificazione (390971)

Questa versione corregge il problema che si verifica quando la lunghezza del numero di identificazione non corrisponde alla definizione all'interno del tipo di identificazione. 

### <a name="fixed-compensation-doesnt-update-level-with-changes-to-position-details--348085"></a>La retribuzione fissa non aggiorna il livello con modifiche ai dettagli della posizione (348085)

Nella versione di questa settimana, **Data di inizio retribuzione** determina il lavoro associato alla posizione in quel punto nel momento in cui si crea un nuovo record di retribuzione fissa per un dipendente.

### <a name="workers-employees-and-contractors-lists-show-worker-type-as-both-when-they-should-only-be-worker-or-contractor-384473"></a>Gli elenchi di lavoratori, dipendenti e appaltatori mostrano il tipo di lavoratore come Entrambi quando dovrebbero essere solo lavoratore o appaltatore (384473)

Questa modifica riflette accuratamente il tipo di lavoratore inserito (appaltatore o impiegato).

### <a name="email-notifications-for-new-hire-actions-dont-contain-name-information-due-to-security-policies-383402"></a>Le notifiche e-mail per le nuove azioni di assunzione non contengono informazioni sul nome a causa dei criteri di sicurezza (383402)

Questa modifica corregge le informazioni visualizzate nei campi nome o cognome all'interno dei segnaposto per il flusso di lavoro quando è abilitata la sicurezza avanzata.

### <a name="system-allows-two-full-day-leave-requests-for-the-same-day-379284"></a>Il sistema consente due richieste di congedo di un'intera giornata per lo stesso giorno (379284)

Con questa modifica, non è possibile emettere due richieste di congedo per lo stesso giorno. 

### <a name="address-changes-list-should-be-sorted-by-effective-date-352798"></a>L'elenco delle modifiche dell'indirizzo deve essere ordinato per Data di validità (352798)

Con questa modifica, l'elenco delle modifiche dell'indirizzo è ora ordinato per **Data di validità**.

### <a name="leave-requests-should-allow-deletes-from-common-data-service-to-talent-376999"></a>Le richieste di congedo dovrebbero consentire l'eliminazione da Common Data Service a Talent (376999)

Con questa modifica, è possibile eliminare le richieste di congedo bozza e annullate da Common Data Service e quindi rimosse da Talent.

### <a name="delete-earning-codes-is-allowed-when-the-same-earning-code-is-assigned-to-an-employee-371792"></a>L'eliminazione dei codici di reddito è consentita quando lo stesso codice di reddito è assegnato a un dipendente (371792)

In questa versione, è necessario prima rimuovere il codice di reddito dal dipendente prima di eliminare il codice di reddito dal sistema.

### <a name="leave-and-absence-workflow-with-two-approval-stages-fails-to-complete--391116"></a>Il flusso di lavoro di congedo e assenza con due fasi di approvazione non viene completato (391116)

Con questa modifica, il flusso di lavoro di congedo e assenza continua attraverso tutti i passaggi quando più di una fase di approvazione è configurata per la richiesta.

### <a name="issue-date-doesnt-sync-to-common-data-service-when-updated-or-entered-in-talent-397361"></a>La data di emissione non si sincronizza con Common Data Service se aggiornata o inserita in Talent (397361)

Questa modifica risolve un problema in cui la data di emissione per i record **Identificazione di una persona** non sono stati sincronizzati con Common Data Service da Talent.

### <a name="hierarchy-circular-reference-error-issued-when-assigning-a-manager-to-a-position-386659"></a>Errore di riferimento circolare della gerarchia generato durante l'assegnazione di un responsabile a una posizione (386659)

Questa modifica corregge uno scenario unico in cui appare un errore di riferimento circolare quando si assegna un nuovo responsabile a una posizione.

### <a name="common-data-service-entities-that-now-support-custom-fields"></a>Entità in Common Data Service che ora supportano campi personalizzati

Le seguenti entità di Common Data Service supportano ora i campi personalizzati:

| Nome | Entità |
| --- | --- |
| Esborso conto bancario | cdm_bankaccountdisbursement |
| Frequenza di calcolo benefit | cdm_benefitcalculationfrequency |
| Periodo retributivo della frequenza di calcolo benefit | cdm_benefitcalculationfrequencypayperiod |
| Coefficiente di calcolo benefit | cdm_benefitcalculationrate |
| Dettagli dei coefficienti di calcolo benefit | cdm_benefitcalculationratedetail |
| Opzione benefit | cdm_benefitoption |
| Piano benefit | cdm_benefitplan (Non abilitato per il supporto del campo personalizzato) |
| Tipo di benefit | cdm_benefittype |
| Calendario di processi aziendali | cdm_businessprocesscalendar |
| Assegnazione gruppo di processi aziendali | cdm_businessprocessgroupassignment |
| Gruppo di attività libreria processi aziendali | cdm_businessprocesslibrarytaskgroup |
| Fase di processi aziendali | cdm_businessprocessstage |
| Intestazione modello elenco di controllo | cdm_businessprocesstemplateheader |
| Attività del modello elenco di controllo | cdm_businessprocesstemplatetask |
| Società | cdm_company |
| Piano di retribuzione fissa | cdm_compensationfixedplan |
| Griglia di retribuzione | cdm_compensationgrid |
| Livello retributivo | cdm_compensationlevel |
| Frequenza della retribuzione | cdm_compensationpayfrequency |
| Impostazione punti di riferimento per le retribuzioni | cdm_compensationreferencepointsetup |
| Riga impostazione punti di riferimento per le retribuzioni | cdm_compensationreferencepointsetupline |
| Paese di retribuzione | cdm_compensationregion |
| Struttura retributiva | cdm_compensationstructure |
| Piano di retribuzione variabile | cdm_compensationvariableplan |
| Livello del piano di retribuzione variabile | cdm_compensationvariableplanlevel |
| Tipo di piano di retribuzione variabile | cdm_compensationvariableplantype |
| Reparto | cdm_department |
| Impiego | cdm_employment |
| Origine etnica | cdm_ethnicorigin |
| Evento di retribuzione fissa | cdm_fixedcompensationevent |
| Posizione | cdm_job |
| Funzione lavorativa | cdm_jobfunction |
| Posizione lavorativa | cdm_jobposition |
| Tipo di mansione | cdm_jobtype |
| Lingua | cdm_language |
| Transazione bancaria di congedo | cdm_leavebanktransaction |
| Iscrizione congedo | cdm_leaveenrollment |
| Piano di congedo | cdm_leaveplan |
| Richiesta di congedo | cdm_leaverequest |
| Dettagli richiesta congedo | cdm_leaverequestdetail |
| Tipo di congedo | cdm_leavetype |
| Codice motivo del tipo di congedo | cdm_leavetypereasoncode |
| Ciclo retributivo | cdm_paycycle |
| Periodo retributivo | cdm_payperiod |
| Codice di reddito per retribuzione | cdm_payrollearningcode |
| Agenzia di rilascio dell'identificazione della persona | cdm_personidentificationissuingagency |
| Tipo di posizione | cdm_positiontype |
| Assegnazione lavoratore posizione | cdm_positionworkerassignmentmap |
| Codice causale | cdm_reasoncode |
| Tipo di competenza | cdm_skilltype |
| Regione fiscale | cdm_taxregion |
| Regola di distribuzione incentivi | cdm_vestingrule |
| Stato di veterano | cdm_veteranstatus |
| Calendario lavorativo | cdm_workcalendar |
| Giorno calendario di lavoro | cdm_workcalendarday |
| Festività calendario lavorativo |cdm_workcalendarholiday |
| Riga festività del calendario di lavoro | cdm_workcalendarholidayline |
| Intervallo orario calendario di lavoro | cdm_workcalendartimeinterval (Non abilitato per il supporto del campo personalizzato) |
| Lavoro | cdm_worker |
| Indirizzo lavoratore | cdm_workeraddress |
| Conto bancario del lavoratore | cdm_workerbankaccount |
| Retribuzione fissa lavoratore | cdm_workerfixedcompensation |
| Dati personali lavoratore | cdm_workerpersonaldetail |
| Numero di identificazione lavoratore | cdm_workerpersonidentificationnumber |
| Tipo di identificazione lavoratore | cdm_workerpersonidentificationtype |

## <a name="in-preview"></a>In anteprima

Le funzionalità di anteprima sono disponibili solo negli ambienti **sandbox**.

### <a name="print-performance-reviews"></a>Stampare le valutazioni delle prestazioni

Vedere [Stampare le valutazioni delle prestazioni](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) nel piano della seconda ondata di rilascio di Dynamics 365: 2019.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
---
title: Novità o modifiche in Dynamics 365 Human Resources (03 settembre 2020)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 3 settembre 2020.
author: andreabichsel
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7d558f4b0ddb3e8fe3479567483e2c2349a40774
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891352"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-3-2020"></a>Novità o modifiche in Dynamics 365 Human Resources (3 settembre 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Questo articolo descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources. Le modifiche si applicano alla build 8.1.3504. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Lifecycle Services (LCS) per riferimento.

Per ulteriori informazioni sulle funzionalità future di Human Resources, vedere [Panoramica del secondo ciclo di rilascio del 2019 di Dynamics 365 Human Resources](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/). Per ulteriori informazioni sul processo di aggiornamento per Human Resources, vedere [Processo di aggiornamento](hr-admin-setup-update-process.md).

## <a name="in-this-release"></a>In questa versione

### <a name="new-default-financial-dimensions-grid-and-dialog-pattern-throughout-human-resources-469495"></a>Nuova griglia delle dimensioni finanziarie predefinite e schema di dialogo in Human Resources (469495)

Il nuovo modello per le dimensioni finanziarie è ora disponibile nelle seguenti aree:

- Azioni della posizione (Modulo: **HcmPositionActionDetail**)
- Codici di reddito per retribuzione (Modulo: **PayrollEarningCode**)

### <a name="entries-dont-appear-in-company-leave-calendar-if-leave-and-absence-calendar-enhancements-arent-enabled-484406"></a>Le voci non vengono visualizzate nel calendario dei congedi dell'azienda se i miglioramenti del calendario dei congedi e delle assenze non sono abilitati (484406)

Questa versione corregge un problema in cui le voci di congedo non vengono visualizzate nel calendario dei congedi dell'azienda. Questo problema si verifica solo quando l'opzione di Gestione funzionalità **Miglioramenti del calendario di congedi e assenze** non è abilitata.

### <a name="benefitplanemployeeentity-issue-467597"></a>Problema di BenefitPlanEmployeeEntity (467597)

Questa versione risolve un problema con l'entità **BenefitsPlanEmployee**. Quando si importano le iscrizioni dei lavoratori, il **Codice di copertura** e il **Codice tipo piano** vengono ora impostati correttamente. Questo problema causa la visualizzazione errata dei piani di benefit per i dipendenti nei moduli **Piano di benefit del lavoratore** e **Iscrizione aperta** in Self-service dipendente.

### <a name="electronic-file-1094-c-output-missing-letter-in-xml-435190"></a>lettera mancante nell'output del file elettronico 1094-C in XML (435190)

Questa modifica risolve un problema con il file di output 1094-C privo di un carattere necessario per l'invio all'IRS.

### <a name="employee-variable-compensation-table-mapped-to-fixed-compensation-form-476117"></a>Tabella retribuzione variabile dipendente mappata al modulo retribuzione fissa (476117)

Questa modifica allinea i campi di retribuzione fissa con il modulo di retribuzione fissa. I campi di retribuzione variabile sono ora disponibili solo con il modulo di retribuzione variabile.

### <a name="leave-requests-allowed-before-enrollment-if-that-leave-type-has-a-negative-minimum-balance-469917"></a>Richieste di congedo consentite prima dell'iscrizione se il tipo di congedo ha un saldo minimo negativo (469917)

Questa modifica impedisce l'inserimento di richieste di congedo prima di essere iscritti al piano, anche se l'iscrizione ha un saldo minimo negativo. È possibile inserire o inviare richieste solo quando il piano è attivo.

### <a name="document-templates-dont-download-457279"></a>I modelli di documento non vengono scaricati (457279)

Con questa modifica, ora è possibile scaricare tutti i modelli di documento. 

### <a name="data-displays-as-column-headers-instead-of-rows-for-the-pay-rate-field-in-the-compensation-plan-report-476077"></a>I dati vengono visualizzati come intestazioni di colonna anziché righe per il campo Tariffa retributiva nel report del piano di retribuzione (476077)

Il report di analisi ora visualizza le informazioni corrette per **Tariffa retributiva**.

## <a name="in-preview"></a>In anteprima

### <a name="human-resources-application-in-teams"></a>Applicazione Human Resources in Teams

I dipendenti possono visualizzare i congedi e richiederli in Microsoft Teams. Possono interagire con un bot per creare richieste di congedo. Per ulteriori informazioni, vedere:

- [Esperienza di congedo e assenza dei dipendenti in Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) nel piano della prima ondata di rilascio di Dynamics 365 2020
- [App Human Resources in Teams](./hr-admin-teams-leave-app.md) nella documentazione di Human Resources

### <a name="human-resources-app-in-teams-preview-features"></a>Funzioni di anteprima dell'app Human Resources in Teams
 
-  **Notifiche**: i mittenti e gli approvatori delle richieste di permesso verranno informati nell'app Human Resources in Teams. Gli approvatori potranno approvare o rifiutare le richieste di permesso. I mittenti riceveranno una notifica se la richiesta è stata approvata o rifiutata. Per ulteriori informazioni, vedere:
   - [Esperienza di congedo e assenza dei dipendenti in Microsoft Teams](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) nel piano del primo ciclo di rilascio del 2020 di Dynamics 365
   - [Abilitare le notifiche per l'app Human Resources in Teams](./hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) nella documentazione di Human Resources
   - [Attivare o disattivare le notifiche di Teams per i singoli utenti](./hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users) nella documentazione di Human Resources
   - [Notifiche di Teams](./hr-teams-leave-app.md#respond-to-teams-notifications) nella documentazione di Human Resources
   - [Visualizzare il calendario dei congedi della team](./hr-teams-leave-app.md#view-your-teams-leave-calendar) nella documentazione di Human Resources
 
- **Calendario permessi del responsabile**: i responsabili potranno vedere i permessi approvati e in sospeso per i loro diretti subalterni in una visualizzazione calendario. Questa visualizzazione fornisce una facile comprensione di quando i membri del team non sono al lavoro. Per ulteriori informazioni, vedere:
   - [Esperienza di congedo e assenza dei dipendenti in Microsoft Teams](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) nel piano del primo ciclo di rilascio del 2020 di Dynamics 365
   - [Visualizzare il calendario dei congedi della team](./hr-teams-leave-app.md#view-your-teams-leave-calendar) nella documentazione di Human Resources

### <a name="configuration-option-to-position-work-items-assigned-to-me-list-477004"></a>Opzione di configurazione per posizionare l'elenco Elementi di lavoro assegnati all'utente (477004)

È ora disponibile una nuova opzione per posizionare l'elenco **Elementi di lavoro assegnati all'utente** nella colonna di destra della dashboard. Con questa modifica, tutti gli elementi di lavoro e gli elenchi di attività vengono visualizzati nella stessa area. Abilitare questa funzionalità attivandola in **Anteprima: miglioramenti dell'esperienza del flusso di lavoro** in Gestione funzionalità. Per ulteriori informazioni su come attivare le funzionalità di anteprima, vedere [Gestire le funzionalità](hr-admin-manage-features.md).

Questa funzione promuove anche le opzioni del flusso di lavoro che appaiono nei moduli delle azioni del personale. Le opzioni del flusso di lavoro vengono visualizzate anche sopra la scheda dettaglio Azione per un accesso rapido. Per ulteriori informazioni, vedere: 

- [Miglioramenti all'esperienza del flusso di lavoro di organizzazione e gestione del personale](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) nel piano del secondo ciclo di rilascio del 2020 di Dynamics 365

![Elementi di lavoro assegnati all'utente.](./media/hr-workflow-work-items-assigned-to-me.png)

![Accesso rapido agli elementi del flusso di lavoro.](./media/hr-workflow-quick-access.png)

## <a name="coming-soon"></a>Presto disponibili

### <a name="checklist-entities-included-in-dataverse"></a>Elenco di controllo entità incluso in Dataverse

Le entità dell'elenco di controllo per i processi di onboarding, offboarding, trasferimenti e aziendali saranno presto disponibili in Dataverse.

### <a name="benefits-management-reason-codes"></a>Codici motivo gestione vantaggi

I codici motivo per la gestione dei vantaggi verranno presto combinati con i codici motivo esistenti in Human Resources. Se sono stati creati codici motivo nella gestione dei vantaggi che superano i 15 caratteri, è necessario modificare il nome del codice motivo nel modulo **Codici motivo** della gestione dei vantaggi in modo che abbia al massimo 15 caratteri. Dopo aver aggiornato il nome, il codice motivo verrà visualizzato sotto il modulo del codice motivo esistente in Gestione del personale. Questa modifica sarà disponibile in futuro e non influirà sul funzionamento esistente.

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

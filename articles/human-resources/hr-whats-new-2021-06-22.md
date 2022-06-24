---
title: Novità e modifiche in Dynamics 365 Human Resources 22 giugno 2021
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 22 giugno 2021.
author: marcelbf
ms.date: 06/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: aacb605374d99a3c0bad3438c89e33a04a4d7faf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897779"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-22-2021"></a>Novità e modifiche in Dynamics 365 Human Resources 22 giugno 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo descrive le funzionalità nuove, modificate o future di Dynamics 365 Human Resources.

Per ulteriori informazioni sul processo di aggiornamento e pianificazione, vedere [Processo di aggiornamento](hr-admin-setup-update-process.md).

Per ulteriori informazioni sulle nuove funzionalità e sulle date di disponibilità generale previste, vedere [Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>In questa versione

Questa versione include le seguenti nuove funzionalità e correzioni di bug. Le modifiche si applicano alla build 8.1.4258.

### <a name="new-features"></a>Nuove funzionalità

Le seguenti funzioni sono generalmente disponibili con questa versione.

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| Informa gli utenti della funzione lavoratori senza impiego - Quando l'accesso avanzato è attivo e la funzionalità **Visualizza tutti i lavoratori senza impego** è disabilitata nella gestione delle funzionalità, verrà visualizzato un banner nel modulo lavoratori senza impiego. Il banner indirizzerà l'utente ad attivare la funzionalità **Visualizza tutti i lavoratori senza impiego**. | Non applicabile| [Lavoratori senza impiego](/dynamics365/human-resources/hr-personnel-workers-without-employment)|
| Supporto per campi personalizzati delle regole di idoneità di Gestione benefit | [Supporto per campi personalizzati per l'elaborazione dell'idoneità](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |[Configurazione delle regole di idoneità](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules) |
| Controllo transazione accumulo per congedo | Non applicabile | [Controllo transazione accumulo per congedo](hr-leave-and-absence-accrue.md)|
| Miglioramenti dell'esperienza del flusso di lavoro congedo e assenza | [Miglioramenti dell'esperienza del flusso di lavoro congedo e assenza](https://go.microsoft.com/fwlink/?linkid=2147528) | [Richiedere un permesso](hr-employee-self-service-request-time-off.md)|

### <a name="bug-fixes"></a>Correzioni di bug

Questa versione include le seguenti correzioni di bug.

> [!NOTE]
> Il nostro obiettivo è fornire queste informazioni il prima possibile. Potremmo aggiornare questo articolo per includere le correzioni di bug che sono state inserite nella build dopo che questo articolo è stato inizialmente pubblicato.

| Numero problema | Problema |  Description |
| --- | --- | --- |
| 583052 | L'utente che riceve il feedback è in grado di modificare il feedback ricevuto | Quando un dipendente che riceve un feedback su un diario delle prestazioni seleziona **Aggiungi collegamento esterno**, il modulo diventa modificabile, consentendo al dipendente di modificare il feedback sulle prestazioni ricevuto. |
| 522281 | La selezione del numero di dipendenti nei riquadri della struttura retributiva in Gestione retribuzioni porta a risultati errati| Quando si esegue il drill-down dei piani retributivi dall'area di lavoro retribuzioni, viene ora visualizzato il numero corretto di dipendenti. |
| 580683 | Gli utenti assegnati ai ruoli di dipendente e responsabile non sono in grado di allegare note o aggiornare un giornale di registrazione delle prestazioni | Gli utenti assegnati ai ruoli di dipendente e responsabile non sono in grado di allegare note o aggiornare un giornale di registrazione delle prestazioni. L'utente riceve l'errore "Impossibile creare un record nella voce del giornale di registrazione prestazioni (HcmPerfJournal). Autorizzazione criteri di sicurezza negata". |
| 583077 | La data di nascita di un dipendente nel calendario aziendale di congedo e assenza mostra una data errata | Gli utenti potranno visualizzare la data di nascita corretta dei dipendenti nel calendario aziendale di congedi e assenze. |
| 586996 | La funzione di visualizzazione dei congedi interaziendali fa sì che i saldi siano vuoti quando l'accesso è limitato a una singola azienda | Gli utenti possono visualizzare correttamente i saldi dei congedi futuri dei dipendenti quando è abilitata la visualizzazione dei congedi interaziendali. |
| 581014 | L'abilitazione della visualizzazione di congedi e assenze interaziendali causa un errore durante la visualizzazione dei saldi futuri | Gli errori sono stati corretti quando gli utenti visualizzavano i saldi dei congedi futuri con la visualizzazione dei congedi interaziendali abilitata. |
| 509404 | L'analisi dell'organico del reparto non prende in considerazione il movimento dei dipendenti tra i reparti. | Quando un dipendente migra da un reparto a un altro, i dati dell'organico del reparto non riflettono il vecchio reparto da cui il dipendente è uscito se i dettagli della posizione sono scaduti nell'anno in corso. |
| 584851 | La regola di ripartizione del credito dei benefit "Nessuno" non fornisce mai credito |La regola di ripartizione del credito flessibile "Nessuno" ha comportato che i dipendenti non ricevessero crediti per il periodo di benefit, indipendentemente da quando sono stati assunti. Questo è stato corretto in modo che un dipendente riceva crediti flessibili completi se viene assunto prima dell'inizio del periodo di benefit e nessuno se viene assunto dopo l'inizio del periodo. |
| 584897 | La duplicazione del diritto "Utilizza funzionalità esterna di base" genera un errore | Durante il tentativo di duplicare il diritto "Utilizza funzionalità esterna di base", l'utente ha ricevuto l'errore "Impossibile trovare l'oggetto con identificatore UserDefinedAppHostDialogView". |
| 575692 | Il congedo e l'assenza maturati non sono disponibili per i lavoratori in sospeso | L'accumulo di ferie e assenze può essere eseguita su assunzioni future quando **Inserimento dipendenti semplificato** è abilitato. |
| 580110 | L'aggiunta di una società all'integrazione retribuzioni reimposta l'integrazione per utilizzare tutte le entità anche se l'opzione è impostata per non aggiornare il progetto | Se un cliente ha rimosso entità o ha modificato il progetto dati per l'integrazione retribuzioni e ha impostato l'opzione per impedire un aggiornamento automatico del progetto, l'aggiunta di una nuova società all'integrazione ignora l'impostazione e aggiorna il progetto.  |
| 584518 |Problema delle prestazioni di elaborazione di registrazione dei benefit | Questo bug ha risolto i problemi di prestazioni nel processo di registrazione dei benefit legacy. |

## <a name="in-preview"></a>In anteprima

Le seguenti nuove funzionalità sono in anteprima. Per ulteriori informazioni su come attivare o disattivare le funzionalità, vedere [Gestire le funzionalità](hr-admin-manage-features.md).

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| Area di lavoro gestione benefit | [Area di lavoro Gestione benefit](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Area di lavoro gestione benefit](hr-benefits-management-workspace.md) |
| Abilitare l'integrazione delle retribuzioni semplificata (API di integrazione delle retribuzioni) | [Abilitare l'integrazionei semplificata con i fornitori retribuzioni](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md)|


## <a name="coming-soon"></a>Presto disponibile

| Funzionalità | Dettagli |
| --- | --- |
| Platform Update 10.0.19 (43) | L'implementazione dell'aggiornamento della piattaforma 10.0.19 inizierà con la versione di servizio il 28 giugno 2021. Per ulteriori informazioni, vedere [Aggiornamenti della piattaforma per la versione 10.0.19 delle app per la finanza e le operazioni (giugno 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-19). |
|  Attivare/Disattivare la visualizzazione anni di servizio | Questa funzione offre la possibilità di utilizzare date diverse per calcolare gli anni di servizio visualizzati nel modulo **Inserimento dipendenti semplificato** e nel modulo **Persone**.  Questo sarà disponibile nei parametri Human Resources. |
|  Consentire a un responsabile dei congedi di gestire le ferie | [Consentire a un responsabile dei congedi di gestire le ferie](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) |
|  Collegamenti di mandato per tipi di congedo specifici | Questa funzione consente agli amministratori di richiedere l'aggiunta di collegamenti di mandato quando si inviano richieste di congedo per tipi di congedo specifici. |
|  Configurare unità di congedo per tipo di congedo | Questa funzione consente agli amministratori di configurare le unità di congedo (ore o giorni) per ciascun tipo di congedo.  |
| Consentire ai dipendenti di essere contrassegnati come pronti per essere pagati | [Consentire ai dipendenti di essere contrassegnati come pronti per essere pagati](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) |

Per un elenco completo delle funzionalità pianificate e delle relative versioni pianificate, vedi [Panoramica del primo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica del primo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

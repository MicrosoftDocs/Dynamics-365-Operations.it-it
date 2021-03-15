---
title: Novità o modifiche in Dynamics 365 Human Resources (6 ottobre 2020)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 6 ottobre 2020.
author: jcart1106
manager: tfehr
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 036b43d8730b52bddc93c0fc3b47d9d62649e898
ms.sourcegitcommit: 2190be6c205d7d9e43bdb99b9190cc0112f9f093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/10/2021
ms.locfileid: "5152175"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-6-2020"></a>Novità o modifiche in Dynamics 365 Human Resources (6 ottobre 2020)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo argomento descrive le funzionalità nuove, modificate o presto disponibili in Dynamics 365 Human Resources. Per ulteriori informazioni sul processo di aggiornamento e pianificazione, vedere [Processo di aggiornamento](hr-admin-setup-update-process.md).

Per ulteriori informazioni sulle nuove funzionalità e sulle date di disponibilità generale previste, vedere [Panoramica del secondo ciclo di rilascio del 2020 di Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>In questa versione

Questa versione include le seguenti nuove funzionalità e correzioni di bug. Le modifiche si applicano alla build 8.1.3636.

### <a name="new-features"></a>Nuove funzionalità

La seguente funzione è generalmente disponibile con questa versione.

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| Ulteriori informazioni sui calendari dei congedi | [Fornire ulteriori informazioni dettagliate nelle visualizzazioni dei calendari dei congedi](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-leave-calendar-views) | [Visualizzare il calendario per team e società](hr-employee-self-service-calendar.md) |

### <a name="bug-fixes"></a>Correzioni di bug

Questa versione include le seguenti correzioni di bug.

>[!NOTE]
> Il nostro obiettivo è fornire queste informazioni il prima possibile. Potrebbero esserci aggiornamenti a questo argomento per includere correzioni di bug che sono state introdotte nella build dopo la pubblicazione iniziale di questo argomento.

| Numero problema | Uscita | descrizione |
| --- | --- | --- |
| 448806 | **Tipo di identificazione predefinito** viene esportato come **RecID** nei parametri HCM | Questa modifica all'entità dei parametri di Human Resources aggiunge una colonna che visualizza il **Tipo di identificazione predefinito**. |
| 492923 | Le registrazioni delle attività non vengono salvate in Lifecycle Services (LCS) | Le registrazioni attività ora possono essere salvate in LCS. |
| 429950 | La retribuzione fissa non scade correttamente durante il cambio di posizione | Quando si cambia la posizione di un lavoratore nella pagina **Trasferisci lavoratore**, la data di fine retribuzione è stata fissata un giorno prima della fine della posizione. La data di fine della retribuzione è ora la stessa della data di fine della posizione. |
| 467214 | **Analisi stipendio** viene visualizzato solo se **Nome conversione tariffa retributiva** è impostato su **Annuale** | Le tariffe retributive stipendiate con un nome diverso da **Annuale** non vengono visualizzate nell'analisi di retribuzione. Con questo aggiornamento, le analisi di retribuzione ora utilizzano tutte le conversioni della tariffa retributiva. Quando si eseguono i report da **Orario** o **Stipendio**, qualsiasi conversione della tariffa di pagamento che utilizza un periodo diverso da quello orario è inclusa nel filtro **Stipendio**. Paga solo tariffe retributive con un periodo **Orario** sono incluse nel filtro **Orario**. |
| 482464 | Durante la visualizzazione delle **Revisioni**, la vista **Dettagli** non cambia in visualizzazione griglia dopo aver applicato un filtro | Dopo aver applicato un filtro, la griglia delle revisioni viene visualizzata come previsto. |
| 483184 | Human Resources non genera la maturazione delle ferie quando si seleziona **Base livello** come **Data di inizio rettificata** nel record **Iscrizione congedo** |La **Data di inizio rettificata** viene compilata e utilizzata per la generazione della maturazione delle ferie.  |
| 509731 | La richiesta di ferie per futuri lavoratori licenziati causa problemi se richiedono un periodo di ferie dopo la data di cessazione | Ora è possibile inviare richieste di ferie per i dipendenti con una data di cessazione futura purché la richiesta sia anteriore alla data di cessazione. |
| 510716 | L'analisi retributiva include dipendenti sia uomini che donne per **Retribuzione oraria media maschile** | Nell'analisi retributiva, **Retribuzione oraria media maschile** in **Analisi demografica retribuzione** include la retribuzione media femminile. Ora include solo i maschi. |
| 511348 | Il self-service dei vantaggi deve mostrare solo i piani di benefit validi da oggi fino alla fine del periodo di benefit | I piani di benefit scaduti venivano mostrati ai dipendenti nella pagina **Iscrizione ai benefit**. Questa correzione rimuove questi piani. |
| 512706 | Impostare i seguenti campi su sola lettura:<ul><li>BenefitPlanEmployeeEntity</li><li>EnrollmentConfirmed</li><li>EnrollmentConfirmedBy</li><li>EnrollmentConfirmedDateTime | I pulsanti **Aggiungi** e **Rimuovi** per i dettagli delle dimensioni erano abilitati in modo errato dopo il completamento dell'azione. Questo aggiornamento alla pagina **Dettagli azione posizione** rende i campi non modificabili dopo che l'azione è stata completata. |

## <a name="in-preview"></a>In anteprima

Le seguenti nuove funzionalità sono in anteprima. Per ulteriori informazioni su come attivare o disattivare le funzionalità, vedere [Gestire le funzionalità](hr-admin-manage-features.md).

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| App Human Resources in Microsoft Teams | [Esperienza di congedo e assenza dei dipendenti in Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [App Human Resources in Teams](https://go.microsoft.com/fwlink/?linkid=2127841)<br>[Gestire le richieste di congedo in Teams](hr-teams-leave-app.md) |
| Richieste e approvazioni del flusso di lavoro migliorate | [Miglioramenti all'esperienza del flusso di lavoro dell'organizzazione e della gestione del personale](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Opzione di configurazione per posizionare l'elenco Elementi di lavoro assegnati all'utente](https://docs.microsoft.com/dynamics365/human-resources/hr-whats-new-2020-09-03#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Entità virtuali in Dataverse per Human Resources | [Espandere i dati di base Dynamics 365 Human Resources in Dataverse](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/expand-dynamics-365-human-resources-core-data-common-data-service) | [Configurare le entità virtuali di Dataverse](hr-admin-integration-common-data-service-virtual-entities.md) |

## <a name="coming-soon"></a>Presto disponibili

Le seguenti nuove funzionalità sono previste per le versioni future:

- **Elenco di controllo entità incluso in Dataverse**: Le entità dell'elenco di controllo per i processi di onboarding, offboarding, trasferimenti e aziendali saranno presto disponibili in Dataverse.

- **Codici motivo gestione vantaggi**: I codici motivo per la gestione dei vantaggi verranno presto combinati con i codici motivo esistenti in Human Resources. Se sono stati creati codici motivo nella gestione dei vantaggi che superano i 15 caratteri, è necessario modificare il nome del codice motivo nel modulo **Codici motivo** della gestione dei vantaggi in modo che abbia al massimo 15 caratteri. Dopo aver aggiornato il nome, il codice motivo verrà visualizzato sotto il modulo del codice motivo esistente in Gestione del personale. Questa modifica sarà disponibile in futuro e non influirà sul funzionamento esistente.

- **Collegamenti personalizzati in self-service dei responsabili** : Per supportare i responsabili, stiamo espandendo le capacità nel self-service dei responsabili. Stiamo aggiungendo la possibilità di aggiungere collegamenti personalizzati nella scheda **Team personale**. Questa funzione è simile alla funzione dei collegamenti personalizzati nella **scheda Informazioni personali** nel self-service dei dipendenti. Per ulteriori informazioni, vedere [Collegamenti personalizzati nel self-service responsabili](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service).

Per un elenco completo delle funzionalità pianificate e delle relative versioni pianificate, vedere [Panoramica del secondo ciclo di rilascio del 2019 di Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/).

## <a name="additional-resources"></a>Risorse aggiuntive

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica del secondo ciclo di rilascio del 2020 di Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
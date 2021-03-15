---
title: Novità o modifiche in Dynamics 365 Human Resources 21 gennaio 2021
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 21 gennaio 2021.
author: marcelbf
manager: tfehr
ms.date: 01/21/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-01-21
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: af847ed36187c0d0629ce4063d9c17cb0fa8cfcf
ms.sourcegitcommit: 630a0b3f800f36ced49b79156dd52132904fef75
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/25/2021
ms.locfileid: "5060844"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-january-21-2021"></a>Novità o modifiche in Dynamics 365 Human Resources 21 gennaio 2021

Questo argomento descrive le funzionalità nuove, modificate o presto disponibili in Dynamics 365 Human Resources.

Per ulteriori informazioni sul processo di aggiornamento e pianificazione, vedere [Processo di aggiornamento](hr-admin-setup-update-process.md).

Per ulteriori informazioni sulle nuove funzionalità e sulle date di disponibilità generale previste, vedere [Panoramica del secondo ciclo di rilascio del 2020 di Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).


## <a name="in-this-release"></a>In questa versione

Questa versione include le seguenti nuove funzionalità e correzioni di bug. Le modifiche si applicano alla build 8.1.3866.

### <a name="new-features"></a>Nuove funzionalità

Le seguenti funzioni sono generalmente disponibili con questa versione.

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| Aggiornamento della piattaforma 10.0.16(40) | -- | [Aggiornamento della piattaforma per la versione 10.0.16 delle app Finance and Operations (febbraio 2021)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-16) |
| Richieste e approvazioni del flusso di lavoro migliorate | [Miglioramenti all'esperienza del flusso di lavoro dell'organizzazione e della gestione del personale](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Opzione di configurazione per posizionare l'elenco Elementi di lavoro assegnati all'utente](https://docs.microsoft.com/dynamics365/human-resources/hr-whats-new-2020-09-03#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Aggiornamenti sulla conformità dell'Affordable Care Act (ACA) per il modulo 1095-C, il modulo 1095-B e la creazione di report elettronici nei benefit legacy | -- | -- | 
| La gestione dei benefit ora supporta il reporting di conformità ACA per le persone giuridiche con sede negli Stati Uniti | -- | [Genera report ACA nella gestione dei benefit](hr-benefits-management-aca-reports.md) |
| La gestione dei benefit ora ha livelli di tasso di benefit e entità di doppio livello di tasso di benefit esposti  | -- | -- |

### <a name="bug-fixes"></a>Correzioni di bug

Questa versione include le seguenti correzioni di bug.

> [!NOTE]
> Il nostro obiettivo è fornire queste informazioni il prima possibile. È possibile aggiornare questo argomento per includere correzioni di bug che sono state introdotte nella build dopo la pubblicazione iniziale di questo argomento.

| Numero problema | Uscita |  descrizione |
| --- | --- | --- |
| 533079 | Errore di navigazione "Il modulo è stato richiamato in modo errato" quando proviamo a esaminare le detrazioni. | Risolto errore durante la visualizzazione delle detrazioni sui benefit con vista **Ad oggi**. |
| 543641 | Il codice postale non viene compilato nella creazione dei report elettronici.  | Risolto un bug interno sul codice postale che non veniva visualizzato nei report elettronici ACA per la gestione dei benefit quando il codice di copertura è compreso tra M e Q. |
| 542815 | La schermata dei contatti personali in Dipendente self-service consente ai dipendenti di vedere i contatti personali degli altri. | Risolto errore in cui il modulo **Modifica** per i contatti personali self-service dei dipendenti non limita abbastanza la sua query da garantire che venga recuperato un solo contatto personale, consentendo a un utente di utilizzare le scorciatoie da tastiera per visualizzare i contatti di altre persone. |
| 536157 | Impossibile aprire la pagina **Integrazione Microsoft Dataverse** in Amministrazione di sistema a causa della chiamata IsVirtualEntityPackageInstalled(). | Il problema impedisce il caricamento della pagina **Integrazione di Microsoft Dataverse** in Human Resources. |
| 533079 | Errore di navigazione "Il modulo è stato richiamato in modo errato" quando proviamo a esaminare le detrazioni. | Risolto errore che si verificava quando si entra nel modulo **Detrazioni** per la gestione dei vantaggi quando visualizzato **Ad oggi**. |
| 537264 | Scheda **Informazioni personale** mancante dal record del candidato. | Le informazioni personali per il candidato sono ora disponibili nel record del candidato. |
| 537267 | **Esperienza professionale** non viene visualizzata nei record dei candidati interni. | La scheda **Esperienza professionale** ora visualizza i record dei candidati interni. In precedenza, se il candidato era interno, **Esperienza professionale** è stato sostituito da **Storico lavorativo**, che è la cronologia lavorativa del candidato all'interno dell'organizzazione. Entrambi sono applicabili e devono essere visualizzati per i candidati interni. |
| 537067 | **Autorizzato a contattare il datore di lavoro** non viene visualizzata. | Il comando **Autorizzato a contattare il datore di lavoro** è stato aggiunto al riquadro **Modifica esperienza professionale** per un record candidato. |
| 525957 | **Stato candidato** non si aggiorna sui candidati interni quando il trasferimento è stato completato. | Quando un trasferimento viene completato (il pulsante **Cambia posizione** o **Continua** è selezionato nella pagina **Trasferisci lavoratore a una nuova assegnazione di posizione**), lo **Stato** sul record del candidato deve essere modificata in **Assunto**. |
| 537051 | I simboli della valuta per la rupia indiana e la lira turca non si sincronizzano correttamente in Dataverse | I simboli della rupia indiana e della lira turca ora si sincronizzano correttamente in Dataverse. |
| 534846 | Le tabelle di reclutamento devono essere abilitate per Gestione dati. | Le nuove tabelle create per reclutare richieste e candidati sono ora abilitate per Gestione dati. Ciò consente di abilitare il rilevamento delle modifiche per le tabelle, abilitando il rilevamento delle modifiche OData nelle tabelle virtuali Dataverse. |
| 533474 | Correzione del riferimento mancante a Microsoft.SqlServer.XEvent.dll. | Le eccezioni di carico dell'assembly per Microsoft.SqlServer.XEvent.dll stavano bloccando le tabelle virtuali Dataverse dall'essere impostate in alcuni ambienti. |
| 481122 | L'area di lavoro **Persone** che mostra le posizioni in pensione. | Le posizioni in pensione erano visualizzate come posizioni aperte nell'area di lavoro **Persone**. Le posizioni in pensione non vengono più visualizzate. | 
| 541978 | Aggiungi l'indirizzo e-mail principale all'entità BaseWorker. | Questa modifica ha aggiunto l'indirizzo e-mail principale del lavoratore a HcmWorkerBaseEntity. |

## <a name="in-preview"></a>In anteprima

Le seguenti nuove funzionalità sono in anteprima. Per ulteriori informazioni su come attivare o disattivare le funzionalità, vedere [Gestire le funzionalità](hr-admin-manage-features.md).

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| App Human Resources in Microsoft Teams | [Esperienza di congedo e assenza dei dipendenti in Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [App Human Resources in Teams](https://go.microsoft.com/fwlink/?linkid=2127841)<br>[Gestire le richieste di congedo in Teams](hr-teams-leave-app.md) |
| Integrazione con LinkedIn Talent Hub | [Integrazione con LinkedIn Talent Hub](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [Integrazione con LinkedIn Talent Hub](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-linkedin) |
| Visualizzazione interaziendale del congedo per responsabili | [Visualizzazione interaziendale del congedo dei dipendenti per responsabili](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Configurare i parametri di congedo e assenza](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-parameters) |
|Fornire ulteriori informazioni dettagliate sui saldi dei congedi| [Fornire ulteriori informazioni dettagliate sui saldi dei congedi](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-into-leave-balances) | [Gestire il congedo dei dipendenti](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-manage-employee-leave) |
| I responsabili sono in grado di inviare richieste di selezione per le posizioni | [I responsabili possono inviare una richiesta di selezione per le posizioni aperte](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [Aggiungere una richiesta di selezione](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit#add-a-recruiting-request) |
| Profilo candidato migliorato in Gestione personale | [Profilo candidato migliorato in Gestione personale](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [Aggiungere o modificare un profilo candidato](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit#add-or-edit-a-candidate-profile) |
| Abilitare le integrazioni semplificate con i selezionatori | [Abilitare le integrazioni semplificate con i selezionatori](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [Selezione dei candidati](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit) |

## <a name="coming-soon"></a>Presto disponibili
| Funzionalità | Dettagli |
| --- | --- |
| Conferma tramite e-mail per le iscrizioni dei benefit | Questa funzione fornirà un'opzione per inviare un e-mail di conferma ai dipendenti quando effettuano il check-out dalle esperienze di registrazione dei vantaggi in self-service dei dipendenti. Per ulteriori informazioni, vedi [Configurare i parametri di gestione dei benefit per azienda](hr-benefits-setup-parameters-per-company.md). |
| Le competenze immesse da un manager per i propri dipendenti possono essere approvate automaticamente da un flusso di lavoro | Presto disponibili. |

Per un elenco completo delle funzionalità pianificate e delle relative versioni pianificate, vedere [Panoramica del secondo ciclo di rilascio del 2020 di Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="terminology-updates-for-microsoft-dataverse"></a>Aggiornamenti terminologici per Microsoft Dataverse

A partire da novembre 2020, Common Data Service è stato rinominato in [Microsoft Dataverse](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro). Vedi l'[ annuncio ufficiale](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/) sul blog Power Apps per saperne di più. Insieme a questo cambio di nome, è stata aggiornata un po 'di terminologia in Dataverse. Ad esempio, *entità* è ora *tabella* e *campo* è ora *colonna*. Per ulteriori informazioni, vedere [Aggiornamenti della terminologia](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro#terminology-updates).

In questa versione, la terminologia relativa all'integrazione Dynamics 365 Human Resources con Dataverse è stata aggiornata in tutta l'applicazione per riflettere questi cambiamenti. Ad esempio, il modulo **Integrazione Common Data Service** è ora **Integrazione Microsoft Dataverse**.

Per saperne di più sull'integrazione di Dynamics 365 Human Resources con Microsoft Dataverse, vedi [Configura integrazione Microsoft Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service) e [Configura tabelle virtuali di Microsoft Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica del secondo ciclo di rilascio del 2020 di Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
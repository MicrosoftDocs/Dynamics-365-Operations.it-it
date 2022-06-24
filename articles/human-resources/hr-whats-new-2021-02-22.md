---
title: Novità o modifiche in Dynamics 365 Human Resources (22 febbraio 2021)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 22 febbraio 2021.
author: marcelbf
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-02-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d07e73ccd922e9d52a9de9260577087a50ef1da4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897837"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-22-2021"></a>Novità o modifiche in Dynamics 365 Human Resources (22 febbraio 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo descrive le funzionalità nuove, modificate o future di Dynamics 365 Human Resources.

Per ulteriori informazioni sul processo di aggiornamento e pianificazione, vedere [Processo di aggiornamento](hr-admin-setup-update-process.md).

Per ulteriori informazioni sulle nuove funzionalità e sulle date di disponibilità generale previste, vedere [Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>In questa versione

Questa versione include le seguenti nuove funzionalità e correzioni di bug. Le modifiche si applicano alla build 8.1.3988.

### <a name="new-features"></a>Nuove funzionalità

Le seguenti funzioni sono generalmente disponibili con questa versione.

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| App Dynamics 365 Human Resources per Microsoft Teams | [Esperienza di congedo e assenza dei dipendenti in Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [App Human Resources in Teams](./hr-admin-teams-leave-app.md)<br>[Gestire le richieste di congedo in Teams](hr-teams-leave-app.md) |

### <a name="bug-fixes"></a>Correzioni di bug

Questa versione include le seguenti correzioni di bug.

> [!NOTE]
> Il nostro obiettivo è fornire queste informazioni il prima possibile. Potremmo aggiornare questo articolo per includere le correzioni di bug che sono state inserite nella build dopo che questo articolo è stato inizialmente pubblicato.

| Numero problema | Problema |  Description |
| --- | --- | --- |
| 529994 | La modifica del campo **Nome noto** nel modulo **Lavoratore** non attivava un aggiornamento di Dataverse | Risolto un problema in cui Dataverse non veniva aggiornato quando il campo **Nome noto** veniva aggiornato nel modulo **Lavoratore**. |
| 532651 | Il report PBI dell'analisi retributiva non utilizzava la conversione della valuta durante il calcolo delle metriche per tutte le società | Risolto un problema in cui il report PBI dell'analisi retributiva non eseguiva correttamente le conversioni di valuta. |
| 552226 | L'elaborazione di eventi reali chiudeva e riapriva i piani più volte per un singolo evento reale  | Risolto un problema in cui, in caso di presenza di un dipendente in più entità giuridiche e di evento reale, si aveva la generazione di un record evento reale per ogni entità giuridica in cui era presente il dipendente. Quando si elaborano eventi reali, è necessario selezionare la persona giuridica da elaborare. Tuttavia, la logica di elaborazione non si limita a questa persona giuridica. Esegue invece l'elaborazione per tutte le persone giuridiche e chiude e riapre i piani nella persona giuridica selezionata. Ciò genera un evento reale da elaborare più volte nella stessa persona giuridica, con molteplici chiusure/riaperture di ciascun piano interessato dall'evento reale. |
| 518064 | Un solo dipendente veniva selezionato nei piani ammissibili quando più dipendenti erano contrassegnati come beneficiari designati predefiniti | Risolto un problema in cui più beneficiari designati predefiniti non venivano selezionati automaticamente nei piani idonei. Ora è anche possibile designare un beneficiario principale per un contatto personale. Il beneficiario principale è elencato al 100% nei piani ammissibili quando sono presenti più beneficiari. |
| 552365 | I processi di esportazione Portare il proprio database (BYOD) non avevano esito positivo dopo l'aggiornamento 40 della piattaforma | Risolto un problema in cui le esportazioni BYOD non riuscivano dopo l'applicazione dell'aggiornamento 40 della piattaforma all'ambiente. |
| 547123 | Limite del numero di attività sottoposte a query nell'elenco delle cose da fare del dashboard | Il numero di attività mostrato nell'elenco delle cose da fare è ora limitato a 15 per risolvere un problema di prestazioni causato da un numero eccessivo di attività che vengono caricate. |

## <a name="in-preview"></a>In anteprima

Le seguenti nuove funzionalità sono in anteprima. Per ulteriori informazioni su come attivare o disattivare le funzionalità, vedere [Gestire le funzionalità](hr-admin-manage-features.md).

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| Visualizzazione interaziendale del congedo per responsabili | [Visualizzazione interaziendale del congedo dei dipendenti per responsabili](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Configurare i parametri di congedo e assenza](./hr-leave-and-absence-parameters.md) |
| Area di lavoro gestione benefit | [Area di lavoro Gestione benefit](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Area di lavoro gestione benefit](hr-benefits-management-workspace.md) |
| Impedire ai dipendenti di modificare i dettagli di contatto aziendali | [Impedire ai dipendenti di modificare i dettagli di contatto aziendali](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [Impedire la modifica delle informazioni personali](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>Presto disponibili

| Funzionalità | Dettagli |
| --- | --- |
| Le competenze immesse da un manager per i propri dipendenti possono essere approvate automaticamente da un flusso di lavoro | Presto disponibili. |

Per un elenco completo delle funzionalità pianificate e delle relative versioni pianificate, vedi [Panoramica del primo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="terminology-updates-for-microsoft-dataverse"></a>Aggiornamenti terminologici per Microsoft Dataverse

A partire da novembre 2020, Common Data Service è stato rinominato in [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Vedi l'[ annuncio ufficiale](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/) sul blog Power Apps per saperne di più. Con questa modifica del nome, è stata aggiornata una parte della terminologia in Dataverse. Ad esempio, *entità* è ora *tabella* e *campo* è ora *colonna*. Per ulteriori informazioni, vedere [Aggiornamenti della terminologia](/powerapps/maker/data-platform/data-platform-intro#terminology-updates).

In questa versione, la terminologia relativa all'integrazione Dynamics 365 Human Resources con Dataverse è stata aggiornata in tutta l'applicazione per riflettere questi cambiamenti. Ad esempio, il modulo **Integrazione Common Data Service** è ora **Integrazione Microsoft Dataverse**.

Per saperne di più sull'integrazione di Dynamics 365 Human Resources con Microsoft Dataverse, vedi [Configura integrazione Microsoft Dataverse](./hr-admin-integration-common-data-service.md) e [Configura tabelle virtuali di Microsoft Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).

## <a name="updates-to-service-deployment"></a>Aggiornamenti della distribuzione del servizio

A partire dalla versione del 22 febbraio 2021, modificheremo la distribuzione degli aggiornamenti del servizio regionale. Le modifiche includeranno la rotazione dell'ordine in cui le regioni globali ricevono gli aggiornamenti per il servizio Risorse umane e le modifiche nel tempo di attesa tra le fasi di aggiornamento. Queste modifiche consentono un allineamento con le procedure SDP (Safe Deployment Practices) per migliorare la stabilità, la qualità e il supporto del servizio.

Continueremo a seguire la cadenza di distribuzione di due settimane. Tuttavia, i clienti potrebbero notare che gli aggiornamenti vengono generalmente applicati ai loro ambienti delle risorse umane in un giorno diverso del ciclo di due settimane rispetto alle versioni precedenti.

Per ulteriori informazioni sul processo di aggiornamento del servizio, vedere [Processo di aggiornamento](./hr-admin-setup-update-process.md).

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica del primo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
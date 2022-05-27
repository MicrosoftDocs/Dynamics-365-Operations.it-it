---
title: Novità e modifiche in Dynamics 365 Human Resources 12 luglio 2021
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 12 luglio 2021.
author: marcelbf
ms.date: 07/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-07-12
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c01d00e7ede44c20e64fc4a8cd8646201caa3992
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686801"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-12-2021"></a>Novità e modifiche in Dynamics 365 Human Resources 12 luglio 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive le funzionalità nuove, modificate o presto disponibili in Dynamics 365 Human Resources.

Per ulteriori informazioni sul processo di aggiornamento e pianificazione, vedere [Processo di aggiornamento](hr-admin-setup-update-process.md).

Per ulteriori informazioni sulle nuove funzionalità e sulle date di disponibilità generale previste, vedere [Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>In questa versione

Questa versione include le seguenti nuove funzionalità e correzioni di bug. Le modifiche si applicano alla build 8.1.4353.

### <a name="new-features"></a>Nuove funzionalità

Le seguenti funzioni sono generalmente disponibili con questa versione.

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
|  Attivare/Disattivare la visualizzazione anni di servizio | |Questa funzione offre la possibilità di utilizzare date diverse per calcolare gli anni di servizio visualizzati nella pagina **Inserimento dipendenti semplificato** e nella pagina **Persone**.  Questo sarà disponibile nei [parametri Human Resources](/dynamics365/human-resources/hr-setup-parameters). |


### <a name="bug-fixes"></a>Correzioni di bug

Questa versione include le seguenti correzioni di bug.

> [!NOTE]
> Il nostro obiettivo è fornire queste informazioni il prima possibile. È possibile aggiornare questo argomento per includere correzioni di bug che sono state introdotte nella build dopo la pubblicazione iniziale di questo argomento.

| Numero problema | Problema |  descrizione |
| --- | --- | --- |
| 595871 | Il riquadro Informazioni in Human Resources ha una terminologia Dataverse non corretta | Con il rebranding di Common Data Service in Dataverse, la terminologia è stata aggiornata nel riquadro informazioni di Microsoft Dynamics 365 Human Resources (**Aiuto e supporto > Informazioni**). |
| 598676 | Il modulo di inserimento dipendenti semplificato che sovrascrive l'attività può creare un errore se utilizzato con la visualizzazione salvata| Nella pagina **Lavoratore** se la funzione "Inserimento dipendenti semplificato" è attivata, l'applicazione potrebbe non riuscire se **Sempre aperto per la modifica** è impostato sulla vista salvata. |
| 592344 |La sezione relativa ai compensi dei lavoratori nella posizione deve essere letta solo quando è abilitata la gestione dei benefit | Le informazioni sui compensi dei lavoratori vengono create utilizzando la funzionalità dei benefit legacy.  Quando la gestione dei benefit è abilitata, i campi saranno di sola lettura. Quando la gestione dei benefici è attivata e **Nascondi i moduli dei benefit legacy** è impostato su **sì** nei parametri condivisi HR, la scheda **Retribuzione lavoratori** sarà nascosta. |
| 598617 | La scheda di attivazione del modulo **HcmDiscussion** provoca un ciclo infinito quando vengono applicate le personalizzazioni | Quando sia la griglia che la visualizzazione dei dettagli hanno **Sempre aperto per la modifica** attivato, il codice che attiva la scheda nel metodo dell'attività sovrascritta è in conflitto con la personalizzazione su quale controllo deve avere lo stato attivo e crea un ciclo infinito. |
| 593553 | Il campo della data del giornale di registrazione nel giornale di registrazione delle prestazioni viene visualizzato in UTC | Il campo **Data giornale di registrazione** per i giornali di registrazione delle prestazioni viene visualizzato nel fuso orario UTC anziché nel fuso orario definito nell'impostazione della data di sistema, causando l'errata data per alcuni fusi orari. |
| 586930 | L'apertura delle attività per obiettivi di prestazione apre un record completamente diverso | Quando la funzione "Visualizzazione report estesi Giornali di registrazione prestazioni" è abilitata in Gestione funzioni, selezionando gli obiettivi di prestazione per i report estesi nella scheda **Team personale** in **Self-service dipendenti** apre gli obiettivi per un dipendente invece del dipendente selezionato. |
| 569959 |  L'entità HcmPositionWorkerAssignmentV2 non assegna un lavoratore a una posizione | Gli utenti hanno ricevuto un errore durante l'aggiunta di un record di assegnazione della posizione tramite l'entità e la pubblicazione non è riuscita. |
| 582259 | Il report VETS 4212 utilizza il modulo 2017 anziché il modulo 2020 | Aggiornato al formato 2020.  Per caricare il nuovo formato, vai in **Configurazioni report** ed elimina il report VETS-4212 nella colonna di sinistra. Vai in **Creazione di report elettronici - Repository - Risorse HR** e seleziona **Apri**.  Seleziona **VETS-4212 stampa PDF** e poi seleziona **Importa**.|


## <a name="in-preview"></a>In anteprima

Le seguenti nuove funzionalità sono in anteprima. Per ulteriori informazioni su come attivare o disattivare le funzionalità, vedere [Gestire le funzionalità](hr-admin-manage-features.md).

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| Area di lavoro gestione benefit | [Area di lavoro Gestione benefit](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Area di lavoro gestione benefit](hr-benefits-management-workspace.md) |
| Abilitare l'integrazione delle retribuzioni semplificata (API di integrazione delle retribuzioni) | [Abilitare l'integrazionei semplificata con i fornitori retribuzioni](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md)|
|  Consentire a un responsabile dei congedi di gestire le ferie | [Consentire a un responsabile dei congedi di gestire le ferie](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | [Configurare il ruolo di responsabile dei congedi](https://go.microsoft.com/fwlink/?linkid=2168107)|
|  Configurare il requisito per l'allegato per tipo di congedo | [Configurare il requisito per l'allegato per tipo di congedo](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[Configurare i tipi di congedo e assenza](https://go.microsoft.com/fwlink/?linkid=2168108)|
|  Configurare le unità di congedo per tipo di congedo | [Configurare le unità di congedo per tipo di congedo](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[Configurare i tipi di congedo e assenza](https://go.microsoft.com/fwlink/?linkid=2168215)|
| Consentire ai dipendenti di essere contrassegnati come pronti per essere pagati | [Consentire ai dipendenti di essere contrassegnati come pronti per essere pagati](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Pronto per il pagamento](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>Presto disponibile

| Funzionalità | Dettagli |
| --- | --- |
| Platform Update 10.0.20 (44) | L'implementazione dell'aggiornamento della piattaforma 10.0.20 inizierà con la versione di servizio il 26 luglio 2021. Per ulteriori informazioni, vedi [Aggiornamenti della piattaforma per la versione 10.0.20 delle app per finanza e operazioni (agosto 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20). |

Per un elenco completo delle funzionalità pianificate e delle relative versioni pianificate, vedi [Panoramica del primo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica del primo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

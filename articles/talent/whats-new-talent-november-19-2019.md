---
title: Novità o modifiche in Dynamics 365 Talent (19 novembre 2019)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 11/19/2019
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
ms.search.validFrom: 2019-11-19
ms.dyn365.ops.version: Talent
ms.openlocfilehash: aa984a01e9da30e6da07516fa2986833366a882b
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527146"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-november-19-2019"></a>Novità o modifiche in Dynamics 365 Talent (19 novembre 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo articolo descrive le funzionalità nuove o modificate in Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifiche in Onboard

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR

Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2621. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Microsoft Dynamics Lifecycle Services (LCS).

### <a name="platform-update-31-for-finance-and-operations-apps"></a>Update 31 della piattaforma per le app Finance and Operations

Per ulteriori informazioni, vedere [Funzionalità di anteprima nell'aggiornamento 31 della piattaforma per le app Finance and Operations (gennaio 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-31).

### <a name="feature-management-workspace-383856"></a>Area di lavoro Gestione funzionalità (383856)

L'area di lavoro **Gestione funzionalità** fornisce l'elenco delle funzionalità offerte in ciascuna versione. Per impostazione predefinita, le nuove funzionalità sono disabilitate. È possibile utilizzare l'area di lavoro per accendere alle funzionalità e visualizzare la documentazione correlata. Per ulteriori informazioni sulla gestione funzionalità, vedere [Panoramica della gestione funzionalità](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Tutte le nuove funzionalità rimangono in anteprima per almeno 30 giorni e in genere per 30-60 giorni. Le principali funzionalità sono generalmente disponibili in ottobre e aprile di ogni anno successivo al periodo di anteprima. Non appena nuove funzioni sono presenti nell'area di lavoro **Gestione funzionalità**, è possibile attivarle. Alcune funzionalità possono essere attive per impostazione predefinita.
 
Talvolta, una funzionalità integrale viene attivata per impostazione predefinita e non può essere disattivata, ad esempio l'area di lavoro **Gestione funzionalità**.
 
Una volta che una funzionalità è generalmente disponibile, può essere attivata o disattivata negli ambienti di produzione. L'area di lavoro **Gestione funzionalità** indica quando una funzionalità di anteprima diventa obbligatoria. Questa data è in genere il 1° ottobre o il 1° aprile in base ai piani di rilascio semestrali. Non è possibile disattivare le funzionalità obbligatorie. Finché non diventa obbligatoria, è possibile attivare e disattivare una funzionalità in tutti gli ambienti.

### <a name="message-appears-when-canceled-action-exists-for-a-position-382887"></a>Il messaggio viene visualizzato quando l'azione annullata è presente per una posizione (382887)

Il seguente messaggio non viene più visualizzato quando si seleziona una posizione specifica e un'azione annullata è tutto ciò che è disponibile per la posizione: **Per la posizione xxxxxx è in corso un'azione non ancora completata**.

### <a name="in-learning-analytics-the-course-type-and-status-display-incorrect-data-381151"></a>Nell'analisi di apprendimento, il tipo di corso e lo stato visualizzano dati errati (381151)

La versione di questa settimana aggiorna l'analisi di apprendimento in modo da visualizzare correttamente **Tipo di corso** e **Stato**.

### <a name="personnel-number-should-display-in-the-new-worker-form-banner-383832"></a>Il numero dipendente deve essere visualizzato nel banner del modulo nuovo lavoratore (383832)

Nel modulo **Nuovo lavoratore**, il **Numero dipendente** ora viene visualizzato nel banner per riferimento rapido.

### <a name="position-start-date-determines-the-job-record-to-use-when-retrieving-a-compensation-level-during-hire-350361"></a>La data di inizio della posizione determina il record di lavoro da utilizzare quando si recupera un livello di retribuzione durante l'assunzione (350361)

In questa versione, **Data di inizio retribuzione** determina il livello assegnato al nuovo lavoro.

### <a name="custom-pick-list-fields-in-the-position-table-arent-synchronized-to-common-data-service-387503"></a>I campi personalizzati di elenco di prelievo nella tabella di posizione non vengono sincronizzati in Common Data Service (387503)

In questa versione, gli articoli degli elenchi di prelievo vengono sincronizzati con Common Data Service.

### <a name="worker-address-entity-doesnt-synchronize-with-common-data-service-while-importing-new-data-349673"></a>L'entità indirizzo del lavoratore non viene sincronizzata con Common Data Service durante l'importazione dei nuovi dati (349673)

Nella versione di questa settimana, i dati dell'indirizzo ora vengono sincronizzate con Common Data Service durante l'importazione dei nuovi dati.

## <a name="in-preview"></a>In anteprima

### <a name="print-performance-reviews"></a>Stampare le valutazioni delle prestazioni

Vedere [Stampare le valutazioni delle prestazioni](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) nel piano della seconda ondata di rilascio di Dynamics 365: 2019.

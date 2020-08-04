---
title: Novità o modifiche in Dynamics 365 Human Resources (18 febbraio 2020)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 60b46f5bd8f5eeae8aedc9bf81f1e7892caa0c93
ms.sourcegitcommit: bd9ff0d28718d535356ffbe1cffaaf60310dd430
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2020
ms.locfileid: "3555341"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-18-2020"></a>Novità o modifiche in Dynamics 365 Human Resources (18 febbraio 2020)

Questo articolo descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources. Le modifiche si applicano alla build 8.1.2903. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in LCS per riferimento.

## <a name="platform-update-32"></a>Update 32 della piattaforma 

L'update 32 della piattaforma è ora disponibile. Per ulteriori informazioni, vedere [Novità o modifiche introdotte nell'update 32 della piattaforma per app Finance and Operations (febbraio 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32).

## <a name="search-values-are-remembered-when-changing-view-options-in-streamlined-employee-form-383833"></a>I valori di ricerca vengono memorizzati quando si modificano le opzioni di visualizzazione nel modulo dipendente semplificato (383833)

Il nuovo modulo **Lavoratore** ora memorizza i valori di ricerca quando si cambiano le opzioni di visualizzazione e si applicano le modifiche.

## <a name="compensation-management-summary-tiles-in-preview-feature-redirect-to-wrong-form-401861"></a>I riquadri di riepilogo della gestione retribuzioni nella funzione di anteprima reindirizzano al modulo errato (401861)

I riquadri della gestione retribuzioni fissa e variabile ora visualizzano i record corretti nel nuovo modulo **Lavoratore**. Si applica solo alla funzione di anteprima del modulo dipendente semplificato. È possibile abilitare questa funzione di anteprima in **Gestione funzionalità**. Per ulteriori informazioni, vedere [Gestire le funzionalità](hr-admin-manage-features.md).

## <a name="empty-status-field-for-some-leave-request-records-in-common-data-service-414915"></a>Campo di stato vuoto per alcuni record di richiesta di congedo in Common Data Service (414.915)

Questa modifica risolve un problema in Common Data Service quando il campo **Stato** in una richiesta di congedo è impostato su **Revisione**. Common Data Service ora riflette lo stato.

## <a name="skill-gap-analysis-only-possible-for-assigned-job-411390"></a>Analisi lacuna competenze possibile solo per il lavoro assegnato (411390)

È ora possibile eseguire un'analisi lacuna competenze su qualsiasi lavoro definito in Human Resources.

## <a name="system-currency-doesnt-sync-from-common-data-service-to-human-resources-in-new-environments-418011"></a>La valuta di sistema non si sincronizza da Common Data Service in Human Resources in nuovi ambienti (418011)

La valuta di sistema in Common Data Service ora si sincronizza con Human Resources.

## <a name="in-preview"></a>In anteprima

- [Funzionalità di anteprima di Congedo e assenza](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)

- [Funzionalità di anteprima della gestione dei benefit](hr-benefits-management-overview.md)

## <a name="coming-soon"></a>Presto disponibili

### <a name="updated-common-data-service-solution"></a>Soluzione Common Data Service aggiornata

Una nuova soluzione Common Data Service sarà presto disponibile con le seguenti modifiche:

| Descrizione | Modifica |
| ----------------------------------------- | --- |
| Modifiche all'entità **Posizione lavorativa** | Aggiunta di **Paese di retribuzione**</br>Aggiunta di **Dimensioni finanziarie** |
| Modifiche all'entità **Lavoratore** | Aggiunta di **Sequenza nome**</br>Aggiunta di **Lavora da casa**</br>Aggiunta di **Lingua**</br>Aggiunta di **Data di anzianità**</br>Aggiunta di **Data di ricorrenza annuale**</br>Aggiunta di **Data di assunzione originale** |
| Modifiche all'entità **Impiego** | Aggiunta di **Dimensioni finanziarie**</br>Aggiunta di **Motivo fine rapporto**</br>**Data di transizione** rinominata in **Data fine rapporto**</br>Aggiunta di **Date periodo di prova** |
| Modifiche all'entità **Indirizzo lavoratore** | Aggiunta di **Nome della via**</br>**Riga indirizzo 1**, **Riga indirizzo 2** e **Riga indirizzo 3** contrassegnate per deprecamento |
| Nuove entità di impostazione della retribuzione variabile | **Tipo di piano di retribuzione variabile**</br>**Piano di retribuzione variabile**</br>**Regole distribuzione incentivi**</br>**Livello del piano di retribuzione variabile** |
| Nuova entità **Impiego calendario lavoratore** | Aggiunta di **Entità calendario lavoro** |
| Nuova entità **Dettagli posizione di retribuzione** | Aggiunta di **Dettagli posizione di retribuzione** |
| Nuova entità **Titolo** | Aggiunta di **Titolo**. La nuova entità **Titolo** sarà inclusa nel processo di sincronizzazione tra Human Resources e Common Data Service. Inizialmente non vi verrà fatto riferimento dalle entità **Posizione lavorativa** o **Posizione**. |

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)
---
title: Novità o modifiche in Dynamics 365 Talent (23 ottobre 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/23/2019
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
ms.search.validFrom: 2019-10-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 27cb4a7c125cb2b330dff083c8ed0c1ee89c0e7e
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528005"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-23-2019"></a>Novità o modifiche in Dynamics 365 Talent (23 ottobre 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract
Questa versione include correzioni di bug minori per Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifiche in Onboard
Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR

Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2569. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Microsoft Dynamics Lifecycle Services (LCS).

### <a name="platform-update-30-for-finance-and-operations-apps"></a>Update 30 della piattaforma per le app Finance and Operations

Per ulteriori informazioni, vedere [Novità o modifiche introdotte nell'aggiornamento 30 della piattaforma per app Finance and Operations (novembre 2019)](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/whats-new-platform-update-30).

### <a name="remove-benefits-open-enrollment-preview-feature"></a>Rimuovere la funzionalità di anteprima dell'iscrizione aperta ai vantaggi

In concomitanza con l'annuncio nel [post di blog sugli investimenti strategici in Core HR per promuovere l'eccellenza operativa](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence), Microsoft rimuove la funzionalità di iscrizione aperta ai vantaggi dall'anteprima pubblica il 18 ottobre 2019. Nuove funzionalità verranno rilasciate in futuro. L'utilizzo in produzione della funzione di iscrizione aperta ai vantaggi attualmente in anteprima pubblica non sarà supportato.

### <a name="error-while-selecting-the-countryregion-on-the-worker-form-a-second-time-350294"></a>Errore durante la selezione del paese o dell'area geografica nel modulo Lavoratore una seconda volta (350294)

Con la versione di questa settimana, il problema è stato corretto quando si seleziona un paese o un'area geografica nel modulo **Lavoratore**.

### <a name="financial-dimension-values-default-to-the-combination-display-field-when-do-not-allow-manual-entry-is-set-to-true-340097"></a>I valori della dimensione finanziaria vengono impostati automaticamente sul campo Visualizzazione combinazione quando Non consentire l'inserimento manuale è impostato su true (340097)

Con questa modifica, quando si impostano le dimensioni finanziarie e si utilizza l'opzione per non consentire l'immissione manuale, il sistema imposterà correttamente il valore della dimensione predefinita nel campo **Visualizzazione combinazione**.

### <a name="new-relationship-types-should-be-added-to-relationship-lookup-in-the-personal-contacts-form-347691"></a>Nuovi tipi di relazione devono essere aggiunti alla ricerca Relazione nel modulo dei contatti personali (347691)

Questa versione include nuove funzionalità per aggiungere nuovi tipi di relazione nella tabella **Tipi di relazione** e riflettere tali cambiamenti nella ricerca delle relazioni per i contatti personali.

### <a name="additional-list-values-in-custom-fields-arent-reflected-in-common-data-service-379599"></a>I valori di elenco aggiuntivi nei campi personalizzati non vengono riflessi in Common Data Service (379599)

Con la versione di questa settimana, aggiungendo un nuovo valore di elenco a un campo personalizzato esistente che è già sincronizzato con Common Data Service, i nuovi valori dell'elenco di selezione vengono ora visualizzati dopo aver applicato le modifiche all'entità.

### <a name="on-the-terms-of-employment-page-all-employees-terms-of-employment-appear-after-selecting-open-in-excel-348073"></a>Nella pagina Condizioni di impiego, tutte le condizioni di impiego dei dipendenti vengono visualizzate dopo aver selezionato Apri in Excel (348073)

Con questa versione, in Excel verranno aperti solo le condizioni di impiego dei dipendenti selezionati. Anche tutta la sicurezza aziendale è rispettata.

### <a name="the-association-between-the-work-calendar-holiday-entity-and-the-work-calendar-entity-is-missing-in-common-data-service-324178"></a>Manca l'associazione tra l'entità festività del calendario di lavoro e l'entità del calendario di lavoro in Common Data Service (324178)

Questa relazione è stata aggiunta alla versione. Questa modifica consentirà di visualizzare i giorni lavorativi di un dipendente in PowerApps. 

### <a name="error-when-using-employee-self-service-workflows-with-configurable-hierarchies-370132"></a>Errore durante l'utilizzo di flussi di lavoro self-service dei dipendenti con gerarchie configurabili (370132)

In questa versione, sono disponibili migliori indicazioni su come configurare i flussi di lavoro usando gerarchie configurabili. 

### <a name="system-allows-creation-of-new-positions-where-the-available-for-assignment-date-is-earlier-than-the-activation-date-340103"></a>Il sistema consente la creazione di nuove posizioni in cui la data di assegnazione disponibile è precedente alla data di attivazione (340103)

Questa modifica visualizzerà un avviso quando la data **Disponibile per assegnazione** è precedente alla data **Attivazione** della posizione.

## <a name="coming-soon"></a>Presto disponibili

### <a name="print-performance-reviews"></a>Stampare le valutazioni delle prestazioni

Vedere [Stampare le valutazioni delle prestazioni](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) nel piano della seconda ondata di rilascio di Dynamics 365: 2019.

### <a name="feature-management-workspace"></a>Area di lavoro Gestione funzionalità

Le funzionalità vengono aggiunte e aggiornate in ogni versione. L'esperienza di gestione delle funzionalità offre un'area di lavoro in cui è possibile visualizzare un elenco delle funzionalità incluse in ciascuna versione. Per impostazione predefinita, le nuove funzionalità sono disabilitate. È possibile utilizzare l'area di lavoro per accendere alle funzionalità e visualizzare la documentazione correlata.

Per ulteriori informazioni sulle modifiche fornite con la gestione delle funzionalità, vedere [Panoramica della gestione funzionalità](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

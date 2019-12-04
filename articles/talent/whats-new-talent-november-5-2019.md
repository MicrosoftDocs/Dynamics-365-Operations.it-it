---
title: Novità o modifiche in Dynamics 365 Talent (5 novembre 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 11/05/2019
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
ms.search.validFrom: 2019-11-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e6a81209c3c4a95ee51668533d40d4aecc1d58b9
ms.sourcegitcommit: a46fb06138f7f82e973dca3157d30f9b21d3a70b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2019
ms.locfileid: "2778384"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-november-5-2019"></a>Novità o modifiche in Dynamics 365 Talent (5 novembre 2019)

[!include [banner](includes/banner.md)]

Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifiche in Onboard

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR

Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2598. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Microsoft Dynamics Lifecycle Services (LCS).

### <a name="copy-a-core-hr-instance"></a>Copiare un'istanza Core HR

Nella versione di questa settimana, è possibile utilizzare Microsoft Dynamics Lifecycle Services (LCS) per copiare un database di Microsoft Dynamics 365 Talent: Core HR in un ambiente sandbox. Se è disponibile un altro ambiente sandbox, è anche possibile copiare il database da tale ambiente in un ambiente sandbox di destinazione. Per ulteriori informazioni, vedere:

- [Gestione dell'ambiente più ampia](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/broader-environment-management) nel piano della seconda ondata di rilascio di Dynamics 365: 2019.

- Documentazione [Copiare un'istanza Core HR](hr-copy-instance.md) in Talent

### <a name="common-data-service-integration-batch-jobs-arent-created-when-common-data-service-integration-is-enabled-388030"></a>I processi batch di integrazione di Common Data Service non vengono creati quando l'integrazione Common Data Service è attivata (388030)

Questa modifica crea i processi batch per l'integrazione di Common Data Service quando è abilitata.

### <a name="the-hcmpersonimageentity-doesnt-resize-the-person-image-when-uploaded-369469"></a>HcmPersonImageEntity non ridimensiona l'immagine della persona quando viene caricata (369469)

La versione di questa settimana modifica il modo in cui le immagini vengono ridimensionate per migliorare le prestazioni quando importate tramite la gestione dei dati.

### <a name="a-positions-available-for-assignment-date-can-be-earlier-than-the-activation-date-340103"></a>Una posizione disponibile per la data di assegnazione può essere precedente alla data di attivazione (340103)

Con questa modifica, verrà visualizzato un avviso se si seleziona una **data disponibile per l'assegnazione** precedente alla **data di attivazione**della posizione.

### <a name="cant-create-a-compensation-change-request-in-employee-self-service-for-step-based-plans-376872"></a>Impossibile creare una richiesta di modifica di retribuzione nel self-service dei dipendenti per piani basati su passaggi (376872)

Questa versione corregge un problema quando si richiede la modifica della retribuzione tramite Self Service dipendenti per i piani basati su passaggi. 

### <a name="reason-code-doesnt-sync-to-common-data-service-if-the-description-is-longer-than-30-characters-core-hr-allows-60-352682"></a>Il codice motivo non viene sincronizzato in Common Data Service se la descrizione è più lunga di 30 caratteri, Core HR consente 60 (352682)

Con questa modifica, i codici motivo con più di 30 caratteri verranno aggiornati in Common Data Service. Le modifiche apportate in Common Data Service vengono applicate anche in Talent.

### <a name="address-integration-from-talent-to-finance-and-operations-351961"></a>Gestire l'integrazione da Talent in Finance and Operations (351961)

Questa versione risolve un problema a causa del quale gli indirizzi aggiornati in Talent non venivano aggiornati in Finance and Operations. Le modifiche apportate ai blocchi di indirizzi ora vengono aggiornate.

## <a name="coming-soon"></a>Presto disponibili

### <a name="print-performance-reviews"></a>Stampare le valutazioni delle prestazioni

Vedere [Stampare le valutazioni delle prestazioni](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) nel piano della seconda ondata di rilascio di Dynamics 365: 2019.

### <a name="feature-management-workspace"></a>Area di lavoro Gestione funzionalità

Le funzionalità vengono aggiunte e aggiornate in ogni versione. L'esperienza di gestione delle funzionalità offre un'area di lavoro in cui è possibile visualizzare un elenco delle funzionalità incluse in ciascuna versione. Per impostazione predefinita, le nuove funzionalità sono disabilitate. È possibile utilizzare l'area di lavoro per accendere alle funzionalità e visualizzare la documentazione correlata.

Per ulteriori informazioni sulle modifiche fornite con la gestione delle funzionalità, vedere [Panoramica della gestione funzionalità](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

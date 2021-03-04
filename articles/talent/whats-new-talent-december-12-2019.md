---
title: Novità o modifiche in Dynamics 365 Talent (10 dicembre 2019)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 12/10/2019
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
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 18f86f5d87b780d5d4ffc83330d389077987dda6
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528173"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-december-10-2019"></a>Novità o modifiche in Dynamics 365 Talent (10 dicembre 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifiche in Onboard

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR

Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2660. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Microsoft Dynamics Lifecycle Services (LCS).

### <a name="feature-management-workspace"></a>Area di lavoro Gestione funzionalità

L'area di lavoro **Gestione funzionalità** fornisce l'elenco delle funzionalità offerte in ciascuna versione. Per impostazione predefinita, le nuove funzionalità sono disabilitate. È possibile utilizzare l'area di lavoro per accendere alle funzionalità e visualizzare la documentazione correlata. Per ulteriori informazioni sulla gestione funzionalità, vedere [Panoramica della gestione funzionalità](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Tutte le nuove funzionalità rimangono in anteprima per almeno 30 giorni e in genere per 30-60 giorni. Le principali funzionalità sono generalmente disponibili in ottobre e aprile di ogni anno successivo al periodo di anteprima. Non appena nuove funzioni sono presenti nell'area di lavoro **Gestione funzionalità**, è possibile attivarle. Alcune funzionalità possono essere attive per impostazione predefinita.
 
Talvolta, una funzionalità integrale viene attivata per impostazione predefinita e non può essere disattivata, ad esempio l'area di lavoro **Gestione funzionalità**.
 
Una volta che una funzionalità è generalmente disponibile, può essere attivata o disattivata negli ambienti di produzione. L'area di lavoro **Gestione funzionalità** indica quando una funzionalità di anteprima diventa obbligatoria. Questa data è in genere il 1° ottobre o il 1° aprile in base ai piani di rilascio semestrali. Non è possibile disattivare le funzionalità obbligatorie. Finché non diventa obbligatoria, è possibile attivare e disattivare una funzionalità in tutti gli ambienti.

### <a name="streamlined-worker-form-has-moved-to-the-feature-management-workspace-390583"></a>Il modulo di lavoro semplificato è stato spostato nell'area di lavoro Gestione funzionalità (390583)

Con questa modifica, ora è possibile abilitare il modulo di lavoro semplificato nell'area di lavoro **Gestione funzionalità**. Questa funzione è stata spostata dal modulo **Parametri di sistema** in **Amministrazione di sistema**.

### <a name="prevent-hcmworkerpayrollinfo-records-from-being-written-without-a-worker-value-394526"></a>Impedire la scrittura dei record HcmWorkerPayrollInfo senza un valore lavoratore (394526)

Con questa versione, i record **HcmWorkerPayrollInfo** non vengono più creati senza riferimento lavoratore in questo scenario. 

### <a name="message-log-associated-to-the-action-isnt-populated-when-the-action-fails-to-complete-374007"></a>Il registro messaggi associato all'azione non viene popolato quando l'operazione non viene completata (374007)

Questa versione include una modifica per popolare il registro dei messaggi di azione quando un'azione non riesce in determinati scenari. 

### <a name="common-data-service-integration-batch-job-creation-388030"></a>Creazione di processi batch di integrazione di Common Data Service (388030)

Con questa modifica, i processi batch per l'integrazione di Common Data Service vengono creati quando il servizio è abilitato.

### <a name="additional-pick-list-values-to-custom-fields-arent-reflected-in-common-data-service-after-clicking-apply-on-the-custom-fields-form-379599"></a>I valori aggiuntivi della distinta di prelievo nei campi personalizzati non vengono riflessi in Common Data Service quando si fa clic su Applica nel modulo Campi personalizzati (379599)

Con questa modifica, i nuovi valori della distinta di prelievo immessi in Talent sono ora sincronizzati con Common Data Service quando vengono applicate le modifiche.

### <a name="update-to-common-data-service-for-then-leave-bank-transaction-entity-turns-into-an-insert-on-talent-side-352938"></a>L'aggiornamento dell'entità per la transazione bancaria di congedo di Common Data Service viene convertito in un inserimento sul lato Talent (352938)

Questa modifica risolve un problema per cui un aggiornamento di una transazione di congedo bancario crea un nuovo record in Talent.

## <a name="in-preview"></a>In anteprima

Le funzionalità di anteprima sono disponibili solo negli ambienti **sandbox**.

### <a name="print-performance-reviews"></a>Stampare le valutazioni delle prestazioni

Vedere [Stampare le valutazioni delle prestazioni](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) nel piano della seconda ondata di rilascio di Dynamics 365: 2019.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
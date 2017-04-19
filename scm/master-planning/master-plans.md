---
title: Piani generali
description: "Utilizzare i vari piani generali per supportare le attività lavorative giornaliere della società, simulare diverse strategie di pianificazione che si desidera monitorare e implementare i criteri aziendali, ad esempio i criteri relativi alle prestazioni o la soddisfazione dei clienti interna."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqParameters, ReqPlanSched
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 7911
ms.assetid: a116b7de-3d6d-4321-87ba-5a5d99c2f64e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 29bb560c11e63938bea73ed8471c27563b546f8f
ms.lasthandoff: 03/31/2017


---

# <a name="master-plans"></a>Piani generali

Utilizzare i vari piani generali per supportare le attività lavorative giornaliere della società, simulare diverse strategie di pianificazione che si desidera monitorare e implementare i criteri aziendali, ad esempio i criteri relativi alle prestazioni o la soddisfazione dei clienti interna. 

È possibile configurare i piani generali nella pagina **Piani generali**.

Sono disponibili due tipi di piano:
-   **Piano statico**: per il calcolo della pianificazione generale vengono utilizzati i dati correnti per generare un piano del fabbisogno netto. Questo piano rimane invariato fino alla successiva esecuzione della pianificazione generale. Si tratta di un piano operativo che può essere utilizzato dal personale della società a vari livelli, ad esempio un acquirente o un addetto alla pianificazione della produzione, come base per le decisioni e per lo svolgimento dei compiti e delle attività giornalieri.
-   **Piano dinamico**: questo piano viene avviato con lo stesso piano del fabbisogno netto generato dalla pianificazione generale. È tuttavia possibile aggiornare il piano dinamico ogni volta che i dati master vengono modificati. È tuttavia possibile aggiornare il piano dinamico ogni volta che vengono modificati i dati generali, ad esempio quando si crea un nuovo ordine cliente. In questo modo è possibile monitorare la rete di ordini e la disponibilità di articoli senza interferire con il piano statico utilizzato da altri dipendenti per i processi lavorativi.

Una società può scegliere di utilizzare semplicemente un piano dinamico o il piano statico e il piano dinamico. È inoltre possibile configurare qualsiasi piano generale per riflettere una particolare strategia o risolvere un problema. Di seguito sono elencati gli esempi disponibili:
-   Impostare livelli di scorte più elevati per evitare esaurimenti di scorte.
-   Impostare margini di sicurezza più ampi per proteggersi da fornitori inaffidabili.

È inoltre possibile impostare il piano dinamico iniziale in modo che venga aggiornato con il nuovo piano del fabbisogno ogni volta che si esegue la pianificazione generale. È possibile specificare le impostazioni nella pagina **Parametri di pianificazione generale**.



<a name="see-also"></a>Vedere anche
--------

[Impostazioni copertura](coverage-settings.md)

[Separando pianificazione tattica e operative per la programmazione generale (http://blogs.msdn.com/b/axmfg/archive/2012/10/12/separating-tactical-and-operative-planning-for-master-scheduling.aspx)]

[Pianificazione generale: Utilizzare un piano generale statico e dinamico o utilizzare un piano?] (https://community.dynamics.com/ax/b/msdynaxlessonslearned/archive/2014/01/16/master-planning-use-a-static-and-dynamic-master-plan-or-use-one-plan)


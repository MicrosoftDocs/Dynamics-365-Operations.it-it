---
title: Panoramica dei piani generali
description: Utilizzare vari piani generali per supportare le attività lavorative giornaliere della società, simulare diverse strategie di pianificazione da sottoporre a monitoraggio e implementare i criteri aziendali, ad esempio i criteri relativi alle prestazioni interne o alla soddisfazione dei clienti.
author: t-benebo
ms.date: 05/28/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ReqParameters, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "7911"
- intro-internal
ms.assetid: a116b7de-3d6d-4321-87ba-5a5d99c2f64e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1b3d30d9ef2f08c2cb7b2ca022ff1a816567a247
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2022
ms.locfileid: "8468757"
---
# <a name="master-plans-overview"></a>Panoramica dei piani generali

[!include [banner](../includes/banner.md)]

Utilizzare vari piani generali per supportare le attività lavorative giornaliere della società, simulare diverse strategie di pianificazione da sottoporre a monitoraggio e implementare i criteri aziendali, ad esempio i criteri relativi alle prestazioni interne o alla soddisfazione dei clienti.

È possibile configurare i piani generali nella pagina **Piani generali**.

Sono disponibili due tipi di piano:

- **Piano statico**: per il calcolo della pianificazione generale vengono utilizzati i dati correnti per generare un piano del fabbisogno netto. Questo piano rimane invariato fino alla successiva esecuzione della pianificazione generale o alla successiva modifica manuale del piano. Questo è un piano operativo che può essere utilizzato dal personale della società a vari livelli, ad esempio un acquirente o un addetto alla pianificazione della produzione, come base per le decisioni e per lo svolgimento delle attività giornaliere.
- **Piano dinamico**: questo piano viene avviato con lo stesso piano del fabbisogno netto generato dalla pianificazione generale. È tuttavia possibile aggiornare il piano dinamico ogni volta che i dati master vengono modificati. È tuttavia possibile aggiornare il piano dinamico ogni volta che vengono modificati i dati generali, ad esempio quando si crea un nuovo ordine cliente. In questo modo è possibile monitorare la rete di ordini e la disponibilità di articoli senza interferire con il piano statico utilizzato da altri dipendenti per i processi lavorativi.

Una società può scegliere di utilizzare semplicemente un piano dinamico o il piano statico e il piano dinamico. È inoltre possibile configurare qualsiasi piano generale per riflettere una particolare strategia o risolvere un problema. Di seguito sono elencati gli esempi disponibili:

- Impostare livelli di scorte più elevati per evitare esaurimenti di scorte.
- Impostare margini di sicurezza più ampi per proteggersi da fornitori inaffidabili.

È inoltre possibile impostare il piano dinamico iniziale in modo che venga aggiornato con il nuovo piano del fabbisogno ogni volta che si esegue la pianificazione generale. È possibile specificare le impostazioni nella pagina **Parametri di pianificazione generale**.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Impostazioni della copertura](coverage-settings.md)
- [Separazione della pianificazione tattica e operativa per la programmazione generale](https://community.dynamics.com/ax/b/dynamicsaxmanufacturingrdteamblog/posts/separating-tactical-and-operative-planning-for-master-scheduling)
- [Pianificazione generale: utilizzare un piano generale statico e dinamico o utilizzare un piano?](https://community.dynamics.com/ax/b/msdynaxlessonslearned/archive/2014/01/16/master-planning-use-a-static-and-dynamic-master-plan-or-use-one-plan)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

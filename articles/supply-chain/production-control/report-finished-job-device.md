---
title: Dichiarare finito a un'ubicazione controllata da targa dal dispositivo scheda processo
description: In questo argomento viene descritto il processo per il completamento dei prodotti finiti in un ordine di produzione per il magazzino quando una targa controlla l'ubicazione.
author: johanhoffmann
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistration, ProdJournalTransJob, ProdJournalTransRoute, ProdParmReportFinished
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19351
ms.assetid: bcc9e242-b4b8-4144-b14d-c3c106fb40ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2019-09-06
ms.dyn365.ops.version: AX 10.0.6
ms.openlocfilehash: 5f61c1abfb115f02e6ff314f6a3e42bb1d3b543f
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092570"
---
[!include [banner](../includes/banner.md)]

# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a>Dichiarare finito a un'ubicazione controllata da targa dal dispositivo scheda processo 

Il processo denominato Dichiarato finito completa i prodotti finiti in un ordine di produzione nel magazzino. Se il prodotto finito viene abilitato per i processi avanzati del magazzino, i prodotti vengono dichiarati finiti in un'ubicazione denominata unicazione di output di produzione. Per informazioni sull'impostazione dell'ubicazione di output di produzione, vedere [Ubicazione di output di produzione](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).

Se la posizione dell'output di produzione è controllata dalla targa, è necessario fornire una targa al momento della segnalazione come terminata. Il campo **Targa** è visualizzato nella richiesta **Segnala stato** nella pagina **Dispositivo schede processo**. Il campo è visibile solo sul Prompt **Segnala stato** quando viene visualizzato il report sull'ultima operazione dell'ordine di produzione e l'articolo per l'ordine di produzione è abilitato per i processi di gestione del magazzino. 

Esistono due opzioni per fornire la targa
- L'utente seleziona una targa esistente nel campo targa.
- La targa viene generata automaticamente da una sequenza numerica e predefinita nel campo targa.

L'opzione per generare automaticamente la targa viene configurata selezionando l'opzione **Genera targa** della pagina **Configura scheda processo per dispositivi**.

---
title: Dichiarare finito a un'ubicazione controllata da targa dal dispositivo scheda processo
description: In questo argomento viene descritto il processo per il completamento dei prodotti finiti in un ordine di produzione per il magazzino quando una targa controlla l'ubicazione.
author: johanhoffmann
manager: AnnBe
ms.date: 09/06/2019
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
ms.openlocfilehash: cb809e596fd6bf3030bcee460838798435512b95
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "2572131"
---
[!include [banner](../includes/banner.md)]

# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a>Dichiarare finito a un'ubicazione controllata da targa dal dispositivo scheda processo 

Il processo denominato Dichiarato finito completa i prodotti finiti in un ordine di produzione nel magazzino. Se il prodotto finito viene abilitato per i processi avanzati del magazzino, i prodotti vengono dichiarati finiti in un'ubicazione denominata unicazione di output di produzione. Per informazioni sull'impostazione dell'ubicazione di output di produzione, vedere [Ubicazione di output di produzione](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).

È necessario selezionare un numero di identificazione esistente per completare l'attività. Se l'ubicazione di output di produzione è impostata per essere tracciata dalla targa, un numero di identificazione deve essere incluso quando si dichiara l'ubicazione di output di produzione come finita. Il campo **Targa** è visualizzato nella richiesta **Segnala stato** nella pagina **Dispositivo schede processo**. Il campo è visibile solo nella richiesta **Segnala stato** per il reporting dell'ultima operazione dell'ordine di produzione. Il campo viene visualizzato solo se l'articolo per l'ordine di produzione è abilitato per i processi di gestione magazzino. 

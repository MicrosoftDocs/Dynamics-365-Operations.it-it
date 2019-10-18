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
ms.openlocfilehash: 35ad27a6b8a52bfd086fbe4fc57b1681ff88fd5b
ms.sourcegitcommit: 58db26b7edf02e7c33aaaf1c934e3263aa74b01f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2019
ms.locfileid: "1995144"
---
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a><span data-ttu-id="8badd-103">Dichiarare finito a un'ubicazione controllata da targa dal dispositivo scheda processo</span><span class="sxs-lookup"><span data-stu-id="8badd-103">Report as finished to a license plate controlled location from the Job card device</span></span> 

<span data-ttu-id="8badd-104">Il processo denominato Dichiarato finito completa i prodotti finiti in un ordine di produzione nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="8badd-104">The process called Reporting as finished completes finished products on a production order to the inventory.</span></span> <span data-ttu-id="8badd-105">Se il prodotto finito viene abilitato per i processi avanzati del magazzino, i prodotti vengono dichiarati finiti in un'ubicazione denominata unicazione di output di produzione.</span><span class="sxs-lookup"><span data-stu-id="8badd-105">If the finished product is enabled for the advanced warehouse processes, the product is reported as finished to a location called the production output location.</span></span> <span data-ttu-id="8badd-106">Per informazioni sull'impostazione dell'ubicazione di output di produzione, vedere [Ubicazione di output di produzione](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).</span><span class="sxs-lookup"><span data-stu-id="8badd-106">For information about setting up the production output location, see [Production output location](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).</span></span>

<span data-ttu-id="8badd-107">È necessario selezionare un numero di identificazione esistente per completare l'attività.</span><span class="sxs-lookup"><span data-stu-id="8badd-107">You must select an existing license plate number to complete this task.</span></span> <span data-ttu-id="8badd-108">Se l'ubicazione di output di produzione è impostata per essere tracciata dalla targa, un numero di identificazione deve essere incluso quando si dichiara l'ubicazione di output di produzione come finita.</span><span class="sxs-lookup"><span data-stu-id="8badd-108">If the production output location is set up to be tracked by license plate, then a license plate number must be included when reporting the production output location as finished.</span></span> <span data-ttu-id="8badd-109">Il campo **Targa** è visualizzato nella richiesta **Segnala stato** nella pagina **Dispositivo schede processo**.</span><span class="sxs-lookup"><span data-stu-id="8badd-109">The **License plate** field is visible on the **Report progress** prompt on the **Job card device** page.</span></span> <span data-ttu-id="8badd-110">Il campo è visibile solo nella richiesta **Segnala stato** per il reporting dell'ultima operazione dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="8badd-110">The field is only visible on the **Report progress** prompt when reporting on the last operation of the production order.</span></span> <span data-ttu-id="8badd-111">Il campo viene visualizzato solo se l'articolo per l'ordine di produzione è abilitato per i processi di gestione magazzino.</span><span class="sxs-lookup"><span data-stu-id="8badd-111">The field is only shown if the item for the production order is enabled for the warehouse management processes.</span></span> 

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

# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a><span data-ttu-id="14cf6-103">Dichiarare finito a un'ubicazione controllata da targa dal dispositivo scheda processo</span><span class="sxs-lookup"><span data-stu-id="14cf6-103">Report as finished to a license plate controlled location from the Job card device</span></span> 

<span data-ttu-id="14cf6-104">Il processo denominato Dichiarato finito completa i prodotti finiti in un ordine di produzione nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="14cf6-104">The process called Reporting as finished completes finished products on a production order to the inventory.</span></span> <span data-ttu-id="14cf6-105">Se il prodotto finito viene abilitato per i processi avanzati del magazzino, i prodotti vengono dichiarati finiti in un'ubicazione denominata unicazione di output di produzione.</span><span class="sxs-lookup"><span data-stu-id="14cf6-105">If the finished product is enabled for the advanced warehouse processes, the product is reported as finished to a location called the production output location.</span></span> <span data-ttu-id="14cf6-106">Per informazioni sull'impostazione dell'ubicazione di output di produzione, vedere [Ubicazione di output di produzione](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).</span><span class="sxs-lookup"><span data-stu-id="14cf6-106">For information about setting up the production output location, see [Production output location](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).</span></span>

<span data-ttu-id="14cf6-107">Se la posizione dell'output di produzione è controllata dalla targa, è necessario fornire una targa al momento della segnalazione come terminata.</span><span class="sxs-lookup"><span data-stu-id="14cf6-107">If the production output location is license plate controlled, then a license plate must be provided when reporting as finished.</span></span> <span data-ttu-id="14cf6-108">Il campo **Targa** è visualizzato nella richiesta **Segnala stato** nella pagina **Dispositivo schede processo**.</span><span class="sxs-lookup"><span data-stu-id="14cf6-108">The **License plate** field is visible on the **Report progress** prompt on the **Job card device** page.</span></span> <span data-ttu-id="14cf6-109">Il campo è visibile solo sul Prompt **Segnala stato** quando viene visualizzato il report sull'ultima operazione dell'ordine di produzione e l'articolo per l'ordine di produzione è abilitato per i processi di gestione del magazzino.</span><span class="sxs-lookup"><span data-stu-id="14cf6-109">The field is only visible on the **Report progress** prompt when reporting on the last operation of the production order and the item for the production order is enabled for the warehouse management processes.</span></span> 

<span data-ttu-id="14cf6-110">Esistono due opzioni per fornire la targa</span><span class="sxs-lookup"><span data-stu-id="14cf6-110">There are two options for providing the license plate</span></span>
- <span data-ttu-id="14cf6-111">L'utente seleziona una targa esistente nel campo targa.</span><span class="sxs-lookup"><span data-stu-id="14cf6-111">The user is selecting an existing license plate in the license plate field.</span></span>
- <span data-ttu-id="14cf6-112">La targa viene generata automaticamente da una sequenza numerica e predefinita nel campo targa.</span><span class="sxs-lookup"><span data-stu-id="14cf6-112">The license plate is automatically generated from a number sequence and defaulted to the license plate field.</span></span>

<span data-ttu-id="14cf6-113">L'opzione per generare automaticamente la targa viene configurata selezionando l'opzione **Genera targa** della pagina **Configura scheda processo per dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="14cf6-113">The option to have the license plate generated automatically is configured by selecting the option **Generate license plate** on the **Configure job card for devices** page.</span></span>

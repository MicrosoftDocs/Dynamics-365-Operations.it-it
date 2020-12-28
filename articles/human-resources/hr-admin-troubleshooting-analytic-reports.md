---
title: Risolvere i problemi relativi a report analitici
description: In questo articolo viene illustrato come procedere se le modifiche ai dati di un cliente non sono visualizzate in alcuna area di lavoro del cliente.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 99d9eb3a16e6470820a2eb0a19c1d50e89bd3d36
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4419229"
---
# <a name="troubleshoot-analytic-reports"></a><span data-ttu-id="660d1-103">Risolvere i problemi relativi a report analitici</span><span class="sxs-lookup"><span data-stu-id="660d1-103">Troubleshoot analytic reports</span></span>

<span data-ttu-id="660d1-104">**Problema**</span><span class="sxs-lookup"><span data-stu-id="660d1-104">**Issue**</span></span>

<span data-ttu-id="660d1-105">Le modifiche ai dati di un cliente non sono visualizzate nelle schede **Analisi** di alcuna area di lavoro del cliente.</span><span class="sxs-lookup"><span data-stu-id="660d1-105">A customer's data changes don't appear on the **Analytics** tabs of any of the customer's workspaces.</span></span>

<span data-ttu-id="660d1-106">**Causa**</span><span class="sxs-lookup"><span data-stu-id="660d1-106">**Cause**</span></span>

<span data-ttu-id="660d1-107">Per impostazione predefinita, i report di Microsoft Power BI sono aggiornati ogni quattro ore, in base alla programmazione del processo batch Distribuire misura.</span><span class="sxs-lookup"><span data-stu-id="660d1-107">By default, Microsoft Power BI reports are refreshed every four hours, according to the schedule of the Deploy measurement batch job.</span></span>

<span data-ttu-id="660d1-108">**Risoluzione**</span><span class="sxs-lookup"><span data-stu-id="660d1-108">**Resolution**</span></span>

<span data-ttu-id="660d1-109">Il problema potrebbe essere semplicemente una questione di tempistiche.</span><span class="sxs-lookup"><span data-stu-id="660d1-109">This issue might just be a matter of timing.</span></span> <span data-ttu-id="660d1-110">Seguire la procedura seguente per avviare il processo batch e aggiornare le aree di lavoro di analisi.</span><span class="sxs-lookup"><span data-stu-id="660d1-110">Follow these steps to start the batch job and update the analytics workspaces.</span></span>

1. <span data-ttu-id="660d1-111">Aprire la pagina **Processi batch** in **Amministrazione sistema \> Collegamenti \> Processi batch \> Processi batch**.</span><span class="sxs-lookup"><span data-stu-id="660d1-111">Open the **Batch jobs** page at **System administration \> Links \> Batch jobs \> Batch jobs**.</span></span> <span data-ttu-id="660d1-112">In alternativa, utilizzare Cerca e immettere **Processi batch**.</span><span class="sxs-lookup"><span data-stu-id="660d1-112">Alternatively, use Search, and enter **Batch Jobs**.</span></span>
1. <span data-ttu-id="660d1-113">Individuare il processo **Distribuire misura** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="660d1-113">Find the **Deploy measurement** job in the list.</span></span>
1. <span data-ttu-id="660d1-114">Selezionare **Modifica** nella parte superiore della pagina e impostare la data/ora di avvio pianificata su un valore che aggiorna l'analisi più prossima all'ora corrente.</span><span class="sxs-lookup"><span data-stu-id="660d1-114">Select **Edit** at the top of the page, and set the scheduled start date/time to a value that will refresh the analytics closer to the current time.</span></span>

![Processi batch](media/batch-jobs.png)

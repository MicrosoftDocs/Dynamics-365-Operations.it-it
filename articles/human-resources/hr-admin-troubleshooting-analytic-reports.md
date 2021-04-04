---
title: Risolvere i problemi relativi a report analitici
description: In questo articolo viene illustrato come procedere se le modifiche ai dati di un cliente non sono visualizzate in alcuna area di lavoro del cliente.
author: andreabichsel
manager: tfehr
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
ms.openlocfilehash: e0befe1a35aa46b2eabb4516559fe07ce27e9f18
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466666"
---
# <a name="troubleshoot-analytic-reports"></a><span data-ttu-id="bb2ab-103">Risolvere i problemi relativi a report analitici</span><span class="sxs-lookup"><span data-stu-id="bb2ab-103">Troubleshoot analytic reports</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="bb2ab-104">**Problema**</span><span class="sxs-lookup"><span data-stu-id="bb2ab-104">**Issue**</span></span>

<span data-ttu-id="bb2ab-105">Le modifiche ai dati di un cliente non sono visualizzate nelle schede **Analisi** di alcuna area di lavoro del cliente.</span><span class="sxs-lookup"><span data-stu-id="bb2ab-105">A customer's data changes don't appear on the **Analytics** tabs of any of the customer's workspaces.</span></span>

<span data-ttu-id="bb2ab-106">**Causa**</span><span class="sxs-lookup"><span data-stu-id="bb2ab-106">**Cause**</span></span>

<span data-ttu-id="bb2ab-107">Per impostazione predefinita, i report di Microsoft Power BI sono aggiornati ogni quattro ore, in base alla programmazione del processo batch Distribuire misura.</span><span class="sxs-lookup"><span data-stu-id="bb2ab-107">By default, Microsoft Power BI reports are refreshed every four hours, according to the schedule of the Deploy measurement batch job.</span></span>

<span data-ttu-id="bb2ab-108">**Risoluzione**</span><span class="sxs-lookup"><span data-stu-id="bb2ab-108">**Resolution**</span></span>

<span data-ttu-id="bb2ab-109">Il problema potrebbe essere semplicemente una questione di tempistiche.</span><span class="sxs-lookup"><span data-stu-id="bb2ab-109">This issue might just be a matter of timing.</span></span> <span data-ttu-id="bb2ab-110">Seguire la procedura seguente per avviare il processo batch e aggiornare le aree di lavoro di analisi.</span><span class="sxs-lookup"><span data-stu-id="bb2ab-110">Follow these steps to start the batch job and update the analytics workspaces.</span></span>

1. <span data-ttu-id="bb2ab-111">Aprire la pagina **Processi batch** in **Amministrazione sistema \> Collegamenti \> Processi batch \> Processi batch**.</span><span class="sxs-lookup"><span data-stu-id="bb2ab-111">Open the **Batch jobs** page at **System administration \> Links \> Batch jobs \> Batch jobs**.</span></span> <span data-ttu-id="bb2ab-112">In alternativa, utilizzare Cerca e immettere **Processi batch**.</span><span class="sxs-lookup"><span data-stu-id="bb2ab-112">Alternatively, use Search, and enter **Batch Jobs**.</span></span>
1. <span data-ttu-id="bb2ab-113">Individuare il processo **Distribuire misura** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="bb2ab-113">Find the **Deploy measurement** job in the list.</span></span>
1. <span data-ttu-id="bb2ab-114">Selezionare **Modifica** nella parte superiore della pagina e impostare la data/ora di avvio pianificata su un valore che aggiorna l'analisi più prossima all'ora corrente.</span><span class="sxs-lookup"><span data-stu-id="bb2ab-114">Select **Edit** at the top of the page, and set the scheduled start date/time to a value that will refresh the analytics closer to the current time.</span></span>

![Processi batch](media/batch-jobs.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
---
title: I report analitici non sono aggiornati
description: In questo argomento viene illustrato come procedere se le modifiche ai dati di un cliente non sono visualizzate in alcuna area di lavoro del cliente.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: fc2e6259a8f9d17dc0f7652f207acfa53da76a8d
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898575"
---
# <a name="analytic-reports-are-not-updated"></a><span data-ttu-id="4f705-103">I report analitici non sono aggiornati</span><span class="sxs-lookup"><span data-stu-id="4f705-103">Analytic reports are not updated</span></span>

<span data-ttu-id="4f705-104">**Uscita**</span><span class="sxs-lookup"><span data-stu-id="4f705-104">**Issue**</span></span>

<span data-ttu-id="4f705-105">Le modifiche ai dati di un cliente non sono visualizzate nelle schede **Analisi** di alcuna area di lavoro del cliente.</span><span class="sxs-lookup"><span data-stu-id="4f705-105">A customer's data changes don't appear on the **Analytics** tabs of any of the customer's workspaces.</span></span>

<span data-ttu-id="4f705-106">**Causa**</span><span class="sxs-lookup"><span data-stu-id="4f705-106">**Cause**</span></span>

<span data-ttu-id="4f705-107">Per impostazione predefinita, i report di Microsoft Power BI sono aggiornati ogni quattro ore, in base alla programmazione del processo batch Distribuire misura.</span><span class="sxs-lookup"><span data-stu-id="4f705-107">By default, Microsoft Power BI reports are refreshed every four hours, according to the schedule of the Deploy measurement batch job.</span></span>

<span data-ttu-id="4f705-108">**Risoluzione**</span><span class="sxs-lookup"><span data-stu-id="4f705-108">**Resolution**</span></span>

<span data-ttu-id="4f705-109">Il problema potrebbe essere semplicemente una questione di tempistiche.</span><span class="sxs-lookup"><span data-stu-id="4f705-109">This issue might just be a matter of timing.</span></span> <span data-ttu-id="4f705-110">Seguire la procedura seguente per avviare il processo batch e aggiornare le aree di lavoro di analisi.</span><span class="sxs-lookup"><span data-stu-id="4f705-110">Follow these steps to start the batch job and update the analytics workspaces.</span></span>

1. <span data-ttu-id="4f705-111">Aprire la pagina **Processi batch** in **Amministrazione sistema \> Collegamenti \> Processi batch \> Processi batch**.</span><span class="sxs-lookup"><span data-stu-id="4f705-111">Open the **Batch jobs** page at **System administration \> Links \> Batch jobs \> Batch jobs**.</span></span> <span data-ttu-id="4f705-112">In alternativa, utilizzare Cerca e immettere **Processi batch**.</span><span class="sxs-lookup"><span data-stu-id="4f705-112">Alternatively, use Search, and enter **Batch Jobs**.</span></span>
1. <span data-ttu-id="4f705-113">Individuare il processo **Distribuire misura** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="4f705-113">Find the **Deploy measurement** job in the list.</span></span>
1. <span data-ttu-id="4f705-114">Selezionare **Modifica** nella parte superiore della pagina e impostare la data/ora di avvio pianificata su un valore che aggiorna l'analisi più prossima all'ora corrente.</span><span class="sxs-lookup"><span data-stu-id="4f705-114">Select **Edit** at the top of the page, and set the scheduled start date/time to a value that will refresh the analytics closer to the current time.</span></span>

![Processi batch](media/batch-jobs.png)

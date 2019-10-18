---
title: Imposta i codici reporting IVA
description: Questi codici reporting IVA fanno riferimento a un numero di campo in un report IVA.
author: twheeloc
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxReportCollection
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4751256858da417ec9bb1b7d9ccd16fb6bef1cac
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185936"
---
# <a name="set-up-sales-tax-reporting-codes"></a><span data-ttu-id="dd6ce-103">Imposta i codici reporting IVA</span><span class="sxs-lookup"><span data-stu-id="dd6ce-103">Set up sales tax reporting codes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dd6ce-104">Questi codici reporting IVA fanno riferimento a un numero di campo in un report IVA.</span><span class="sxs-lookup"><span data-stu-id="dd6ce-104">The Sales tax reporting codes refer to a field number on a sales tax report.</span></span> <span data-ttu-id="dd6ce-105">Vengono utilizzati nei layout di report specifici del paese e nel report Pagamento IVA per codice per stampare gli importi IVA per un periodo di liquidazione riepilogato per codice reporting.</span><span class="sxs-lookup"><span data-stu-id="dd6ce-105">They are used on country specific report layouts and the Sales tax payment by code report to print sales tax amounts for a settlement period summarized per reporting code.</span></span> <span data-ttu-id="dd6ce-106">Dopo aver creato i codici reporting IVA, è possibile utilizzarli come riferimenti nelle Schede dettaglio Impostazione report della pagina Codice IVA.</span><span class="sxs-lookup"><span data-stu-id="dd6ce-106">After you create Sales tax reporting codes, you can refer to them on the Report setup FastTabs in the Sales tax code page.</span></span> 

<span data-ttu-id="dd6ce-107">Questa registrazione utilizza la società dimostrativa DEMF.</span><span class="sxs-lookup"><span data-stu-id="dd6ce-107">This recording uses the DEMF demo company.</span></span>

1. <span data-ttu-id="dd6ce-108">Nel **pannello di navigazione**, andare a **Imposta > Impostazione > IVA > Codici reporting IVA**.</span><span class="sxs-lookup"><span data-stu-id="dd6ce-108">In the **Navigation pane**, go to **Tax > Setup > Sales tax > Sales tax reporting codes**.</span></span>
2. <span data-ttu-id="dd6ce-109">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="dd6ce-109">Click **New**.</span></span>
3. <span data-ttu-id="dd6ce-110">Selezionare il layout del report a cui appartiene il codice reporting.</span><span class="sxs-lookup"><span data-stu-id="dd6ce-110">Select the report layout that the reporting code belongs to.</span></span> <span data-ttu-id="dd6ce-111">Questo layout viene utilizzato per filtrare i codici reporting disponibili per un codice IVA.</span><span class="sxs-lookup"><span data-stu-id="dd6ce-111">This layout is used to filter the available reporting codes for a Sales tax code.</span></span> <span data-ttu-id="dd6ce-112">Ogni codice IVA appartiene a un periodo di liquidazione appartenente a un ufficio IVA che utilizza un layout di report.</span><span class="sxs-lookup"><span data-stu-id="dd6ce-112">Each Sales tax code belongs to a settlement period which belongs to a Sales tax authority which uses a Report layout.</span></span>  
4. <span data-ttu-id="dd6ce-113">Nel campo **Codice del report** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="dd6ce-113">In the **Reporting code** field, enter a number.</span></span>
5. <span data-ttu-id="dd6ce-114">Nel campo **Testo report** immettere una descrizione da visualizzare nei report.</span><span class="sxs-lookup"><span data-stu-id="dd6ce-114">In the **Report text** field, enter a description to display on reports.</span></span>
6. <span data-ttu-id="dd6ce-115">Nel campo **Breve descrizione** immettere una descrizione per scopi interni.</span><span class="sxs-lookup"><span data-stu-id="dd6ce-115">In the **Brief description** field, enter a description for internal purposes.</span></span>
7. <span data-ttu-id="dd6ce-116">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="dd6ce-116">Click **Save**.</span></span>


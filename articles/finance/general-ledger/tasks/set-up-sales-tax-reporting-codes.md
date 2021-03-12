---
title: Imposta i codici reporting IVA
description: Questi codici reporting IVA fanno riferimento a un numero di campo elencato in un report IVA.
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
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 821d4abcffbca624382aa7709c02b857fcb6e349
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994517"
---
# <a name="set-up-sales-tax-reporting-codes"></a><span data-ttu-id="d1525-103">Imposta i codici reporting IVA</span><span class="sxs-lookup"><span data-stu-id="d1525-103">Set up sales tax reporting codes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d1525-104">Questi codici reporting IVA fanno riferimento a un numero di campo elencato in un report IVA.</span><span class="sxs-lookup"><span data-stu-id="d1525-104">The Sales tax reporting codes refer to a field number that's listed on a sales tax report.</span></span> <span data-ttu-id="d1525-105">Vengono utilizzati su layout di report specifici per paese/area geografica.</span><span class="sxs-lookup"><span data-stu-id="d1525-105">They are used on country-specific report layouts.</span></span> <span data-ttu-id="d1525-106">Vengono utilizzati anche nel pagamento IVA per codice (report).</span><span class="sxs-lookup"><span data-stu-id="d1525-106">They're also used on the Sales tax payment by code report.</span></span> <span data-ttu-id="d1525-107">Tale report mostra gli importi IVA per un periodo di liquidazione riepilogati per ogni codice di reporting.</span><span class="sxs-lookup"><span data-stu-id="d1525-107">That report shows sales tax amounts for a settlement period summarized for each reporting code.</span></span> <span data-ttu-id="d1525-108">Dopo aver creato i codici reporting IVA, è possibile utilizzarli come riferimenti nelle Schede dettaglio Impostazione report accessibili dalla pagina **Codice IVA**.</span><span class="sxs-lookup"><span data-stu-id="d1525-108">After you create Sales tax reporting codes, you can refer to those codes on the Report setup FastTabs, which you can access from the **Sales tax code** page.</span></span> 

<span data-ttu-id="d1525-109">Questa registrazione utilizza la società dimostrativa DEMF.</span><span class="sxs-lookup"><span data-stu-id="d1525-109">This recording uses the DEMF demo company.</span></span>

1. <span data-ttu-id="d1525-110">Nel **pannello di navigazione**, andare a **Imposta > Impostazione > IVA > Codici reporting IVA**.</span><span class="sxs-lookup"><span data-stu-id="d1525-110">In the **Navigation pane**, go to **Tax > Setup > Sales tax > Sales tax reporting codes**.</span></span>
2. <span data-ttu-id="d1525-111">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="d1525-111">Click **New**.</span></span>
3. <span data-ttu-id="d1525-112">Selezionare il layout del report a cui appartiene il codice reporting.</span><span class="sxs-lookup"><span data-stu-id="d1525-112">Select the report layout that the reporting code belongs to.</span></span> <span data-ttu-id="d1525-113">Questo layout viene utilizzato per filtrare i codici reporting disponibili per un codice IVA.</span><span class="sxs-lookup"><span data-stu-id="d1525-113">This layout is used to filter the available reporting codes for a sales tax code.</span></span> <span data-ttu-id="d1525-114">Ogni codice IVA appartiene a un periodo di liquidazione appartenente a un ufficio IVA che utilizza un layout di report.</span><span class="sxs-lookup"><span data-stu-id="d1525-114">Each sales tax code belongs to a settlement period, which belongs to a Sales tax authority, which uses a report layout.</span></span>  
4. <span data-ttu-id="d1525-115">Nel campo **Codice del report** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="d1525-115">In the **Reporting code** field, enter a number.</span></span>
5. <span data-ttu-id="d1525-116">Nel campo **Testo report** immettere una descrizione da visualizzare nei report.</span><span class="sxs-lookup"><span data-stu-id="d1525-116">In the **Report text** field, enter a description to display on reports.</span></span>
6. <span data-ttu-id="d1525-117">Nel campo **Breve descrizione** immettere una descrizione per scopi interni.</span><span class="sxs-lookup"><span data-stu-id="d1525-117">In the **Brief description** field, enter a description for internal purposes.</span></span>
7. <span data-ttu-id="d1525-118">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d1525-118">Click **Save**.</span></span>


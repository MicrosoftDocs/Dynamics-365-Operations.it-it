---
title: Cambiare le convenzioni di ammortamento per più cespiti
description: Tale attività consente di aggiornare la convenzione di ammortamento per un gruppo di cespiti specificato.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysQueryForm, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2c64e4f7117c4ca70236a02b4d36a88e9f2a9906
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210025"
---
# <a name="change-depreciation-conventions-for-multiple-fixed-assets"></a><span data-ttu-id="b0e8d-103">Cambiare le convenzioni di ammortamento per più cespiti</span><span class="sxs-lookup"><span data-stu-id="b0e8d-103">Change depreciation conventions for multiple fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b0e8d-104">Tale attività consente di aggiornare la convenzione di ammortamento per un gruppo di cespiti specificato.</span><span class="sxs-lookup"><span data-stu-id="b0e8d-104">This task updates the depreciation convention for a specified fixed asset group.</span></span> <span data-ttu-id="b0e8d-105">Questa guida attività utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="b0e8d-105">This task guide uses the USMF demo company.</span></span>

1. <span data-ttu-id="b0e8d-106">Andare a Cespiti > Attività periodiche > Aggiornamento di massa</span><span class="sxs-lookup"><span data-stu-id="b0e8d-106">Go to Fixed assets > Periodic tasks > Mass update</span></span>
2. <span data-ttu-id="b0e8d-107">Nel campo Registro beni ammortizzabili fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="b0e8d-107">In the Depreciation book field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="b0e8d-108">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b0e8d-108">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="b0e8d-109">Nel campo Inizio messa in servizio immettere una data.</span><span class="sxs-lookup"><span data-stu-id="b0e8d-109">In the Placed in service start field, enter a date.</span></span>
5. <span data-ttu-id="b0e8d-110">Nel campo Fine messa in servizio immettere una data.</span><span class="sxs-lookup"><span data-stu-id="b0e8d-110">In the Placed in service end field, enter a date.</span></span>
    * <span data-ttu-id="b0e8d-111">Solo i cespiti appartenenti al registro beni ammortizzabili selezionato e messi in servizio nel periodo compreso tra queste date verranno aggiornati.</span><span class="sxs-lookup"><span data-stu-id="b0e8d-111">Only assets that are a part of the select depreciation book and that have been placed in service between these dates will be updated.</span></span>  
6. <span data-ttu-id="b0e8d-112">Nel campo Convenzione di ammortamento corrente selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="b0e8d-112">In the Current depreciation convention field, select an option.</span></span>
    * <span data-ttu-id="b0e8d-113">Solo i cespiti con la convenzione di ammortamento corrente verranno aggiornati.</span><span class="sxs-lookup"><span data-stu-id="b0e8d-113">Only assets that have the current depreciation convention will be updated.</span></span>  
7. <span data-ttu-id="b0e8d-114">Nel campo Nuova convenzione di ammortamento selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="b0e8d-114">In the New depreciation convention field, select an option.</span></span>
    * <span data-ttu-id="b0e8d-115">Verificare che il report venga stampato nella destinazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="b0e8d-115">Verify the report will print to the desired destination.</span></span>  
8. <span data-ttu-id="b0e8d-116">Espandere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="b0e8d-116">Expand the Records to include section.</span></span>
9. <span data-ttu-id="b0e8d-117">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="b0e8d-117">Click Filter.</span></span>
10. <span data-ttu-id="b0e8d-118">Selezionare il gruppo cespite nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b0e8d-118">In the list, select the Fixed asset group.</span></span>
11. <span data-ttu-id="b0e8d-119">Nel campo Criteri fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="b0e8d-119">In the Criteria field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="b0e8d-120">Selezionare il gruppo cespite desiderato.</span><span class="sxs-lookup"><span data-stu-id="b0e8d-120">Select the desired Fixed asset group.</span></span>
13. <span data-ttu-id="b0e8d-121">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b0e8d-121">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="b0e8d-122">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b0e8d-122">Click OK.</span></span>
15. <span data-ttu-id="b0e8d-123">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b0e8d-123">Click OK.</span></span>
    *  <span data-ttu-id="b0e8d-124">I risultati del processo vengono visualizzati nel report Aggiornamento di massa.</span><span class="sxs-lookup"><span data-stu-id="b0e8d-124">Results of the process are shown on the Mass update report.</span></span>     



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
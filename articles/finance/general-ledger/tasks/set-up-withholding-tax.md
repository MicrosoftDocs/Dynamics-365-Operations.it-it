---
title: Impostare i codici di ritenuta d'acconto
description: In questo argomento viene illustrato come impostare la ritenuta d'acconto.
author: twheeloc
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxWithholdTable, TaxWithholdData, TaxWithholdGroup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 10e7018c79e54841d0729636b08ad475a94d20d5
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185959"
---
# <a name="set-up-withholding-tax"></a><span data-ttu-id="47565-103">Impostare i codici di ritenuta d'acconto</span><span class="sxs-lookup"><span data-stu-id="47565-103">Set up withholding tax</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="47565-104">In questo argomento viene illustrato come impostare la ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="47565-104">This topic explains how to set up withholding tax.</span></span> <span data-ttu-id="47565-105">La *ritenuta d'acconto* è un'imposta sui fornitori che non dà origine a transazioni IVA.</span><span class="sxs-lookup"><span data-stu-id="47565-105">*Withholding tax* is a tax on vendors that does not create sales tax transactions.</span></span> <span data-ttu-id="47565-106">La ritenuta d'acconto calcolata sui pagamenti fornitore è considerata una passività</span><span class="sxs-lookup"><span data-stu-id="47565-106">Withholding tax that is calculated on vendor payments is a liability.</span></span> <span data-ttu-id="47565-107">e può pertanto essere registrata solo nei conti dello stato patrimoniale o nei conti passivi.</span><span class="sxs-lookup"><span data-stu-id="47565-107">Therefore, only balance sheet accounts or liability accounts are valid accounts for posting withholding tax.</span></span> <span data-ttu-id="47565-108">Questa guida attività dimostra l'impostazione della ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="47565-108">This task guide demonstrates how to set up withholding tax.</span></span>

1. <span data-ttu-id="47565-109">Andare a **Pannello di navigazione > Moduli > Imposta > Imposte indirette > Ritenuta d'acconto > Codici ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="47565-109">Go to **Navigation pane > Modules > Tax > Indirect taxes > Withholding tax > Withholding tax codes**.</span></span>
2. <span data-ttu-id="47565-110">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="47565-110">Select **New**.</span></span>
3. <span data-ttu-id="47565-111">Nel campo **Codice ritenuta d'acconto** digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="47565-111">In the **Withholding tax code** field, type a value.</span></span>
4. <span data-ttu-id="47565-112">Nel campo **Nome ritenuta d'acconto** immettere il nome del codice di ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="47565-112">In the **Withholding tax name** field, enter the name of the withholding tax code.</span></span>
5. <span data-ttu-id="47565-113">Nel campo **Conto principale** selezionare il conto principale per registrare la ritenuta d'acconto dovuta.</span><span class="sxs-lookup"><span data-stu-id="47565-113">In the **Main account** field, select the main account for posting the withholding tax liability.</span></span>
6. <span data-ttu-id="47565-114">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="47565-114">Select **Save**.</span></span>
7. <span data-ttu-id="47565-115">Selezionare **Valori** e contrassegnare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="47565-115">Select **Values** and mark the desired record in the list.</span></span>
8. <span data-ttu-id="47565-116">Nel campo **Valore**, immettere una percentuale utilizzata per il calcolo della ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="47565-116">In the **Value** field, enter a percentage used for the calculation of the withholding tax.</span></span>
9. <span data-ttu-id="47565-117">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="47565-117">Select **Save**.</span></span>
10. <span data-ttu-id="47565-118">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="47565-118">Close the page.</span></span>
11. <span data-ttu-id="47565-119">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="47565-119">Select **Save**.</span></span>
12. <span data-ttu-id="47565-120">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="47565-120">Close the page.</span></span>
13. <span data-ttu-id="47565-121">Andare a **Pannello di navigazione > Moduli > Imposta > Imposte indirette > Ritenuta d'acconto > Gruppi ritenute d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="47565-121">Go to **Navigation pane > Modules > Tax > Indirect taxes > Withholding tax > Withholding tax groups**.</span></span>
14. <span data-ttu-id="47565-122">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="47565-122">Select **New**.</span></span>
15. <span data-ttu-id="47565-123">Nel campo **Gruppo ritenute d'acconto** immettere l'identificatore del gruppo di ritenute d'acconto.</span><span class="sxs-lookup"><span data-stu-id="47565-123">In the **Withholding tax group** field, enter the identifier of the withholding tax group.</span></span>
16. <span data-ttu-id="47565-124">Nel campo **Descrizione** immettere il nome del gruppo di ritenute d'acconto.</span><span class="sxs-lookup"><span data-stu-id="47565-124">In the **Description** field, enter the name of the withholding tax group.</span></span>
17. <span data-ttu-id="47565-125">Nel campo **Codice ritenuta d'acconto** selezionare il codice ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="47565-125">In the **Withholding tax code** field, select the withholding tax code.</span></span>
18. <span data-ttu-id="47565-126">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="47565-126">Select **Save**.</span></span>
19. <span data-ttu-id="47565-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="47565-127">Close the page.</span></span>


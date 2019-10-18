---
title: Impostare le categorie di conti principali
description: In questo argomento viene illustrato come impostare le categorie di conti principali in Dynamics 365 Finance.
author: aprilolson
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MainAccountCategory, MainAccountCategoryLink
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8e2ba1d900f5d87a76fa93bf53f2970320e7d84c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186005"
---
# <a name="set-up-main-account-categories"></a><span data-ttu-id="dcae8-103">Impostare le categorie di conti principali</span><span class="sxs-lookup"><span data-stu-id="dcae8-103">Set up main account categories</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dcae8-104">In questo argomento viene illustrato come impostare le categorie di conti principali.</span><span class="sxs-lookup"><span data-stu-id="dcae8-104">This topic explains how to set up main account categories.</span></span> <span data-ttu-id="dcae8-105">Le categorie di conti principali sono utilizzate per i report predefiniti nei report finanziari e in Power BI.</span><span class="sxs-lookup"><span data-stu-id="dcae8-105">Main account categories are used for the default reports in financial reporting and in Power BI.</span></span> <span data-ttu-id="dcae8-106">Le categorie di conti principali create per impostazione predefinita possono essere rinominate ma non eliminate.</span><span class="sxs-lookup"><span data-stu-id="dcae8-106">Main account categories that are created by default can be renamed but not deleted.</span></span> <span data-ttu-id="dcae8-107">Categorie di conti aggiuntive possono essere create e utilizzate a fini di report e analisi.</span><span class="sxs-lookup"><span data-stu-id="dcae8-107">Additional account categories can be created and used for reporting and analysis purposes.</span></span> <span data-ttu-id="dcae8-108">In questo argomento viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="dcae8-108">This topic uses the USMF demo company.</span></span>

## <a name="create-a-main-account-category"></a><span data-ttu-id="dcae8-109">Creare una categoria di conti principali</span><span class="sxs-lookup"><span data-stu-id="dcae8-109">Create a main account category</span></span>
1. <span data-ttu-id="dcae8-110">Nel pannello di navigazione andare a **Moduli > Contabilità generale > Piano dei conti > Conti > Categorie di conti principali**.</span><span class="sxs-lookup"><span data-stu-id="dcae8-110">In the navigation pane, go to **Modules > General Ledger > Chart of accounts > Accounts > Main account categories**.</span></span>
2. <span data-ttu-id="dcae8-111">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="dcae8-111">Select **New**.</span></span>
3. <span data-ttu-id="dcae8-112">Immettere un nome univoco nel campo **Categoria di conti principali**.</span><span class="sxs-lookup"><span data-stu-id="dcae8-112">In the **Main account category** field, enter a unique name.</span></span>
4. <span data-ttu-id="dcae8-113">Nel campo **Descrizione** immettere una descrizione per la categoria di conti principali.</span><span class="sxs-lookup"><span data-stu-id="dcae8-113">In the **Description field**, enter a description for the main account category.</span></span>
5. <span data-ttu-id="dcae8-114">Nel campo **Tipo di conto principale** selezionare il tipo di conto principale da collegare alla categoria.</span><span class="sxs-lookup"><span data-stu-id="dcae8-114">In the **Main account type** field, select the main account type that will be linked to the category.</span></span>

## <a name="link-main-accounts-to-account-category"></a><span data-ttu-id="dcae8-115">Collegare conti principali a una categoria di conti</span><span class="sxs-lookup"><span data-stu-id="dcae8-115">Link main accounts to account category</span></span>
1. <span data-ttu-id="dcae8-116">Fare clic su **Collega conti principali**.</span><span class="sxs-lookup"><span data-stu-id="dcae8-116">Click **Link main accounts**.</span></span>
2. <span data-ttu-id="dcae8-117">Nell'elenco, selezionare i conti principali da assegnare alla categoria di conti principali selezionando le caselle nella colonna **Collegato**.</span><span class="sxs-lookup"><span data-stu-id="dcae8-117">In the list, select the main accounts to assign to the main account category by checking the boxes in the **Linked** column.</span></span> <span data-ttu-id="dcae8-118">Assegnare i conti principali a una categoria di conti principali aggregherà i saldi dei conti quando la categoria viene utilizzata per i report finanziari e l'analisi.</span><span class="sxs-lookup"><span data-stu-id="dcae8-118">Assigning main accounts to a main account category will aggregate the balances of the accounts when that category is used for financial reporting and analysis.</span></span>  
3. <span data-ttu-id="dcae8-119">Selezionare o deselezionare l'opzione **Collegato** per scegliere i conti principali.</span><span class="sxs-lookup"><span data-stu-id="dcae8-119">Select or clear the **Linked** option to choose the main accounts.</span></span>
4. <span data-ttu-id="dcae8-120">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="dcae8-120">Select **OK**.</span></span>
5. <span data-ttu-id="dcae8-121">Selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="dcae8-121">Select **Yes**.</span></span>

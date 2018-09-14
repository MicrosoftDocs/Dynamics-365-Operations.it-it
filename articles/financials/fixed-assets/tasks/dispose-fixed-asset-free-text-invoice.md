--- 
title: Eliminare un cespite utilizzando una fattura a testo libero
description: Questa procedura mostra come acquisire un cespite utilizzando la proposta di acquisizione nel giornale di registrazione cespiti.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 742c7d732ff121bff841ac0149b15bef5a94c756
ms.contentlocale: it-it
ms.lasthandoff: 09/14/2018

---
# <a name="dispose-of-a-fixed-asset-using-a-free-text-invoice"></a><span data-ttu-id="af588-103">Eliminare un cespite utilizzando una fattura a testo libero</span><span class="sxs-lookup"><span data-stu-id="af588-103">Dispose of a fixed asset using a free text invoice</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="af588-104">Questa procedura mostra come acquisire un cespite utilizzando la proposta di acquisizione nel giornale di registrazione cespiti.</span><span class="sxs-lookup"><span data-stu-id="af588-104">This procedure shows how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="af588-105">Utilizza il ruolo Ragioniere e i dati dimostrativi della persona giuridica USMF.</span><span class="sxs-lookup"><span data-stu-id="af588-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="af588-106">Andare a Cespiti > Inserimenti nel giornale di registrazione > Giornale di registrazione cespiti.</span><span class="sxs-lookup"><span data-stu-id="af588-106">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="af588-107">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="af588-107">Click New.</span></span>
3. <span data-ttu-id="af588-108">Nel campo Nome immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="af588-108">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="af588-109">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="af588-109">Click Lines.</span></span>
5. <span data-ttu-id="af588-110">Fare clic su Proposte.</span><span class="sxs-lookup"><span data-stu-id="af588-110">Click Proposals.</span></span>
6. <span data-ttu-id="af588-111">Fare clic su Proposta di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="af588-111">Click Acquisition proposal.</span></span>
7. <span data-ttu-id="af588-112">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="af588-112">Click Filter.</span></span>
8. <span data-ttu-id="af588-113">Fare clic su Reimposta per cancellare i valori precedenti.</span><span class="sxs-lookup"><span data-stu-id="af588-113">Click Reset to clear out previous values.</span></span>
9. <span data-ttu-id="af588-114">Selezionare la riga Numero cespite.</span><span class="sxs-lookup"><span data-stu-id="af588-114">Select the Fixed asset number row.</span></span>
10. <span data-ttu-id="af588-115">Nel campo Criteri immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="af588-115">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="af588-116">Impostare i criteri rimanenti per i cespiti che si desidera acquisire con la proposta.</span><span class="sxs-lookup"><span data-stu-id="af588-116">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
11. <span data-ttu-id="af588-117">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="af588-117">Click OK.</span></span>
12. <span data-ttu-id="af588-118">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="af588-118">Click OK.</span></span>
    * <span data-ttu-id="af588-119">Verificare le righe transazione create.</span><span class="sxs-lookup"><span data-stu-id="af588-119">Verify the transaction lines created.</span></span>  
    * <span data-ttu-id="af588-120">Solo i cespiti con la data di acquisizione e il prezzo di acquisizione impostati sul libro verranno inclusi nella proposta di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="af588-120">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
13. <span data-ttu-id="af588-121">Fare clic sulla scheda Libri.</span><span class="sxs-lookup"><span data-stu-id="af588-121">Click the Books tab.</span></span>
14. <span data-ttu-id="af588-122">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="af588-122">Click Post.</span></span>



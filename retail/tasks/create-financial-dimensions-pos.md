--- 
title: " Creare le dimensioni finanziarie per i registri POS e configurare i valori di dimensione nei registri"
description: In questa procedura vengono descritti i passaggi per creare le dimensioni finanziarie per i registratori di cassa del punto vendita (POS) e viene illustrata la configurazione dei valori di dimensione finanziaria nei registratori di cassa.
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 8a3a6abc19bae20b7899628d0463cf458955671a
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="create-financial-dimensions-for-pos-registers-and-configure-dimension-values-on-registers"></a><span data-ttu-id="a6e35-103"> Creare le dimensioni finanziarie per i registri POS e configurare i valori di dimensione nei registri</span><span class="sxs-lookup"><span data-stu-id="a6e35-103">Create financial dimensions for POS registers and configure dimension values on registers</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="a6e35-104">In questa procedura vengono descritti i passaggi per creare le dimensioni finanziarie per i registratori di cassa del punto vendita (POS) e viene illustrata la configurazione dei valori di dimensione finanziaria nei registratori di cassa.</span><span class="sxs-lookup"><span data-stu-id="a6e35-104">This procedure walks through creating financial dimensions for point of sale (POS) registers, and demonstrates how to configure financial dimension values on registers.</span></span> <span data-ttu-id="a6e35-105">In questa procedura non sono inclusi altri passaggi correlati, ad esempio per creare i set di dimensioni e le strutture dei conti.</span><span class="sxs-lookup"><span data-stu-id="a6e35-105">This procedure doesn’t include other related steps, such as creating dimension sets and account structures.</span></span> <span data-ttu-id="a6e35-106">Tali attività sono trattate in altri argomenti.</span><span class="sxs-lookup"><span data-stu-id="a6e35-106">Those tasks can be found in other topics.</span></span> <span data-ttu-id="a6e35-107">Questa registrazione utilizza la società dimostrativa USRT.</span><span class="sxs-lookup"><span data-stu-id="a6e35-107">This recording uses USRT demo company.</span></span>

1. <span data-ttu-id="a6e35-108">Passare a Contabilità generale > Piano dei conti > Dimensioni > Dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="a6e35-108">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="a6e35-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="a6e35-109">Click New.</span></span>
3. <span data-ttu-id="a6e35-110">Selezionare un'opzione nel campo Usa valori da.</span><span class="sxs-lookup"><span data-stu-id="a6e35-110">In the Use values from field, select an option.</span></span>
4. <span data-ttu-id="a6e35-111">Digitare un valore nel campo Nome dimensione.</span><span class="sxs-lookup"><span data-stu-id="a6e35-111">In the Dimension name field, type a value.</span></span>
5. <span data-ttu-id="a6e35-112">Fare clic su Attiva.</span><span class="sxs-lookup"><span data-stu-id="a6e35-112">Click Activate.</span></span>
6. <span data-ttu-id="a6e35-113">Fare clic su Chiudi.</span><span class="sxs-lookup"><span data-stu-id="a6e35-113">Click Close.</span></span>
7. <span data-ttu-id="a6e35-114">Fare clic su Attiva.</span><span class="sxs-lookup"><span data-stu-id="a6e35-114">Click Activate.</span></span>
8. <span data-ttu-id="a6e35-115">Fare clic su Valori di dimensione.</span><span class="sxs-lookup"><span data-stu-id="a6e35-115">Click Dimension values.</span></span>
9. <span data-ttu-id="a6e35-116">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a6e35-116">Close the page.</span></span>
10. <span data-ttu-id="a6e35-117">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="a6e35-117">Click Save.</span></span>
11. <span data-ttu-id="a6e35-118">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a6e35-118">Close the page.</span></span>
12. <span data-ttu-id="a6e35-119">Passare a Vendita al dettaglio e commercio > Impostazione canale > Impostazione POS > Registri.</span><span class="sxs-lookup"><span data-stu-id="a6e35-119">Go to Retail and commerce > Channel setup > POS setup > Registers.</span></span>
13. <span data-ttu-id="a6e35-120">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="a6e35-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="a6e35-121">Attivare/disattivare l'espansione della sezione Dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="a6e35-121">Toggle the expansion of the Financial dimensions section.</span></span>
15. <span data-ttu-id="a6e35-122">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="a6e35-122">Click Edit.</span></span>
16. <span data-ttu-id="a6e35-123">Nel campo Terminale fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="a6e35-123">In the Terminal field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="a6e35-124">Nell'elenco, individuare e selezionare il valore della dimensione per l'aggiornamento del registratore.</span><span class="sxs-lookup"><span data-stu-id="a6e35-124">In the list, find and select the dimension value for the register being updated.</span></span>
18. <span data-ttu-id="a6e35-125">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="a6e35-125">Click Save.</span></span>


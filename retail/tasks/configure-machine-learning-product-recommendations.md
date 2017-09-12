--- 
title: " Configurare i suggerimenti sul prodotto basati su Machine Learning"
description: "Questa procedura consente di aggiornare i dati nell'archivio entità utilizzati dal sistema di apprendimento automatico su cui si basano i suggerimenti sul prodotto e quindi di abilitare tali suggierimenti sui client POS."
author: ashishmsft
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: e32c7cf1283487cb7a52f7d8e261b6b587b76364
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="configure-machine-learning-powered-product-recommendations"></a><span data-ttu-id="8b0ee-103"> Configurare i suggerimenti sul prodotto basati su Machine Learning</span><span class="sxs-lookup"><span data-stu-id="8b0ee-103">Configure machine learning-powered product recommendations</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="8b0ee-104">Questa procedura consente di aggiornare i dati nell'archivio entità utilizzati dal sistema di apprendimento automatico su cui si basano i suggerimenti sul prodotto e quindi di abilitare tali suggierimenti sui client POS.</span><span class="sxs-lookup"><span data-stu-id="8b0ee-104">This procedure refreshes the data in the Entity store that is used by the machine learning system that powers product recommendations, and then enables product recommendations on POS clients.</span></span> <span data-ttu-id="8b0ee-105">Questa procedura utilizza i dati dimostrativi della società USRT.</span><span class="sxs-lookup"><span data-stu-id="8b0ee-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="8b0ee-106">Scegliere Amministrazione sistema > Impostazioni > Archivio entità.</span><span class="sxs-lookup"><span data-stu-id="8b0ee-106">Go to System administration > Setup > Entity Store.</span></span>
2. <span data-ttu-id="8b0ee-107">Nell'elenco trovare e selezionare il record 'RetailSales'.</span><span class="sxs-lookup"><span data-stu-id="8b0ee-107">In the list, find and select the record 'RetailSales'.</span></span>
3. <span data-ttu-id="8b0ee-108">Fare clic su Aggiorna.</span><span class="sxs-lookup"><span data-stu-id="8b0ee-108">Click Refresh.</span></span>
4. <span data-ttu-id="8b0ee-109">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8b0ee-109">Click OK.</span></span>
5. <span data-ttu-id="8b0ee-110">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8b0ee-110">Close the page.</span></span>
6. <span data-ttu-id="8b0ee-111">Andare a Vendita al dettaglio e commercio > Impostazione sedi centrali > Parametri > Parametri di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="8b0ee-111">Go to Retail and commerce > Headquarters setup > Parameters > Retail parameters.</span></span>
7. <span data-ttu-id="8b0ee-112">Fare clic sulla scheda Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="8b0ee-112">Click the Machine learning tab.</span></span>
8. <span data-ttu-id="8b0ee-113">Selezionare 'Sì' nel campo Abilita suggerimenti sul prodotto.</span><span class="sxs-lookup"><span data-stu-id="8b0ee-113">Select 'Yes' in the Enable product recommendations field.</span></span>
    * <span data-ttu-id="8b0ee-114">Se si riceve il messaggio 'Impossibile recuperare i modelli di suggerimento', significa che si è aggiornato l'archivio entità molto di recente e il sistema può non avere completato di assimilare i nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="8b0ee-114">If you receive the message "The recommendation models couldn't be retrieved", it’s because you refreshed the Entity Store very recently and the system may not have finished assimilating the new data.</span></span> <span data-ttu-id="8b0ee-115">Attendere 2-3 ore e riprovare.</span><span class="sxs-lookup"><span data-stu-id="8b0ee-115">Wait 2-3 hours and try again.</span></span>  
9. <span data-ttu-id="8b0ee-116">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8b0ee-116">Click Save.</span></span>
10. <span data-ttu-id="8b0ee-117">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8b0ee-117">Close the page.</span></span>


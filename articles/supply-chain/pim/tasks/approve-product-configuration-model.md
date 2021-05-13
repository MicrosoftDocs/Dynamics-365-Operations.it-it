---
title: Approvare un modello di configurazione prodotto
description: L'esecuzione di questa procedura richiede almeno un modello di configurazione prodotto disponibile.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductModelVersion, PCApproveProductModelVersion, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2c945756997b0580ac7ffb19261f9184e53a1c10
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920509"
---
# <a name="approve-a-product-configuration-model"></a><span data-ttu-id="baddd-103">Approvare un modello di configurazione prodotto</span><span class="sxs-lookup"><span data-stu-id="baddd-103">Approve a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="baddd-104">L'esecuzione di questa procedura richiede almeno un modello di configurazione prodotto disponibile.</span><span class="sxs-lookup"><span data-stu-id="baddd-104">Running this procedure requires that at least one product configuration model is available.</span></span> <span data-ttu-id="baddd-105">Nella procedura viene utilizzato il modello High end speaker della società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="baddd-105">This procedure uses the High end speaker model in the demo data company USMF.</span></span> <span data-ttu-id="baddd-106">Si noti che il modello è già stato approvato, ma nella procedura è incluso il processo completo.</span><span class="sxs-lookup"><span data-stu-id="baddd-106">Note that this model has already been approved, but the procedure walks you through the entire process.</span></span>

1. <span data-ttu-id="baddd-107">Vai a **Gestione informazioni sul prodotto \> Prodotti \> Modelli di configurazione prodotto**.</span><span class="sxs-lookup"><span data-stu-id="baddd-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="baddd-108">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="baddd-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="baddd-109">Selezionare il modello High end speaker per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="baddd-109">Select the High end speaker model for this procedure.</span></span>  
1. <span data-ttu-id="baddd-110">Seleziona **Versioni**.</span><span class="sxs-lookup"><span data-stu-id="baddd-110">Select **Versions**.</span></span>
1. <span data-ttu-id="baddd-111">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="baddd-111">Select **New**.</span></span>
1. <span data-ttu-id="baddd-112">Nel campo **Numero prodotto** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="baddd-112">In the **Product number** field, enter or select a value.</span></span>
    * <span data-ttu-id="baddd-113">Il riferimento a un prodotto rappresenta una versione di un modello di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="baddd-113">The reference to a product represents a version of a product configuration model.</span></span> <span data-ttu-id="baddd-114">Solo le rappresentazioni generali prodotto con la tecnologia di configurazione basata su vincoli verranno visualizzate nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="baddd-114">Only product masters which have the constraint-based configuration technology will appear in this list.</span></span>  
1. <span data-ttu-id="baddd-115">Immettere una data nel campo **Dal**.</span><span class="sxs-lookup"><span data-stu-id="baddd-115">In the **From date** field, enter a date.</span></span>
    * <span data-ttu-id="baddd-116">Selezionare quando la versione del modello prodotto sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="baddd-116">Select when the product model version will be available.</span></span>  
1. <span data-ttu-id="baddd-117">Nel campo **Al** immettere una data.</span><span class="sxs-lookup"><span data-stu-id="baddd-117">In the **To date** field, enter a date.</span></span>
    * <span data-ttu-id="baddd-118">Selezionare una data di fine se questa versione del modello prodotto scade oppure selezionare Mai.</span><span class="sxs-lookup"><span data-stu-id="baddd-118">Select an end date when this product model version will expire, or select Never.</span></span>  
1. <span data-ttu-id="baddd-119">Fare clic su **Approva** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="baddd-119">Select **Approve** to open the drop dialog.</span></span>
1. <span data-ttu-id="baddd-120">Nel campo **Approvato da** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="baddd-120">In the **Approved by** field, enter or select a value.</span></span>
    * <span data-ttu-id="baddd-121">Selezionare la persona responsabile dell'approvazione dei modelli prodotto per l'utilizzo nelle operazioni.</span><span class="sxs-lookup"><span data-stu-id="baddd-121">Select the person who is responsible for approving product models for use in operations.</span></span>  
1. <span data-ttu-id="baddd-122">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="baddd-122">Select **OK**.</span></span>
1. <span data-ttu-id="baddd-123">Selezionare un'opzione nel campo **Metodo di determinazione prezzo**.</span><span class="sxs-lookup"><span data-stu-id="baddd-123">In the **Pricing method** field, select an option.</span></span>
    * <span data-ttu-id="baddd-124">Attivare la versione del modello prodotto.</span><span class="sxs-lookup"><span data-stu-id="baddd-124">Activate the product model version.</span></span> <span data-ttu-id="baddd-125">È possibile avere un solo prodotto attivo per un modello prodotto alla volta.</span><span class="sxs-lookup"><span data-stu-id="baddd-125">It is only possible to have one product active for one product model at a time.</span></span>  
1. <span data-ttu-id="baddd-126">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="baddd-126">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
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
ms.openlocfilehash: 4767d5dc3944d2595a5b2a74a6d5c7c0ea0c849a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809448"
---
# <a name="approve-a-product-configuration-model"></a><span data-ttu-id="5337c-103">Approvare un modello di configurazione prodotto</span><span class="sxs-lookup"><span data-stu-id="5337c-103">Approve a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5337c-104">L'esecuzione di questa procedura richiede almeno un modello di configurazione prodotto disponibile.</span><span class="sxs-lookup"><span data-stu-id="5337c-104">Running this procedure requires that at least one product configuration model is available.</span></span> <span data-ttu-id="5337c-105">Nella procedura viene utilizzato il modello High end speaker della società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="5337c-105">This procedure uses the High end speaker model in the demo data company USMF.</span></span> <span data-ttu-id="5337c-106">Si noti che il modello è già stato approvato, ma nella procedura è incluso il processo completo.</span><span class="sxs-lookup"><span data-stu-id="5337c-106">Note that this model has already been approved, but the procedure walks you through the entire process.</span></span>

1. <span data-ttu-id="5337c-107">Fare clic su Definizione modello di variante prodotto.</span><span class="sxs-lookup"><span data-stu-id="5337c-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="5337c-108">Fare clic su Modelli di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="5337c-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="5337c-109">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="5337c-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="5337c-110">Selezionare il modello High end speaker per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="5337c-110">Select the High end speaker model for this procedure.</span></span>  
4. <span data-ttu-id="5337c-111">Fare clic su Versioni.</span><span class="sxs-lookup"><span data-stu-id="5337c-111">Click Versions.</span></span>
5. <span data-ttu-id="5337c-112">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="5337c-112">Click New.</span></span>
6. <span data-ttu-id="5337c-113">Nel campo Numero prodotto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5337c-113">In the Product number field, enter or select a value.</span></span>
    * <span data-ttu-id="5337c-114">Il riferimento a un prodotto rappresenta una versione di un modello di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="5337c-114">The reference to a product represents a version of a product configuration model.</span></span> <span data-ttu-id="5337c-115">Solo le rappresentazioni generali prodotto con la tecnologia di configurazione basata su vincoli verranno visualizzate nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="5337c-115">Only product masters which have the constraint-based configuration technology will appear in this list.</span></span>  
7. <span data-ttu-id="5337c-116">Immettere una data nel campo Dal.</span><span class="sxs-lookup"><span data-stu-id="5337c-116">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="5337c-117">Selezionare quando la versione del modello prodotto sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="5337c-117">Select when the product model version will be available.</span></span>  
8. <span data-ttu-id="5337c-118">Nel campo Data finale immettere una data.</span><span class="sxs-lookup"><span data-stu-id="5337c-118">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="5337c-119">Selezionare una data di fine se questa versione del modello prodotto scade oppure selezionare Mai.</span><span class="sxs-lookup"><span data-stu-id="5337c-119">Select an end date when this product model version will expire, or select Never.</span></span>  
9. <span data-ttu-id="5337c-120">Fare clic su Approva per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5337c-120">Click Approve to open the drop dialog.</span></span>
10. <span data-ttu-id="5337c-121">Nel campo Approvato da immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5337c-121">In the Approved by field, enter or select a value.</span></span>
    * <span data-ttu-id="5337c-122">Selezionare la persona responsabile dell'approvazione dei modelli prodotto per l'utilizzo nelle operazioni.</span><span class="sxs-lookup"><span data-stu-id="5337c-122">Select the person who is responsible for approving product models for use in operations.</span></span>  
11. <span data-ttu-id="5337c-123">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5337c-123">Click OK.</span></span>
12. <span data-ttu-id="5337c-124">Selezionare un'opzione nel campo Metodo di determinazione prezzo.</span><span class="sxs-lookup"><span data-stu-id="5337c-124">In the Pricing method field, select an option.</span></span>
    * <span data-ttu-id="5337c-125">Attivare la versione del modello prodotto.</span><span class="sxs-lookup"><span data-stu-id="5337c-125">Activate the product model version.</span></span> <span data-ttu-id="5337c-126">È possibile avere un solo prodotto attivo per un modello prodotto alla volta.</span><span class="sxs-lookup"><span data-stu-id="5337c-126">It is only possible to have one product active for one product model at a time.</span></span>  
13. <span data-ttu-id="5337c-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5337c-127">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
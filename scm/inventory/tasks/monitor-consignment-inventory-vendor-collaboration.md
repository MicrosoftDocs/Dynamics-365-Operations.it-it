---
title: Verificare l'inventario spedizione tramite la collaborazione fornitore
description: "In questa procedura viene illustrato come utilizzare la collaborazione fornitore per visualizzare le informazioni sul livello scorte di un prodotto che è stato inserito in spedizione a un cliente."
author: mkirknel
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: 567be29bd9989b3471b22d5a970ed0e51e4549ec
ms.contentlocale: it-it
ms.lasthandoff: 09/12/2017

---
# <a name="monitor-consignment-inventory-using-vendor-collaboration"></a><span data-ttu-id="4366d-103">Verificare l'inventario spedizione tramite la collaborazione fornitore</span><span class="sxs-lookup"><span data-stu-id="4366d-103">Monitor consignment inventory using vendor collaboration</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4366d-104">In questa procedura viene illustrato come utilizzare la collaborazione fornitore per visualizzare le informazioni sul livello scorte di un prodotto che è stato inserito in spedizione a un cliente.</span><span class="sxs-lookup"><span data-stu-id="4366d-104">This procedure shows how to use vendor collaboration to see information about the stock level of product that you have placed in consignment with a customer.</span></span> <span data-ttu-id="4366d-105">È inoltre possibile monitorare il consumo delle scorte quando il cliente assume la proprietà dell'inventario.</span><span class="sxs-lookup"><span data-stu-id="4366d-105">You can also monitor the consumption of the stock when the customer takes ownership of the inventory.</span></span> <span data-ttu-id="4366d-106">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="4366d-106">You can use this procedure in the USMF demo data company.</span></span> <span data-ttu-id="4366d-107">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations, versione 1611.</span><span class="sxs-lookup"><span data-stu-id="4366d-107">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="view-consumed-inventory"></a><span data-ttu-id="4366d-108">Visualizzare l'inventario consumato</span><span class="sxs-lookup"><span data-stu-id="4366d-108">View consumed inventory</span></span>
1. <span data-ttu-id="4366d-109">Andare a Collaborazione fornitore > Inventario spedizione > Prodotti entrati da inventario spedizione.</span><span class="sxs-lookup"><span data-stu-id="4366d-109">Go to Vendor collaboration > Consignment inventory > Products received from consignment inventory.</span></span>
    * <span data-ttu-id="4366d-110">Nell'elenco verranno visualizzate le righe entrata prodotti generate quando la proprietà dell'inventario di spedizione è stata modificata dal fornitore al cliente.</span><span class="sxs-lookup"><span data-stu-id="4366d-110">The list shows the product receipt lines that were generated when ownership of the consignment inventory was changed from the vendor to the customer.</span></span> <span data-ttu-id="4366d-111">Può essere necessario scorrere a destra per visualizzare le quantità e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="4366d-111">You might have to scroll to the right to see quantities and other information.</span></span> <span data-ttu-id="4366d-112">È possibile utilizzare le informazioni contenute in questo elenco per generare le fatture per il cliente.</span><span class="sxs-lookup"><span data-stu-id="4366d-112">You can use the information in this list to generate invoices for your customer.</span></span> <span data-ttu-id="4366d-113">È possibile anche esportare i dati in Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="4366d-113">You can also export the data to Microsoft Excel.</span></span>   
2. <span data-ttu-id="4366d-114">Fare clic su Visualizza ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="4366d-114">Click View purchase order.</span></span>
3. <span data-ttu-id="4366d-115">Espandere la sezione Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="4366d-115">Expand the Line details section.</span></span>
    * <span data-ttu-id="4366d-116">La riga viene contrassegnata come Spedizione e la sezione di intestazione indica che l'ordine fornitore ha stato Ricevuto.</span><span class="sxs-lookup"><span data-stu-id="4366d-116">The line is marked as Consignment, and the header section shows that the purchase order has a status of Received.</span></span>  
4. <span data-ttu-id="4366d-117">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4366d-117">Close the page.</span></span>

## <a name="view-on-hand-inventory"></a><span data-ttu-id="4366d-118">Visualizzare le scorte disponibili</span><span class="sxs-lookup"><span data-stu-id="4366d-118">View on-hand inventory</span></span>
1. <span data-ttu-id="4366d-119">Andare a Collaborazione fornitore > Inventario spedizione > Inventario spedizione disponibile.</span><span class="sxs-lookup"><span data-stu-id="4366d-119">Go to Vendor collaboration > Consignment inventory > On-hand consignment inventory.</span></span>
    * <span data-ttu-id="4366d-120">La pagina Inventario spedizione disponibile mostra le scorte di proprietà nel magazzino del cliente.</span><span class="sxs-lookup"><span data-stu-id="4366d-120">The On-hand consignment inventory page shows the stock that you own at the customer’s warehouse.</span></span> <span data-ttu-id="4366d-121">È possibile visualizzare ulteriori dimensioni, ad esempio sito e magazzino, facendo clic sulla scheda Visualizza dimensioni.</span><span class="sxs-lookup"><span data-stu-id="4366d-121">You can show additional dimensions, such as the site and warehouse, by clicking the Display dimensions tab.</span></span>   

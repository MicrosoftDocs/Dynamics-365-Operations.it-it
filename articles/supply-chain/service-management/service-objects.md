---
title: Oggetti assistenza
description: "Gli oggetti assistenza sono i cespiti cliente e i prodotti per i quali è possibile prestare assistenza."
author: YuyuScheller
manager: AnnBe
ms.date: 02/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceObjectTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 0f7b63393085858c5ff4c64ebdf5d64b3c3ccdef
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="service-objects"></a><span data-ttu-id="9fcb5-103">Oggetti assistenza</span><span class="sxs-lookup"><span data-stu-id="9fcb5-103">Service objects</span></span> 

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="9fcb5-104">Gli oggetti assistenza sono i cespiti cliente e i prodotti per i quali è possibile prestare assistenza.</span><span class="sxs-lookup"><span data-stu-id="9fcb5-104">Service objects are a customer’s assets and products for which you can perform a service.</span></span> <span data-ttu-id="9fcb5-105">A seconda del tipo di assistenza fornita, gli oggetti si distinguono in materiali e immateriali:</span><span class="sxs-lookup"><span data-stu-id="9fcb5-105">Depending on the type of service you provide, objects can be tangible or intangible:</span></span>

-  <span data-ttu-id="9fcb5-106">Gli oggetti materiali sono oggetti tangibili, ad esempio macchine o edifici, su cui è possibile effettuare assistenza costituita da attività concrete.</span><span class="sxs-lookup"><span data-stu-id="9fcb5-106">Tangible objects are things, such as a machine or a building, on which you can perform a physical service task.</span></span>

    <span data-ttu-id="9fcb5-107">Un oggetto assistenza tangibile può inoltre corrispondere a un articolo di tipo Assistenza creato nel modulo Dettagli prodotto rilasciato.</span><span class="sxs-lookup"><span data-stu-id="9fcb5-107">A tangible service object can also be an inventory item that you create in the Released product details form.</span></span> <span data-ttu-id="9fcb5-108">A seconda del gruppo di dimensioni inventariali collegato all'articolo, è possibile creare un oggetto assistenza fino al di dettaglio che include il numero di serie dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="9fcb5-108">Depending on the inventory dimension group that you attach to the item, you can create a service object to a level of detail that includes the item serial number.</span></span> <span data-ttu-id="9fcb5-109">Questa funzionalità è utile nel caso in cui sia necessario tenere traccia dell'articolo esatto rappresentato dall'oggetto assistenza.</span><span class="sxs-lookup"><span data-stu-id="9fcb5-109">This is useful when you must keep track of the exact item that the service object represents.</span></span>

    <span data-ttu-id="9fcb5-110">Un oggetto assistenza materiale può inoltre essere un articolo non direttamente correlato alla produzione o alla supply chain della società.</span><span class="sxs-lookup"><span data-stu-id="9fcb5-110">A tangible service object can also be an item that is not directly related to a company's direct production or supply chain.</span></span> <span data-ttu-id="9fcb5-111">Ad esempio, un kit di strumenti utilizzato per le riparazioni in un ordine di assistenza può essere un oggetto assistenza non incluso nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="9fcb5-111">For example, a tool kit that is used for repairs in a service order can be a service object that is not included in inventory.</span></span> <span data-ttu-id="9fcb5-112">In questo caso, non registrarlo come articolo di magazzino.</span><span class="sxs-lookup"><span data-stu-id="9fcb5-112">In this case, you don’t register it as an inventory item.</span></span>

-  <span data-ttu-id="9fcb5-113">Gli oggetti immateriali sono cose non fisiche, ad esempio un set di conti o un documento legale in cui è possibile eseguire un'attività di assistenza.</span><span class="sxs-lookup"><span data-stu-id="9fcb5-113">Intangible objects are nonphysical things, such as a set of accounts or a legal document, on which you can perform a service task.</span></span>

## <a name="example-of-an-intangible-service-object"></a><span data-ttu-id="9fcb5-114">Esempio di un oggetto assistenza immateriale</span><span class="sxs-lookup"><span data-stu-id="9fcb5-114">Example of an intangible service object</span></span>

<span data-ttu-id="9fcb5-115">La società A gestisce i record finanziari per diverse piccole imprese.</span><span class="sxs-lookup"><span data-stu-id="9fcb5-115">Company A maintains the financial records for several small companies.</span></span> <span data-ttu-id="9fcb5-116">Uno dei clienti della società A è la squadra di football locale, per cui la società A esegue la contabilità settimanale e il controllo annuale dei conti della società.</span><span class="sxs-lookup"><span data-stu-id="9fcb5-116">One of Company A's clients is the local football team, for which Company A does the weekly bookkeeping and annual audit of the club's accounts.</span></span> <span data-ttu-id="9fcb5-117">I conti della società vengono impostati nel modulo Oggetti assistenza e vengono specificati come oggetto nel contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="9fcb5-117">The club's accounts are set up in the Service objects form and specified as the object in the service agreement.</span></span> <span data-ttu-id="9fcb5-118">Sono disponibili due righe del contratto di assistenza per l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="9fcb5-118">There are two service agreement lines for the object.</span></span> <span data-ttu-id="9fcb5-119">La riga 1 è la contabilità settimanale con un intervallo settimanale assegnato alla riga, e la riga 2 è il controllo annuale con un intervallo annuale assegnato.</span><span class="sxs-lookup"><span data-stu-id="9fcb5-119">Line 1 is weekly bookkeeping with a weekly interval assigned to the line, and line 2 is the annual audit with a yearly interval assigned to it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9fcb5-120">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9fcb5-120">Related topics</span></span>

[<span data-ttu-id="9fcb5-121">Creare oggetti assistenza</span><span class="sxs-lookup"><span data-stu-id="9fcb5-121">Create service objects</span></span>](create-service-objects.md)



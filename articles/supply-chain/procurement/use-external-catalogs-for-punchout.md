---
title: Usare cataloghi esterni per PunchOut eProcurement
description: In questo argomento viene descritto come utilizzare i cataloghi esterni per creare e inviare richieste.
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchVendorPortalRequests
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ec2874fb21184ccbf4f7039acf20db399e5cf5fb
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2019
ms.locfileid: "2813341"
---
# <a name="use-external-catalogs-for-punchout-eprocurement"></a><span data-ttu-id="23716-103">Usare cataloghi esterni per PunchOut eProcurement</span><span class="sxs-lookup"><span data-stu-id="23716-103">Use external catalogs for PunchOut eProcurement</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="23716-104">Se si utilizzano i cataloghi esterni per PunchOut eProcurement, non è necessario gestire le informazioni sui prodotti dei fornitori nei propri dati master.</span><span class="sxs-lookup"><span data-stu-id="23716-104">By using external catalogs for PunchOut e-procurement, you don't have to maintain information about your vendors' products in your own master data.</span></span> <span data-ttu-id="23716-105">Il carrello nel sito Web del fornitore viene invece convertito in righe di richiesta con le informazioni sul prodotto corrette.</span><span class="sxs-lookup"><span data-stu-id="23716-105">Instead, the shopping cart on a vendor's website is converted to requisition lines that have the correct product information.</span></span> 

<span data-ttu-id="23716-106">È consigliabile evitare di conservare le descrizioni e i prezzi dei prodotti dei fornitori nei propri dati master.</span><span class="sxs-lookup"><span data-stu-id="23716-106">You should avoid maintaining the descriptions and prices of your vendors’ products in your own product master data.</span></span> <span data-ttu-id="23716-107">Utilizzare invece i cataloghi esterni per PunchOut e-procurement.</span><span class="sxs-lookup"><span data-stu-id="23716-107">Instead, use external catalogs for PunchOut e-procurement.</span></span> <span data-ttu-id="23716-108">Quando i dipendenti creano le richieste, possono accedere al sito esterno del fornitore (in altre parole lasciano il sistema per accedere al sito del fornitore).</span><span class="sxs-lookup"><span data-stu-id="23716-108">Then, when employees create requisitions, they can “punch out” to a vendor’s external catalog site (in other words, they leave your system and go to the vendor’s site).</span></span> <span data-ttu-id="23716-109">I prodotti aggiunti al carrello nel sito Web del fornitore possono quindi essere convertiti in righe di richiesta.</span><span class="sxs-lookup"><span data-stu-id="23716-109">The products that are added to the shopping cart on the vendor’s website can then be converted to requisition lines.</span></span> <span data-ttu-id="23716-110">Si ottengono così le informazioni corrette sul prodotto: ID prodotto, nome, prezzo e così via.</span><span class="sxs-lookup"><span data-stu-id="23716-110">Therefore, you get the correct product information: product ID, name, price, and so on.</span></span>

<span data-ttu-id="23716-111">Per utilizzare i cataloghi esterni, un dipendente deve creare una richiesta nella pagina **Richieste di acquisto personali**.</span><span class="sxs-lookup"><span data-stu-id="23716-111">To use external catalogs, an employee must create a requisition on the **My purchase requisitions** page.</span></span>

<span data-ttu-id="23716-112">Il dipendente che crea la richiesta è definito il preparatore della richiesta.</span><span class="sxs-lookup"><span data-stu-id="23716-112">The employee who creates a requisition is referred to as the preparer of the requisition.</span></span> <span data-ttu-id="23716-113">Un preparatore può completare le attività seguenti.</span><span class="sxs-lookup"><span data-stu-id="23716-113">As a preparer, you can complete the following tasks.</span></span>

<span data-ttu-id="23716-114">Utilizzare l'azione di riga **Cataloghi esterni** per aprire una pagina che includa tutti i cataloghi esterni disponibili per il richiedente specificato, la persona giuridica acquirente e l'unità operativa ricevente.</span><span class="sxs-lookup"><span data-stu-id="23716-114">Use the **External catalogs** line action to open a page that includes all external catalogs that are available for the specified requester, buying legal entity, and receiving operating unit.</span></span>

<span data-ttu-id="23716-115">In base alle autorizzazioni, modificare il richiedente, la persona giuridica acquirente e l'unità operativa ricevente.</span><span class="sxs-lookup"><span data-stu-id="23716-115">Depending on your permissions, change the requester, buying legal entity, and receiving operating unit.</span></span> <span data-ttu-id="23716-116">Una modifica a tali valori può modificare l'elenco dei cataloghi esterni disponibili a un richiedente.</span><span class="sxs-lookup"><span data-stu-id="23716-116">A change in those values might change the list of external catalogs that are available to a requester.</span></span> <span data-ttu-id="23716-117">I cataloghi esterni che sono disponibili variano in base ai criteri di acquisto attivi correnti per la persona giuridica acquirente o l'unità operativa ricevente.</span><span class="sxs-lookup"><span data-stu-id="23716-117">The external catalogs that are available depend on the current active purchasing policies for the buying legal entity or the receiving operating unit.</span></span> <span data-ttu-id="23716-118">Questi criteri possono consentire o impedire l'accesso a categorie di approvvigionamento specifiche.</span><span class="sxs-lookup"><span data-stu-id="23716-118">These policies can allow or prevent access to specific procurement categories.</span></span> <span data-ttu-id="23716-119">Di conseguenza, l'elenco dei cataloghi esterni che sono mappati a queste categorie di approvvigionamento può rimanerne influenzato.</span><span class="sxs-lookup"><span data-stu-id="23716-119">Therefore, the list of external catalogs that are mapped to these procurement categories can be affected.</span></span>

<span data-ttu-id="23716-120">Per ulteriori informazioni sui criteri, vedere [Panoramica dei criteri di acquisto](../procurement/purchase-policies.md).</span><span class="sxs-lookup"><span data-stu-id="23716-120">For more information about policies, see [Purchasing policies overview](../procurement/purchase-policies.md).</span></span>

- <span data-ttu-id="23716-121">Per individuare cataloghi esterni per categorie di approvvigionamento specifiche, immettere il testo nel campo di ricerca catalogo.</span><span class="sxs-lookup"><span data-stu-id="23716-121">To find external catalogs for specific procurement categories, enter text in the catalog search field.</span></span>
- <span data-ttu-id="23716-122">Per aggiungere i prodotti di un catalogo esterno disponibile nel sito Web del fornitore, fare clic sul catalogo esterno.</span><span class="sxs-lookup"><span data-stu-id="23716-122">To add products from a vendor’s external catalog on the vendor’s website, click the external catalog.</span></span> <span data-ttu-id="23716-123">Aggiungere quindi i prodotti al carrello ed effettuare il check out. Le righe del carrello verranno trasferite in Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="23716-123">Then add products to the shopping cart, and check out. The shopping cart lines will be transferred to Microsoft Dynamics 365.</span></span>

<span data-ttu-id="23716-124">Se sono disponibili più opzioni per le categorie di approvvigionamento, selezionare la categoria di approvvigionamento corretta prima di aggiungere le righe alla richiesta.</span><span class="sxs-lookup"><span data-stu-id="23716-124">If there are multiple options for procurement categories, select the correct procurement category before you add the lines to the requisition.</span></span>
<span data-ttu-id="23716-125">Dopo che le righe sono state aggiunte a una richiesta, è possibile aggiungere altre righe senza utilizzare i cataloghi esterni.</span><span class="sxs-lookup"><span data-stu-id="23716-125">After lines have been added to a requisition, you can add more lines without using external catalogs.</span></span> <span data-ttu-id="23716-126">In alternativa, è possibile continuare a utilizzare i cataloghi esterni per aggiungere le righe.</span><span class="sxs-lookup"><span data-stu-id="23716-126">Alternatively, you can continue to use external catalogs to add lines.</span></span>

<span data-ttu-id="23716-127">Quando la richiesta è pronta, utilizzare l'azione **Flusso di lavoro** > **Invia** per inoltrare la richiesta per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="23716-127">When the requisition is ready, use the **Workflow** > **Submit** action to submit it for approval.</span></span>

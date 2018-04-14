---
title: Cataloghi del call center
description: "Questo articolo descrive le funzionalità specifiche del servizio clienti per i cataloghi in Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailMCRChannelDetailPage, RetailCatalogDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: d9df8682769254f44cc23675fe2237080b447925
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="call-center-catalogs"></a><span data-ttu-id="197c3-103">Cataloghi del servizio clienti</span><span class="sxs-lookup"><span data-stu-id="197c3-103">Call center catalogs</span></span>

[!INCLUDE [banner](includes/banner.md)]

<span data-ttu-id="197c3-104">Questo articolo descrive le funzionalità specifiche del servizio clienti per i cataloghi in Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="197c3-104">This article describes the call center–specific functionality for catalogs in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="197c3-105">In un servizio clienti è possibile utilizzare i cataloghi dei prodotti per identificare quelli che si desidera offrire ai clienti.</span><span class="sxs-lookup"><span data-stu-id="197c3-105">In a call center, you can use product catalogs to identify the products that you want to offer to customers.</span></span> <span data-ttu-id="197c3-106">In genere nei servizi clienti vengono utilizzati i cataloghi stampati.</span><span class="sxs-lookup"><span data-stu-id="197c3-106">Call centers typically use printed catalogs.</span></span> <span data-ttu-id="197c3-107">La progettazione e la produzione di un catalogo stampato viene gestita al di fuori di Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="197c3-107">The design and production of a printed catalog is handled outside Dynamics 365 for Retail.</span></span> <span data-ttu-id="197c3-108">Tuttavia, è possibile creare e archiviare un formato digitale di un catalogo utilizzando le stesse pagine che si utilizzano per impostare i cataloghi al dettaglio online.</span><span class="sxs-lookup"><span data-stu-id="197c3-108">However, you can create and store a digital form of a catalog by using the same pages that you use to set up online retail catalogs.</span></span> <span data-ttu-id="197c3-109">Prima di poter creare un catalogo, è necessario impostare gli assortimenti dei prodotti e assegnare gli assortimenti a un servizio clienti.</span><span class="sxs-lookup"><span data-stu-id="197c3-109">Before you can create a catalog, you must set up product assortments and assign the assortments to a call center.</span></span> <span data-ttu-id="197c3-110">Successivamente, è possibile aggiungere i prodotti al catalogo selezionandoli da questi assortimenti.</span><span class="sxs-lookup"><span data-stu-id="197c3-110">You then add products to the catalog by selecting products from these assortments.</span></span> <span data-ttu-id="197c3-111">Al termine dell'aggiunta dei prodotti al catalogo e del completamento del catalogo, è necessario convalidare quest'ultimo per verificare i dati.</span><span class="sxs-lookup"><span data-stu-id="197c3-111">After products have been added to the catalog, and the catalog is complete, you must validate the catalog to verify the data.</span></span> <span data-ttu-id="197c3-112">Successivamente, è necessario inviare il catalogo per la revisione e l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="197c3-112">You must then submit the catalog for review and approval.</span></span> <span data-ttu-id="197c3-113">Dopo l'approvazione, il catalogo può essere pubblicato.</span><span class="sxs-lookup"><span data-stu-id="197c3-113">After the catalog is approved, it can be published.</span></span> <span data-ttu-id="197c3-114">Quando viene creato un catalogo del servizio clienti, è possibile creare uno snapshot dei dati del catalogo al momento della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="197c3-114">When a call center catalog is created, you can take a snapshot of the catalog data at the time that the catalog is published.</span></span> <span data-ttu-id="197c3-115">Questa funzionalità dello snapshot consente di accedere a una determinata versione del catalogo anche se quest'ultimo viene modificato e aggiornato in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="197c3-115">This snapshot functionality lets you access a particular version of the catalog even if the catalog is later changed and updated.</span></span> <span data-ttu-id="197c3-116">I cataloghi dei servizi clienti possono inoltre essere configurati per includere le seguenti funzionalità facoltative:</span><span class="sxs-lookup"><span data-stu-id="197c3-116">Call center catalogs can also be set up to include the following optional features:</span></span>

-   <span data-ttu-id="197c3-117">**Codici di origine** - I codici di origine vengono utilizzati per tenere traccia delle risposte dei clienti a specifici messaggi di posta elettronica sul catalogo.</span><span class="sxs-lookup"><span data-stu-id="197c3-117">**Source codes** – Source codes are used to track the customer response to specific catalog mailings.</span></span>
-   <span data-ttu-id="197c3-118">**Prodotti gratuiti** - I prodotti possono essere inclusi in un ordine di un cliente senza costi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="197c3-118">**Free products** – Products can be included in a customer's order at no additional charge.</span></span> <span data-ttu-id="197c3-119">Questi prodotti vengono automaticamente aggiunti all'ordine quando il codice di origine del catalogo viene immesso nell'ordine.</span><span class="sxs-lookup"><span data-stu-id="197c3-119">These products are automatically added to an order when the source code for the catalog is entered into the order.</span></span>
-   <span data-ttu-id="197c3-120">**Script** - Gli script sono testi che un dipendente del call center legge a un cliente mentre crea un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="197c3-120">**Scripts** – Scripts are texts that a call center worker reads to a customer when a sales order is being created.</span></span> <span data-ttu-id="197c3-121">Gli script possono includere auguri o suggerimenti di acquisti.</span><span class="sxs-lookup"><span data-stu-id="197c3-121">Scripts can include greetings or purchase suggestions.</span></span>
-   <span data-ttu-id="197c3-122">**Layout di pagina** - Un layout di pagina cattura la posizione dei prodotti nella pagina nel catalogo stampato.</span><span class="sxs-lookup"><span data-stu-id="197c3-122">**Page layout** – A page layout captures the page position of products in the printed catalog.</span></span> <span data-ttu-id="197c3-123">Queste informazioni vengono utilizzate per il report di analisi area catalogo.</span><span class="sxs-lookup"><span data-stu-id="197c3-123">This information is used for the catalog area analysis report.</span></span>






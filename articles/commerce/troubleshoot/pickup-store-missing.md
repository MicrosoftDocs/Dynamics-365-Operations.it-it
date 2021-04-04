---
title: Il punto vendita al dettaglio non viene visualizzato nell'elenco dei punti vendita presso cui effettuare il ritiro
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando un punto vendita al dettaglio non viene visualizzato nell'elenco dei punti vendita presso i quali è possibile ritirare gli articoli.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 652f5f1a779a412c21c18814071ba0fb7dd2e155
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585400"
---
# <a name="retail-store-doesnt-appear-in-the-list-of-stores-to-pick-up-from"></a><span data-ttu-id="08c22-103">Il punto vendita al dettaglio non viene visualizzato nell'elenco dei punti vendita presso cui effettuare il ritiro</span><span class="sxs-lookup"><span data-stu-id="08c22-103">Retail store doesn't appear in the list of stores to pick up from</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="08c22-104">Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando un punto vendita al dettaglio non viene visualizzato nell'elenco dei punti vendita presso i quali è possibile ritirare gli articoli.</span><span class="sxs-lookup"><span data-stu-id="08c22-104">This topic provides troubleshooting guidance that can help when a retail store doesn't appear in the list of stores where items can be picked up.</span></span>

## <a name="description"></a><span data-ttu-id="08c22-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08c22-105">Description</span></span>

<span data-ttu-id="08c22-106">Un punto vendita al dettaglio non viene visualizzato nell'elenco dei punti vendita presso i quali è possibile ritirare gli articoli.</span><span class="sxs-lookup"><span data-stu-id="08c22-106">A retail store doesn't appear in the list of stores where items can be picked up.</span></span>

## <a name="resolution"></a><span data-ttu-id="08c22-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="08c22-107">Resolution</span></span>

### <a name="configure-the-longitude-and-latitude-for-the-store-address-in-commerce-headquarters"></a><span data-ttu-id="08c22-108">Configurare la longitudine e la latitudine per l'indirizzo del punto vendita in Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="08c22-108">Configure the longitude and latitude for the store address in Commerce headquarters</span></span>

<span data-ttu-id="08c22-109">Per configurare la longitudine e la latitudine per l'indirizzo del punto vendita in Commerce Headquarters, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="08c22-109">To configure the longitude and latitude for the store address in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="08c22-110">Passare a **Retail e Commerce \> Canali \> Punti vendita \> Tutti i punti vendita**.</span><span class="sxs-lookup"><span data-stu-id="08c22-110">Go to **Retail and Commerce \> Channels \> Stores \> All stores**.</span></span>
1. <span data-ttu-id="08c22-111">Trovare il punto vendita che deve essere visualizzato tra le opzioni di ritiro nel sito di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="08c22-111">Find the store that you want to appear among the pickup options on the e-commerce site.</span></span> <span data-ttu-id="08c22-112">Prendere nota del relativo valore **Numero unità operativa**.</span><span class="sxs-lookup"><span data-stu-id="08c22-112">Make a note of its **Operating unit number** value.</span></span>
1. <span data-ttu-id="08c22-113">Selezionare **Amministrazione organizzazione \> Organizzazioni \> Unità operative**.</span><span class="sxs-lookup"><span data-stu-id="08c22-113">Go to **Organization administration \> Organizations \> Operating units**.</span></span>
1. <span data-ttu-id="08c22-114">Cercare il numero di unità operativa annotata in precedenza, quindi selezionare l'unità operativa nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="08c22-114">Search for the operating unit number that you noted earlier, and then select the operating unit in the search results.</span></span>
1. <span data-ttu-id="08c22-115">Nella Scheda dettaglio **Indirizzi**, selezionare **Altre opzioni** e quindi selezionare **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="08c22-115">On the **Addresses** FastTab, select **More options**, and then select **Advanced**.</span></span>
1. <span data-ttu-id="08c22-116">Nella Scheda dettaglio **Generale**, assicurarsi che i campi **Longitudine** e **Latitudine** siano impostati correttamente.</span><span class="sxs-lookup"><span data-stu-id="08c22-116">On the **General** FastTab, make sure that the **Longitude** and **Latitude** fields are correctly set.</span></span> <span data-ttu-id="08c22-117">Come parte di questo passaggio, assicurarsi che i valori siano specificati correttamente come numeri positivi o negativi.</span><span class="sxs-lookup"><span data-stu-id="08c22-117">As part of this step, make sure that the values are correctly specified as positive or negative numbers.</span></span>

### <a name="configure-fulfillment-groups-in-commerce-headquarters"></a><span data-ttu-id="08c22-118">Configurare gruppi di adempimento in Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="08c22-118">Configure fulfillment groups in Commerce headquarters</span></span>

<span data-ttu-id="08c22-119">Per configurare gruppi di adempimento in Commerce Headquarters, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="08c22-119">To configure fulfillment groups in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="08c22-120">Andare a **Retail e Commerce \> Canali \> Punti vendita online**.</span><span class="sxs-lookup"><span data-stu-id="08c22-120">Go to **Retail and Commerce \> Channels \> Online stores**.</span></span>
1. <span data-ttu-id="08c22-121">Selezionare il punto vendita online da configurare.</span><span class="sxs-lookup"><span data-stu-id="08c22-121">Select the online store to configure.</span></span>
1. <span data-ttu-id="08c22-122">Nel riquadro Azioni, selezionare **Imposta**, quindi selezionare **Assegnazione gruppo di adempimento**.</span><span class="sxs-lookup"><span data-stu-id="08c22-122">On the Action Pane, select **Set up**, and then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="08c22-123">Nella pagina **Assegnazione gruppo di adempimento**, selezionare il gruppo di adempimento per il punto vendita online.</span><span class="sxs-lookup"><span data-stu-id="08c22-123">On the **Fulfillment group assignment** page, select the fulfillment group for the online store.</span></span>
1. <span data-ttu-id="08c22-124">In **Impostazione**, assicurarsi che il punto vendita al dettaglio sia configurato correttamente per il gruppo di adempimento.</span><span class="sxs-lookup"><span data-stu-id="08c22-124">Under **Setup**, make sure that the retail store is correctly configured for the fulfillment group.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="08c22-125">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="08c22-125">Additional resources</span></span> 

[<span data-ttu-id="08c22-126">Creare una unità operativa</span><span class="sxs-lookup"><span data-stu-id="08c22-126">Create an operating unit</span></span>](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit)

[<span data-ttu-id="08c22-127">Impostare un canale online</span><span class="sxs-lookup"><span data-stu-id="08c22-127">Set up an online channel</span></span>](../channel-setup-online.md)

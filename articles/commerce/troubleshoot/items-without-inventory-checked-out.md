---
title: Gli articoli non disponibili possono essere acquistati
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando i clienti possono aggiungere articoli non disponibili al carrello e procedere al pagamento.
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
ms.openlocfilehash: 6df9c77248c7f4e16765b98327fe5838f0fce7e4
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585391"
---
# <a name="items-without-inventory-can-be-checked-out"></a><span data-ttu-id="955f1-103">Gli articoli non disponibili possono essere acquistati</span><span class="sxs-lookup"><span data-stu-id="955f1-103">Items without inventory can be checked out</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="955f1-104">Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando i clienti possono aggiungere articoli non disponibili al carrello e procedere al pagamento.</span><span class="sxs-lookup"><span data-stu-id="955f1-104">This topic provides troubleshooting guidance that can help when customers can add out-of-stock items to their cart and proceed to checkout.</span></span>

## <a name="description"></a><span data-ttu-id="955f1-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="955f1-105">Description</span></span>

<span data-ttu-id="955f1-106">Gli utenti possono aggiungere un articolo al carrello, anche se non ci sono scorte disponibili nel punto vendita, e procedere alla pagina di pagamento.</span><span class="sxs-lookup"><span data-stu-id="955f1-106">Users can add an item to their cart, even though there is no on-hand inventory in the store, and then proceed to the checkout page.</span></span>

## <a name="resolution"></a><span data-ttu-id="955f1-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="955f1-107">Resolution</span></span>

### <a name="enable-the-show-out-of-stock-errors-property-in-commerce-site-builder"></a><span data-ttu-id="955f1-108">Abilitare la proprietà Mostra errori scorte esaurite in Creazione di siti di Commerce</span><span class="sxs-lookup"><span data-stu-id="955f1-108">Enable the Show Out Of Stock Errors property in Commerce site builder</span></span>

<span data-ttu-id="955f1-109">Per abilitare la proprietà **Mostra errori scorte esaurite** in Creazione di siti di Commerce, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="955f1-109">To enable the **Show Out Of Stock Errors** property in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="955f1-110">Selezionare il sito sul quale si sta lavorando.</span><span class="sxs-lookup"><span data-stu-id="955f1-110">Select the site that you're working on.</span></span>
1. <span data-ttu-id="955f1-111">Nel pannello di navigazione a sinistra, selezionare **Pagine**.</span><span class="sxs-lookup"><span data-stu-id="955f1-111">In the left navigation, select **Pages**.</span></span>
1. <span data-ttu-id="955f1-112">Selezionare **CartPage** per aprire questa pagina.</span><span class="sxs-lookup"><span data-stu-id="955f1-112">Select **CartPage** to open it.</span></span>
1. <span data-ttu-id="955f1-113">Selezionare lo slot **Carrello 1**, selezionare **Modifica** quindi nel riquadro delle proprietà, selezionare la casella di controllo **Mostra errori scorte esaurite**.</span><span class="sxs-lookup"><span data-stu-id="955f1-113">Select the **Cart 1** slot, select **Edit**, and then, in the properties pane, select the **Show Out Of Stock Errors** check box.</span></span>
1. <span data-ttu-id="955f1-114">Salva e pubblica la pagina.</span><span class="sxs-lookup"><span data-stu-id="955f1-114">Save and publish the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="955f1-115">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="955f1-115">Additional resources</span></span>

[<span data-ttu-id="955f1-116">Applicare le impostazioni delle scorte</span><span class="sxs-lookup"><span data-stu-id="955f1-116">Apply inventory settings</span></span>](../inventory-settings.md)

[<span data-ttu-id="955f1-117">Calcolare la disponibilità scorte per i canali di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="955f1-117">Calculate inventory availability for retail channels</span></span>](../calculated-inventory-retail-channels.md)

[<span data-ttu-id="955f1-118">Configurare buffer scorte e livelli scorte</span><span class="sxs-lookup"><span data-stu-id="955f1-118">Configure inventory buffers and inventory levels</span></span>](../inventory-buffers-levels.md)

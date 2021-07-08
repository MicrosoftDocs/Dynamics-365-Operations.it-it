---
title: Il codice fornitore non è autorizzato per un prodotto e una data specifici
description: Quando tenti di stabilizzare un ordine pianificato o di aggiungere una riga a un ordine di acquisto, viene visualizzato un messaggio di errore che indica che il codice fornitore non è autorizzato per un prodotto e una data.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO_ReqTransPoMarkFirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e6b1189e4fedfdb029f4b4503f0635133df9d87e
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294113"
---
# <a name="vendor-code-isnt-authorized-for-a-specific-product-and-date"></a><span data-ttu-id="448a7-103">Il codice fornitore non è autorizzato per un prodotto e una data specifici</span><span class="sxs-lookup"><span data-stu-id="448a7-103">Vendor code isn't authorized for a specific product and date</span></span>

<span data-ttu-id="448a7-104">Codice errore: SYP4881415</span><span class="sxs-lookup"><span data-stu-id="448a7-104">Error code: SYP4881415</span></span>

## <a name="symptoms"></a><span data-ttu-id="448a7-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="448a7-105">Symptoms</span></span>

<span data-ttu-id="448a7-106">Quando tenti di stabilizzare un ordine pianificato o aggiungere una riga a un ordine fornitore viene visualizzato il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="448a7-106">When you try to firm a planned order or add a line to a purchase order, you receive the following error message:</span></span>

> <span data-ttu-id="448a7-107">Codice fornitore %1 non autorizzato per %2 in %3.</span><span class="sxs-lookup"><span data-stu-id="448a7-107">Vendor code %1 is not authorized for %2 on %3.</span></span>

## <a name="cause"></a><span data-ttu-id="448a7-108">Causa</span><span class="sxs-lookup"><span data-stu-id="448a7-108">Cause</span></span>

<span data-ttu-id="448a7-109">L'errore si verifica perché il campo **Metodo di controllo fornitore approvato** è impostato su *Solo avviso* o *Non consentito* per il prodotto specificato e il fornitore non è attualmente autorizzato a fornire quel prodotto.</span><span class="sxs-lookup"><span data-stu-id="448a7-109">The error occurs because the **Approved vendor check method** field is set to *Warning only* or *Not allowed* for the specified product, and the vendor isn't currently authorized to supply that product.</span></span>

## <a name="resolution"></a><span data-ttu-id="448a7-110">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="448a7-110">Resolution</span></span>

<span data-ttu-id="448a7-111">Per risolvere questo problema, disabilita il controllo del fornitore per il prodotto in questione o approva il fornitore.</span><span class="sxs-lookup"><span data-stu-id="448a7-111">To fix this issue, either disable the vendor check for the relevant product or approve the vendor.</span></span>

<span data-ttu-id="448a7-112">Per disabilitare il controllo del fornitore per un prodotto, attieniti alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="448a7-112">To disable the vendor check for a product, follow these steps.</span></span>

1. <span data-ttu-id="448a7-113">Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="448a7-113">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="448a7-114">Apri il prodotto rilevante.</span><span class="sxs-lookup"><span data-stu-id="448a7-114">Open the relevant product.</span></span>
1. <span data-ttu-id="448a7-115">Nella scheda dettaglio **Acquisto** imposta il campo **Metodo di controllo fornitore approvato** su un valore diverso da *Solo avviso* o *Non consentito*.</span><span class="sxs-lookup"><span data-stu-id="448a7-115">On the **Purchase** FastTab, set the **Approved vendor check method** field to a value other than *Warning only* or *Not allowed*.</span></span>

<span data-ttu-id="448a7-116">Per approvare un fornitore per un prodotto, attieniti alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="448a7-116">To approve a vendor for a product, follow these steps.</span></span>

1. <span data-ttu-id="448a7-117">Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="448a7-117">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="448a7-118">Apri l'articolo rilevante.</span><span class="sxs-lookup"><span data-stu-id="448a7-118">Open the relevant item.</span></span>
1. <span data-ttu-id="448a7-119">Nel riquadro azioni, nella scheda **Acquisto**, nel gruppo **Fornitore approvato**, seleziona **Imposta**.</span><span class="sxs-lookup"><span data-stu-id="448a7-119">On the Action Pane, on the **Purchase** tab, in the **Approved vendor** group, select **Setup**.</span></span>
1. <span data-ttu-id="448a7-120">Nella pagina elenco **Fornitore approvato** aggiungi una riga alla griglia e imposta i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="448a7-120">On the **Approved vendor** list page, add a row to the grid, and set the following values for it:</span></span>

    - <span data-ttu-id="448a7-121">**Fornitore** – Seleziona il fornitore da approvare per il prodotto corrente.</span><span class="sxs-lookup"><span data-stu-id="448a7-121">**Vendor** – Select the vendor to approve for the current product.</span></span>
    - <span data-ttu-id="448a7-122">**Data di validità** – Seleziona la data di inizio dell'approvazione del fornitore.</span><span class="sxs-lookup"><span data-stu-id="448a7-122">**Effective date** – Select the first date that the vendor is approved for.</span></span>
    - <span data-ttu-id="448a7-123">**Data di scadenza** – Seleziona la data di fine dell'approvazione del fornitore.</span><span class="sxs-lookup"><span data-stu-id="448a7-123">**Expiration date** – Select the last date that the vendor is approved for.</span></span>

<span data-ttu-id="448a7-124">Per informazioni, vedi [Approvare i fornitori per prodotti specifici](/dynamics365/supply-chain/procurement/tasks/approve-vendors-specific-products.md).</span><span class="sxs-lookup"><span data-stu-id="448a7-124">For more information, see [Approve vendors for specific products](/dynamics365/supply-chain/procurement/tasks/approve-vendors-specific-products.md).</span></span>

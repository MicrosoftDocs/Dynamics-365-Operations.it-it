---
title: L'IVA negli ordini online è calcolata in modo errato
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando l'IVA negli ordini online viene calcolata in modo errato o quando la fascia IVA nella riga di vendita non è impostata correttamente.
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
ms.openlocfilehash: 421df7545e285950ef8a3c4b753c8c6dc5f26422
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585389"
---
# <a name="taxes-on-online-orders-are-incorrectly-calculated"></a><span data-ttu-id="71f6b-103">L'IVA negli ordini online è calcolata in modo errato</span><span class="sxs-lookup"><span data-stu-id="71f6b-103">Taxes on online orders are incorrectly calculated</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="71f6b-104">Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando l'IVA negli ordini online viene calcolata in modo errato o quando la fascia IVA nella riga di vendita non è impostata correttamente.</span><span class="sxs-lookup"><span data-stu-id="71f6b-104">This topic provides troubleshooting guidance that can help when taxes on online orders are incorrectly calculated, or when the tax group on the sales line isn't correctly set.</span></span>

## <a name="description"></a><span data-ttu-id="71f6b-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71f6b-105">Description</span></span>

<span data-ttu-id="71f6b-106">Quando viene effettuato un ordine di e-commerce, l'IVA viene calcolata in modo errato o la fascia IVA nella riga di vendita è impostata in modo errato.</span><span class="sxs-lookup"><span data-stu-id="71f6b-106">When an e-commerce order is placed, the taxes are incorrectly calculated, or the tax group on the sales line is incorrectly set.</span></span>

## <a name="resolution"></a><span data-ttu-id="71f6b-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="71f6b-107">Resolution</span></span>

### <a name="configure-the-sales-tax-for-a-retail-store-in-commerce-headquarters"></a><span data-ttu-id="71f6b-108">Configurare l'IVA per un punto vendita al dettaglio in Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="71f6b-108">Configure the sales tax for a retail store in Commerce headquarters</span></span>

<span data-ttu-id="71f6b-109">Per configurare l'IVA per un punto vendita al dettaglio in Commerce Headquarters, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="71f6b-109">To configure the sales tax for a retail store in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="71f6b-110">Selezionare **Retail e Commerce \> Canali \> Tutti i punti vendita**.</span><span class="sxs-lookup"><span data-stu-id="71f6b-110">Go to **Retail and Commerce \> Channels \> All stores**.</span></span>
1. <span data-ttu-id="71f6b-111">Selezionare il punto vendita per configurare l'IVA.</span><span class="sxs-lookup"><span data-stu-id="71f6b-111">Select the store to configure sales tax for.</span></span>
1. <span data-ttu-id="71f6b-112">Nella Scheda dettaglio **Generale**, nella sezione **IVA**, configurare le informazioni sull'IVA per il punto vendita.</span><span class="sxs-lookup"><span data-stu-id="71f6b-112">On the **General** FastTab, in the **Sales tax** section, configure the sales tax information for the store.</span></span>

> [!NOTE]
> <span data-ttu-id="71f6b-113">Per il ritiro del prodotto presso un punto vendita, la fascia IVA proviene dal punto vendita selezionato per il ritiro.</span><span class="sxs-lookup"><span data-stu-id="71f6b-113">For product pickup from a store, the tax group comes from the store that is selected for pickup.</span></span> <span data-ttu-id="71f6b-114">Per ulteriori informazioni, vedere [Impostare altre opzioni IVA per i punti vendita](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span><span class="sxs-lookup"><span data-stu-id="71f6b-114">For more information, see [Set other tax options for stores](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span></span>

### <a name="configure-the-sales-tax-for-a-customers-address-in-commerce-headquarters"></a><span data-ttu-id="71f6b-115">Configurare l'IVA per l'indirizzo di un cliente in Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="71f6b-115">Configure the sales tax for a customer's address in Commerce headquarters</span></span>

<span data-ttu-id="71f6b-116">Per configurare l'IVA per l'indirizzo di un cliente in Commerce Headquarters, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="71f6b-116">To configure the sales tax for a customer's address in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="71f6b-117">Andare a **Contabilità clienti \> Clienti \> Tutti i clienti**.</span><span class="sxs-lookup"><span data-stu-id="71f6b-117">Go to **Accounts receivable \> Customers \> All customers**.</span></span>
1. <span data-ttu-id="71f6b-118">Selezionare il cliente per cui configurare l'IVA.</span><span class="sxs-lookup"><span data-stu-id="71f6b-118">Select the customer to configure sales taxes for.</span></span>
1. <span data-ttu-id="71f6b-119">Nella Scheda dettaglio **Indirizzi** selezionare l'indirizzo per cui configurare l'IVA, selezionare **Altre opzioni** e quindi selezionare **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="71f6b-119">On the **Addresses** FastTab, select the address to configure sales taxes for, select **More options**, and then select **Advanced**.</span></span>
1. <span data-ttu-id="71f6b-120">Nella Scheda dettaglio **Generale**, selezionare la **Fascia IVA**.</span><span class="sxs-lookup"><span data-stu-id="71f6b-120">On the **General** FastTab, select the **Tax group**.</span></span>
1. <span data-ttu-id="71f6b-121">Nel capo **Fascia IVA** selezionare il valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="71f6b-121">In the **Sales tax** field, select the appropriate value.</span></span>

> [!NOTE]
> <span data-ttu-id="71f6b-122">Per la spedizione che comporta l'IVA nell'indirizzo del cliente, l'indirizzo di consegna della riga determina la fascia IVA per la riga.</span><span class="sxs-lookup"><span data-stu-id="71f6b-122">For shipping that involves sales tax on the customer's address, the delivery address of the line determines the tax group for the line.</span></span> <span data-ttu-id="71f6b-123">Se il cliente effettua la spedizione a un indirizzo esistente con una fascia IVA già configurata, verrà utilizzata la fascia IVA esistente.</span><span class="sxs-lookup"><span data-stu-id="71f6b-123">If the customer is shipping to an existing address that has a tax group that is already configured, the existing tax group will be used.</span></span> <span data-ttu-id="71f6b-124">Per impostazione predefinita, gli indirizzi non hanno una fascia IVA quando vengono creati.</span><span class="sxs-lookup"><span data-stu-id="71f6b-124">By default, addresses don't have a tax group when they are created.</span></span>

### <a name="configure-general-sales-tax-groups-in-commerce-headquarters"></a><span data-ttu-id="71f6b-125">Configurare le fasce IVA generali in Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="71f6b-125">Configure general sales tax groups in Commerce headquarters</span></span>

<span data-ttu-id="71f6b-126">Per configurare fasce IVA generali in Commerce Headquarters, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="71f6b-126">To configure general sales tax groups in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="71f6b-127">Selezionare **Imposta \> Imposte indirette \> IVA \> Fascia IVA**.</span><span class="sxs-lookup"><span data-stu-id="71f6b-127">Go to **Tax \> Indirect taxes \> Sales tax \> Sales tax group**.</span></span>
1. <span data-ttu-id="71f6b-128">Nel riquadro di spostamento a sinistra, selezionare la fascia IVA da configurare.</span><span class="sxs-lookup"><span data-stu-id="71f6b-128">In the left navigation, select the tax group to configure.</span></span>
1. <span data-ttu-id="71f6b-129">Nella Scheda dettaglio **Imposta in base alla destinazione vendita al dettaglio**, configurare le imposte per la fascia IVA.</span><span class="sxs-lookup"><span data-stu-id="71f6b-129">On the **Retail destination based tax** FastTab, configure the taxes for the sales tax group.</span></span>

> [!NOTE]
> <span data-ttu-id="71f6b-130">Per la spedizione che non prevede l'IVA nell'indirizzo del cliente, l'indirizzo di consegna della riga e le imposte basate sulla destinazione configurate per la fascia IVA determinano la fascia IVA.</span><span class="sxs-lookup"><span data-stu-id="71f6b-130">For shipping that doesn't involve sales tax on the customer's address, the delivery address of the line and the destination-based taxes that are configured for the tax group determine the tax group.</span></span> <span data-ttu-id="71f6b-131">Per ulteriori informazioni, vedere [Impostare le imposte per i punti vendita online in base alla destinazione](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span><span class="sxs-lookup"><span data-stu-id="71f6b-131">For more information, see [Set up taxes for online stores based on destination](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="71f6b-132">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="71f6b-132">Additional resources</span></span>

[<span data-ttu-id="71f6b-133">Configurare l'IVA per gli ordini online</span><span class="sxs-lookup"><span data-stu-id="71f6b-133">Configure sales tax for online orders</span></span>](../sales-tax-config.md)

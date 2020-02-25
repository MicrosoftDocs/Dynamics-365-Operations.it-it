---
title: Creare un cliente predefinito
description: Questo argomento descrive come creare un cliente predefinito da utilizzare durante la creazione di un canale in Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 9e1087821b357c578993cdd5742399c5ec0ecc95
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001808"
---
# <a name="create-a-default-customer"></a><span data-ttu-id="d77a0-103">Creare un cliente predefinito</span><span class="sxs-lookup"><span data-stu-id="d77a0-103">Create a default customer</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="d77a0-104">Questo argomento descrive come creare un cliente predefinito da utilizzare durante la creazione di un canale in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d77a0-104">This topic describes how to create a default customer to use when creating a channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d77a0-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="d77a0-105">Overview</span></span>

<span data-ttu-id="d77a0-106">Quando si crea un canale di vendita al dettaglio o online, sarà necessario fornire un cliente predefinito.</span><span class="sxs-lookup"><span data-stu-id="d77a0-106">When creating a retail or online channel, you will need to provide a default customer.</span></span> <span data-ttu-id="d77a0-107">Un cliente predefinito può essere creato facilmente dopo aver creato il gruppo di clienti e la rubrica clienti.</span><span class="sxs-lookup"><span data-stu-id="d77a0-107">A default customer can easily be created after first creating the customer group and customer address book.</span></span>

## <a name="create-a-customer-group"></a><span data-ttu-id="d77a0-108">Creare un gruppo di clienti</span><span class="sxs-lookup"><span data-stu-id="d77a0-108">Create a customer group</span></span>

<span data-ttu-id="d77a0-109">Se non esistono ancora gruppi di clienti, è possibile crearne uno.</span><span class="sxs-lookup"><span data-stu-id="d77a0-109">If no customer groups exist yet, you can create one.</span></span> <span data-ttu-id="d77a0-110">Esempi possono essere gruppi per rappresentare diversi gruppi di clienti, come Ingrosso, Al dettaglio, Internet, Dipendenti, ecc.</span><span class="sxs-lookup"><span data-stu-id="d77a0-110">Examples may be groups to represent different customer groups, such as wholesale, retail, Internet, Employees, etc.</span></span>

<span data-ttu-id="d77a0-111">Per creare un gruppo di clienti, completare i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="d77a0-111">To create a customer group, follow these steps.</span></span>

1. <span data-ttu-id="d77a0-112">Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Clienti \> Gruppi di clienti**.</span><span class="sxs-lookup"><span data-stu-id="d77a0-112">In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> Customer groups**.</span></span>
1. <span data-ttu-id="d77a0-113">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="d77a0-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="d77a0-114">Nella casella **Gruppo di clienti** immettere un ID gruppo di clienti.</span><span class="sxs-lookup"><span data-stu-id="d77a0-114">In the **Customer group** box, enter a customer group ID.</span></span>
1. <span data-ttu-id="d77a0-115">Immettere una descrizione appropriata nella casella **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="d77a0-115">In the **Description** box, enter an appropriate description.</span></span>
1. <span data-ttu-id="d77a0-116">Immettere un valore appropriato nella casella **Termini di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="d77a0-116">In the **Terms of payment** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="d77a0-117">Nella casella **Tempo tra la data di scadenza della fattura e la data di pagamento**, immettere un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="d77a0-117">In the **Time between invoice due date and payment date** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="d77a0-118">Nella casella **Gruppo imposta predefinito**, immettere un gruppo di imposta, se applicabile.</span><span class="sxs-lookup"><span data-stu-id="d77a0-118">In the **Default tax group** box, enter a tax group if applicable.</span></span>
1. <span data-ttu-id="d77a0-119">Selezionare la casella di controllo **Prezzi IVA inclusa** se applicabile.</span><span class="sxs-lookup"><span data-stu-id="d77a0-119">Select the **Prices include sales tax** check box if applicable.</span></span>
1. <span data-ttu-id="d77a0-120">Nella casella **Motivo di annullamento predefinito**, immettere un valore appropriato, se applicabile.</span><span class="sxs-lookup"><span data-stu-id="d77a0-120">In the **Default write-off reason** box, enter an appropriate value, if applicable.</span></span>

<span data-ttu-id="d77a0-121">L'immagine seguente mostra diversi gruppi di clienti configurati.</span><span class="sxs-lookup"><span data-stu-id="d77a0-121">The following image shows several configured customer groups.</span></span>

![Gruppi di clienti](media/customer-groups.png)

## <a name="create-a-customer-address-book"></a><span data-ttu-id="d77a0-123">Creare una nuova rubrica clienti</span><span class="sxs-lookup"><span data-stu-id="d77a0-123">Create a customer address book</span></span>

<span data-ttu-id="d77a0-124">Un cliente deve essere associato a una rubrica.</span><span class="sxs-lookup"><span data-stu-id="d77a0-124">A customer needs to be associated with an address book.</span></span> <span data-ttu-id="d77a0-125">Se una rubrica non è ancora stata creata, sarà necessario crearne una.</span><span class="sxs-lookup"><span data-stu-id="d77a0-125">If one has not yet been created, then you will need to create one.</span></span>

<span data-ttu-id="d77a0-126">Per creare una rubrica clienti, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="d77a0-126">To create a customer address book, follow these steps.</span></span>

1. <span data-ttu-id="d77a0-127">Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione canale \> Rubriche**.</span><span class="sxs-lookup"><span data-stu-id="d77a0-127">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Address Books**.</span></span>
1. <span data-ttu-id="d77a0-128">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="d77a0-128">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="d77a0-129">Nella casella **Nome** immettere un nome.</span><span class="sxs-lookup"><span data-stu-id="d77a0-129">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="d77a0-130">Nella casella **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="d77a0-130">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="d77a0-131">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d77a0-131">On the action pane, select **Save**.</span></span>

<span data-ttu-id="d77a0-132">L'immagine seguente mostra un esempio di rubrica.</span><span class="sxs-lookup"><span data-stu-id="d77a0-132">The following image shows an example address book.</span></span>

![Rubrica](media/address-book.png)

## <a name="create-a-default-customer"></a><span data-ttu-id="d77a0-134">Creare un cliente predefinito</span><span class="sxs-lookup"><span data-stu-id="d77a0-134">Create a default customer</span></span>

<span data-ttu-id="d77a0-135">Per creare un cliente predefinito, completare i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="d77a0-135">To create a default customer, follow these steps.</span></span>

1. <span data-ttu-id="d77a0-136">Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Clienti \> Tutti i clienti**.</span><span class="sxs-lookup"><span data-stu-id="d77a0-136">In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> All customers**.</span></span>
1. <span data-ttu-id="d77a0-137">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="d77a0-137">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="d77a0-138">Nell'elenco a discesa **Tipo** selezionare "Persona".</span><span class="sxs-lookup"><span data-stu-id="d77a0-138">In the **Type** drop-down list, select "Person".</span></span>
1. <span data-ttu-id="d77a0-139">Nell'elenco a discesa **Conto cliente**, selezionare o inserire un numero di conto (ad esempio "100001").</span><span class="sxs-lookup"><span data-stu-id="d77a0-139">In the **Customer account** drop-down list, select or enter an account number (for example, "100001").</span></span>
1. <span data-ttu-id="d77a0-140">Nell'elenco a discesa **Nome**, selezionare o inserire un nome (ad esempio, "Predefinito").</span><span class="sxs-lookup"><span data-stu-id="d77a0-140">In the **First name** drop-down list, select or enter a name (for example, "Default").</span></span>
1. <span data-ttu-id="d77a0-141">Nell'elenco a discesa **Secondo nome**, selezionare o inserire un nome (ad esempio, "Al dettaglio").</span><span class="sxs-lookup"><span data-stu-id="d77a0-141">In the **Middle name** drop-down list, select or enter a name (for example, "Retail").</span></span>
1. <span data-ttu-id="d77a0-142">Nell'elenco a discesa **Cognome**, selezionare o inserire un nome (ad esempio, "Cliente").</span><span class="sxs-lookup"><span data-stu-id="d77a0-142">In the **Last name** drop-down list, select or enter a name (for example, "Customer").</span></span>
1. <span data-ttu-id="d77a0-143">Nell'elenco a discesa **Valuta**, selezionare o inserire una valuta (ad esempio, "USD").</span><span class="sxs-lookup"><span data-stu-id="d77a0-143">In the **Currency** drop-down list, select or enter a currency (for example, "USD").</span></span>
1. <span data-ttu-id="d77a0-144">Nell'elenco a discesa **Valuta**, selezionare il gruppo di clienti creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d77a0-144">In the **Currency** drop-down list, select the customer group created previously.</span></span>
1. <span data-ttu-id="d77a0-145">Nell'elenco a discesa **Rubriche**, selezionare una rubrica clienti esistente.</span><span class="sxs-lookup"><span data-stu-id="d77a0-145">In the **Address books**  drop-down list, select an existing customer address book.</span></span>
1. <span data-ttu-id="d77a0-146">Selezionare **Salva** per salvare e tornare alla schermata dei dettagli cliente per il nuovo cliente.</span><span class="sxs-lookup"><span data-stu-id="d77a0-146">Select **Save** to save and return to customer details screen for the new customer.</span></span>

> [!NOTE]
> <span data-ttu-id="d77a0-147">Non è necessario aggiungere un indirizzo per un cliente predefinito.</span><span class="sxs-lookup"><span data-stu-id="d77a0-147">It is not necessary to add an address for a default customer.</span></span>

<span data-ttu-id="d77a0-148">L'immagine seguente illustra un esempio di creazione di un cliente.</span><span class="sxs-lookup"><span data-stu-id="d77a0-148">The following image shows an example of customer creation.</span></span>

![Creazione di un cliente predefinito](media/default-customer-creation.png)

<span data-ttu-id="d77a0-150">L'immagine seguente mostra la configurazione di un cliente predefinito.</span><span class="sxs-lookup"><span data-stu-id="d77a0-150">The following image shows a default customer configuration.</span></span>

![Esporta di configurazione di un cliente](media/default-customer-configuration1.png)

<span data-ttu-id="d77a0-152">La maggior parte dei valori predefiniti nella schermata dei dettagli cliente può rimanere, ma è necessario modificare due valori.</span><span class="sxs-lookup"><span data-stu-id="d77a0-152">Most of the default values on the customer detials screen can remain, but two values should be changed.</span></span>

1. <span data-ttu-id="d77a0-153">Nella schermata dei dettagli cliente, espandere **Impostazioni predefinite ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="d77a0-153">On the customer details screen, expand **Sales order defaults**.</span></span>
1. <span data-ttu-id="d77a0-154">Nell'elenco a discesa **Sito**, selezionare o inserire un sito preconfigurato.</span><span class="sxs-lookup"><span data-stu-id="d77a0-154">In the **Site** drop-down list, select or enter a pre-configured site.</span></span>
1. <span data-ttu-id="d77a0-155">Nell'elenco a discesa **Magazzino**, selezionare o inserire un magazzino preconfigurato.</span><span class="sxs-lookup"><span data-stu-id="d77a0-155">In the **Warehouse** drop-down list, and select or enter a pre-configured warehouse.</span></span>

<span data-ttu-id="d77a0-156">L'immagine seguente illustra un esempio di configurazione di un cliente.</span><span class="sxs-lookup"><span data-stu-id="d77a0-156">The following image shows an example customer configuration.</span></span>

![Esporta di configurazione di un cliente](media/default-customer-configuration2.png)

## <a name="additional-resources"></a><span data-ttu-id="d77a0-158">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d77a0-158">Additional resources</span></span>

[<span data-ttu-id="d77a0-159">Panoramica dei canali</span><span class="sxs-lookup"><span data-stu-id="d77a0-159">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="d77a0-160">Prerequisiti di impostazione dei canali</span><span class="sxs-lookup"><span data-stu-id="d77a0-160">Channel setup prerequisites</span></span>](channels-prerequisites.md)

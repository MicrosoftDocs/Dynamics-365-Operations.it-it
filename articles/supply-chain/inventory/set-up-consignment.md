---
title: Impostare la spedizione
description: In questo argomento viene illustrato come configurare le operazioni di inventario spedizione in entrata.
author: perlynne
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirPartyTable, EcoResTrackingDimensionGroup, InventJournalName, InventJournalOwnershipChange, InventOwner, InventTableInventoryDimensionGroups, VendTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 220804
ms.assetid: 88822f78-4de5-462c-a55f-1f766c572719
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 00102f5c7a043c5ca22458a53b1445c57c61957c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209565"
---
# <a name="set-up-consignment"></a><span data-ttu-id="95ca0-103">Impostare la spedizione</span><span class="sxs-lookup"><span data-stu-id="95ca0-103">Set up consignment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="95ca0-104">In questo argomento viene illustrato come configurare le operazioni di inventario spedizione in entrata.</span><span class="sxs-lookup"><span data-stu-id="95ca0-104">This topic explains how to configure inbound consignment inventory operations.</span></span>

<span data-ttu-id="95ca0-105">L'inventario spedizione è l'inventario che appartiene a un fornitore ma immagazzinato presso il sito del cliente.</span><span class="sxs-lookup"><span data-stu-id="95ca0-105">Consignment inventory is inventory that’s owned by a vendor, but stored at your site.</span></span> <span data-ttu-id="95ca0-106">Quando si è pronti per consumare o utilizzare l'inventario, si assume la proprietà dell'inventario.</span><span class="sxs-lookup"><span data-stu-id="95ca0-106">When you’re ready to consume or use the inventory, you take over the ownership of the inventory.</span></span> <span data-ttu-id="95ca0-107">In questo argomento viene descritta l'impostazione necessaria per abilitare i processi di spedizione.</span><span class="sxs-lookup"><span data-stu-id="95ca0-107">This topic describes the setup needed to enable consignment processes.</span></span> <span data-ttu-id="95ca0-108">Per ulteriori informazioni sui processi di spedizione, vedere [Impostare la spedizione](consignment.md).</span><span class="sxs-lookup"><span data-stu-id="95ca0-108">For more information about consignment processes, see [Set up consignment](consignment.md).</span></span>

## <a name="inventory-owners"></a><span data-ttu-id="95ca0-109">Proprietari inventario</span><span class="sxs-lookup"><span data-stu-id="95ca0-109">Inventory owners</span></span>
<span data-ttu-id="95ca0-110">Per registrare l'inventario spedizione in entrata fisico, è necessario definire un proprietario fornitore.</span><span class="sxs-lookup"><span data-stu-id="95ca0-110">In order to record physical inbound consignment inventory, you need to define a vendor owner.</span></span> <span data-ttu-id="95ca0-111">Questo viene effettuato nella pagina **Proprietario inventario**.</span><span class="sxs-lookup"><span data-stu-id="95ca0-111">This is done on the **Inventory owner** page.</span></span> <span data-ttu-id="95ca0-112">Quando si seleziona un **Conto fornitore**, vengono generati i valori predefiniti per i campi **Nome** e **Proprietario**.</span><span class="sxs-lookup"><span data-stu-id="95ca0-112">When you select a **Vendor account** this generates default values for the **Name** and **Owner** fields.</span></span> <span data-ttu-id="95ca0-113">Il valore nel campo **Proprietario** sarà visibile al fornitore, pertanto è possibile modificarlo se i nomi di conto fornitore non sono facili da riconoscere per le persone esterne.</span><span class="sxs-lookup"><span data-stu-id="95ca0-113">The value in the **Owner** field will be visible to the vendor, so you might want to change it if your vendor account names aren’t easy for external people to recognize.</span></span> <span data-ttu-id="95ca0-114">È possibile modificare il campo **Proprietario**, ma solo fino al passaggio quando si salva il record **Proprietario inventario**.</span><span class="sxs-lookup"><span data-stu-id="95ca0-114">It’s possible to edit the **Owner** field, but only up to the point when you save the **Inventory owner** record.</span></span> <span data-ttu-id="95ca0-115">Il campo **Nome** viene popolato automaticamente con il nome della parte a cui il conto fornitore è associato e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="95ca0-115">The **Name** field is populated with the name of the party that the vendor account is associated with, and this cannot be changed.</span></span>

<span data-ttu-id="95ca0-116">[![inventory-owners](./media/inventory-owners.png)](./media/inventory-owners.png)</span><span class="sxs-lookup"><span data-stu-id="95ca0-116">[![inventory-owners](./media/inventory-owners.png)](./media/inventory-owners.png)</span></span>

## <a name="tracking-dimension-group"></a><span data-ttu-id="95ca0-117">Gruppo di dimensioni di tracciabilità</span><span class="sxs-lookup"><span data-stu-id="95ca0-117">Tracking dimension group</span></span>
<span data-ttu-id="95ca0-118">Gli articoli che verranno utilizzati nei processi di spedizione devono essere associati a un **Gruppo di dimensioni di tracciabilità** dove la dimensione **Proprietario** è impostata su **Attivo**.</span><span class="sxs-lookup"><span data-stu-id="95ca0-118">Items that are going to be used in consignment processes must be associated with a **Tracking dimension group** where the **Owner** dimension is set to **Active**.</span></span> <span data-ttu-id="95ca0-119">La dimensione Proprietario ha sempre le opzioni **Inventario fisico** e **Inventario finanziario** selezionate.</span><span class="sxs-lookup"><span data-stu-id="95ca0-119">The Owner dimension always has the **Physical inventory** and **Financial inventory** options selected.</span></span> <span data-ttu-id="95ca0-120">**Piano di copertura per dimensione** non è mai selezionato.</span><span class="sxs-lookup"><span data-stu-id="95ca0-120">The **Coverage plan by dimension** is never selected.</span></span>

<span data-ttu-id="95ca0-121">[![tracking-dimension-group](./media/tracking-dimension-group.png)](./media/tracking-dimension-group.png)</span><span class="sxs-lookup"><span data-stu-id="95ca0-121">[![tracking-dimension-group](./media/tracking-dimension-group.png)](./media/tracking-dimension-group.png)</span></span>

## <a name="inventory-ownership-change-journal"></a><span data-ttu-id="95ca0-122">Giornale di registrazione modifiche proprietà inventario</span><span class="sxs-lookup"><span data-stu-id="95ca0-122">Inventory ownership change journal</span></span>
<span data-ttu-id="95ca0-123">Il giornale di registrazione **Modifica proprietà inventario** viene utilizzato per registrare il trasferimento di proprietà dell'inventario di spedizione dal fornitore alla persona giuridica che lo consuma.</span><span class="sxs-lookup"><span data-stu-id="95ca0-123">The **Inventory ownership change** journal is used to record the transfer of ownership of consignment inventory from the vendor to the legal entity that’s consuming it.</span></span> <span data-ttu-id="95ca0-124">Come qualsiasi giornale di registrazione magazzino, deve essere identificatocon un nome di giornale di registrazione magazzino.</span><span class="sxs-lookup"><span data-stu-id="95ca0-124">Like any inventory journal, it must be identified with an Inventory journal name.</span></span> <span data-ttu-id="95ca0-125">Questi nomi vengono creati nella pagina **Nomi giornale di registrazione magazzino** e **Tipo di giornale di registrazione** deve essere impostato su **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="95ca0-125">These names are created on the **Inventory journal names** page, and the **Journal type** must be set to **Ownership change**.</span></span>

<span data-ttu-id="95ca0-126">[![inventory-ownership-change-journal](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)</span><span class="sxs-lookup"><span data-stu-id="95ca0-126">[![inventory-ownership-change-journal](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)</span></span>

## <a name="vendor-collaboration-in-consignment-processes"></a><span data-ttu-id="95ca0-127">Collaborazione fornitore nei processi di spedizione</span><span class="sxs-lookup"><span data-stu-id="95ca0-127">Vendor collaboration in consignment processes</span></span>
<span data-ttu-id="95ca0-128">Se i fornitori utilizzano l'interfaccia di collaborazione fornitore, possono utilizzare questa per monitorare il consumo dell'inventario nel sito.</span><span class="sxs-lookup"><span data-stu-id="95ca0-128">If your vendors are using the vendor collaboration interface, they can use this to monitor the consumption of inventory at your site.</span></span> <span data-ttu-id="95ca0-129">Per ulteriori informazioni su come impostare i fornitori per utilizzare la collaborazione fornitore, vedere [Sicurezza degli utenti del portale fornitori](../procurement/configure-security-vendor-portal-users.md).</span><span class="sxs-lookup"><span data-stu-id="95ca0-129">For more information about setting up vendors to use vendor collaboration, see [Vendor portal user security](../procurement/configure-security-vendor-portal-users.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
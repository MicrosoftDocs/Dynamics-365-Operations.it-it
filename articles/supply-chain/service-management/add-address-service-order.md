---
title: Aggiungere un indirizzo a un ordine di servizio
description: In questo argomento viene descritto come aggiungere un indirizzo cliente a un ordine di assistenza.
author: YuyuScheller
manager: AnnBe
ms.date: 05/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: e6dfa27b2101e84fbab678e781c26126cf1db898
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---

# <a name="add-an-address-to-a-service-order"></a><span data-ttu-id="5ac0d-103">Aggiungere un indirizzo a un ordine di servizio</span><span class="sxs-lookup"><span data-stu-id="5ac0d-103">Add an address to a service order</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="5ac0d-104">In questo argomento viene descritto come aggiungere un indirizzo cliente a un ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="5ac0d-104">This topic describes how to add a customer address to a service order.</span></span> <span data-ttu-id="5ac0d-105">Quando si crea un ordine di assistenza, in esso vengono trasferite le informazioni relative all'indirizzo dal progetto a cui l'ordine di assistenza è collegato.</span><span class="sxs-lookup"><span data-stu-id="5ac0d-105">When you create a service order, the address information is transferred from the project that the service order is attached to.</span></span> <span data-ttu-id="5ac0d-106">È tuttavia possibile selezionare un'ubicazione alternativa dagli indirizzi già immessi in Microsoft Dynamics AX per i clienti, i fornitori, i siti, i magazzini, gli ordini di assistenza e i progetti.</span><span class="sxs-lookup"><span data-stu-id="5ac0d-106">However, you can select an alternative location from addresses that are already entered in Microsoft Dynamics AX for customers, vendors, sites, warehouses, service orders, and projects.</span></span>

<span data-ttu-id="5ac0d-107">È inoltre possibile creare un nuovo indirizzo.</span><span class="sxs-lookup"><span data-stu-id="5ac0d-107">You can also create a new address.</span></span> <span data-ttu-id="5ac0d-108">Per impostazione predefinita, il nuovo indirizzo viene trasferito al progetto.</span><span class="sxs-lookup"><span data-stu-id="5ac0d-108">By default, the new address is transferred to the project.</span></span> <span data-ttu-id="5ac0d-109">È tuttavia possibile specificare che il nuovo indirizzo è solo importante per questa istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="5ac0d-109">However, you can specify that the new address is only relevant for this instance of the service.</span></span> <span data-ttu-id="5ac0d-110">In questo caso, il nuovo indirizzo non viene trasferito al progetto.</span><span class="sxs-lookup"><span data-stu-id="5ac0d-110">If you do, the new address is not transferred to the project.</span></span>

## <a name="create-a-customer-address-for-a-service-order"></a><span data-ttu-id="5ac0d-111">Creare un indirizzo cliente per un ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="5ac0d-111">Create a customer address for a service order</span></span>

<span data-ttu-id="5ac0d-112">Per aggiungere un indirizzo a un ordine di assistenza, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ac0d-112">To add an address to a service order, follow these steps:</span></span>

1.  <span data-ttu-id="5ac0d-113">Fare clic su **Gestione assistenza** \> **Comune** \> **Ordini di assistenza** \> **Ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="5ac0d-113">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="5ac0d-114">Aprire l'ordine di assistenza per cui si desidera creare un indirizzo.</span><span class="sxs-lookup"><span data-stu-id="5ac0d-114">Open the service order that you want to create an address for.</span></span>

3.  <span data-ttu-id="5ac0d-115">Nel **riquadro azioni** fare clic su **Modifica**, quindi fare clic su **Visualizzazione intestazione**.</span><span class="sxs-lookup"><span data-stu-id="5ac0d-115">On the **Action Pane**, click **Edit**, and then click **Header view**.</span></span>

4.  <span data-ttu-id="5ac0d-116">Nella Scheda dettaglio **Indirizzo** fare clic su **Aggiungi indirizzo**.</span><span class="sxs-lookup"><span data-stu-id="5ac0d-116">On the **Address** FastTab, click **Add address**.</span></span>

5.  <span data-ttu-id="5ac0d-117">Nel modulo **Nuovo indirizzo**, immettere un nome univoco per l'indirizzo e completare i campi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="5ac0d-117">In the **New address** form, enter a unique name for the address and complete the remaining fields.</span></span> 
    

    > [!WARNING]
    > <P><span data-ttu-id="5ac0d-118">Se si immette lo stesso nome dell'indirizzo esistente, le informazioni immesse nei campi rimanenti sovrascriveranno le informazioni relative all'indirizzo esistente.</span><span class="sxs-lookup"><span data-stu-id="5ac0d-118">If you enter the same name as an existing address, the information that you enter in the remaining fields will overwrite information for the existing address.</span></span></P>


6.  <span data-ttu-id="5ac0d-119">Fare clic su **OK** per copiare il nuovo indirizzo nell'ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="5ac0d-119">Click **OK** to copy the new address to your service order.</span></span>

## <a name="specify-an-alternative-address-on-a-service-order"></a><span data-ttu-id="5ac0d-120">Specificare un indirizzo alternativo nell'ordine di assistenza</span><span class="sxs-lookup"><span data-stu-id="5ac0d-120">Specify an alternative address on a service order</span></span>

<span data-ttu-id="5ac0d-121">Per aggiungere un indirizzo alternativo a un ordine di assistenza, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ac0d-121">To add an alternative address to a service order, follow these steps:</span></span>

1.  <span data-ttu-id="5ac0d-122">Fare clic su **Gestione assistenza** \> **Comune** \> **Ordini di assistenza** \> **Ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="5ac0d-122">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="5ac0d-123">Aprire l'ordine di assistenza per cui si desidera inserire un indirizzo alternativo.</span><span class="sxs-lookup"><span data-stu-id="5ac0d-123">Open the service order that you want to enter an alternative address for.</span></span>

3.  <span data-ttu-id="5ac0d-124">Nel **riquadro azioni** fare clic su **Modifica**, quindi fare clic su **Visualizzazione intestazione**.</span><span class="sxs-lookup"><span data-stu-id="5ac0d-124">On the **Action Pane**, click **Edit**, and then click **Header view**.</span></span>

4.  <span data-ttu-id="5ac0d-125">Nella Scheda dettaglio **Indirizzo** fare clic su **Altro indirizzo**.</span><span class="sxs-lookup"><span data-stu-id="5ac0d-125">On the **Address** FastTab, click **Other address**.</span></span>

5.  <span data-ttu-id="5ac0d-126">Nel modulo **Selezione indirizzo**, nel campo **Tipo di record**, selezionare **Ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="5ac0d-126">In the **Address selection** form, in the **Record type** field, select **Service orders**.</span></span>

6.  <span data-ttu-id="5ac0d-127">Selezionare un indirizzo, quindi fare clic su **OK** per copiarlo nell'ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="5ac0d-127">Select an address, and then click **OK** to copy it to your service order.</span></span>


  




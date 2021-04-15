---
title: Creare cespiti in base agli ordini fornitore
description: In questo argomento viene descritto come è possibile creare un elenco degli articoli cespite che è possibile utilizzare come base per creare i cespiti per i processi di gestione in Gestione cespiti.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectItem, EntAssetPendingAssets
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 51896f512a00bd41617fd02c2cd364c4e00eb774
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811160"
---
# <a name="create-assets-based-on-purchase-orders"></a><span data-ttu-id="7c634-103">Creare cespiti in base agli ordini fornitore</span><span class="sxs-lookup"><span data-stu-id="7c634-103">Create assets based on purchase orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="7c634-104">In questo argomento viene descritto come è possibile creare un elenco degli articoli cespite che è possibile utilizzare come base per creare i cespiti per i processi di gestione in Gestione cespiti.</span><span class="sxs-lookup"><span data-stu-id="7c634-104">This topic explains how you can create a list of asset items that can be used as a basis for creating assets for maintenance jobs in Asset Management.</span></span> <span data-ttu-id="7c634-105">A seconda degli articoli cespite, è possibile visualizzare un elenco di righe ordine fornitore create per tali articoli.</span><span class="sxs-lookup"><span data-stu-id="7c634-105">Based on the asset items, you are able to view a list of the purchase order lines that have been created on those items.</span></span> <span data-ttu-id="7c634-106">Lo scopo di questa funzionalità è creare facilmente un cespite in Gestione cespiti in base a un ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="7c634-106">The purpose of this functionality is to easily create an asset in Asset Management based on a purchase order.</span></span>

<span data-ttu-id="7c634-107">Innanzitutto, vengono impostati gli articoli da utilizzare per creare i cespiti da un ordine fornitore in **Articoli cespite**.</span><span class="sxs-lookup"><span data-stu-id="7c634-107">First, you set up the items to be used for creating assets from a purchase order in **Asset items**.</span></span> <span data-ttu-id="7c634-108">Dopo la creazione di una riga ordine fornitore, creare i cespiti in **Cespiti in sospeso**.</span><span class="sxs-lookup"><span data-stu-id="7c634-108">After creating a purchase order line, you create the assets in **Pending assets**.</span></span> <span data-ttu-id="7c634-109">È possibile decidere a quale fase dell'ordine fornitore il cespite deve essere creata.</span><span class="sxs-lookup"><span data-stu-id="7c634-109">It is possible to decide at which stage of the purchase order the asset should be created.</span></span>


## <a name="select-asset-items"></a><span data-ttu-id="7c634-110">Selezionare articoli cespite</span><span class="sxs-lookup"><span data-stu-id="7c634-110">Select asset items</span></span>

1. <span data-ttu-id="7c634-111">Fare clic **Gestione cespiti** > **Impostazione** > **Cespiti** > **Articoli**.</span><span class="sxs-lookup"><span data-stu-id="7c634-111">Click **Asset management** > **Setup** > **Assets** > **Items**.</span></span>
2. <span data-ttu-id="7c634-112">Fare clic su **Nuovo** per creare un nuovo articolo cespite.</span><span class="sxs-lookup"><span data-stu-id="7c634-112">Click **New** to create a new asset item.</span></span>
3. <span data-ttu-id="7c634-113">Nel campo **Numero articolo**, selezionare l'articolo.</span><span class="sxs-lookup"><span data-stu-id="7c634-113">Select the item in the **Item number** field.</span></span> <span data-ttu-id="7c634-114">Quando si lascia il campo, il nome dell'articolo viene automaticamente inserito nel campo **Nome prodotto**.</span><span class="sxs-lookup"><span data-stu-id="7c634-114">When you leave that field, the item name is automatically inserted in the **Product name** field.</span></span>
4. <span data-ttu-id="7c634-115">Nella Scheda dettaglio **Generale**, selezionare un tipo di cespite per l'articolo.</span><span class="sxs-lookup"><span data-stu-id="7c634-115">On the **General** FastTab, select an asset type for the item.</span></span>
5. <span data-ttu-id="7c634-116">Selezionare il produttore e il modello del cespite per l'articolo.</span><span class="sxs-lookup"><span data-stu-id="7c634-116">Select asset manufacturer and model for the item.</span></span>
6. <span data-ttu-id="7c634-117">Salvare l'articolo.</span><span class="sxs-lookup"><span data-stu-id="7c634-117">Save the item.</span></span>


## <a name="create-assets-from-pending-assets"></a><span data-ttu-id="7c634-118">Creare cespiti dai cespiti in sospeso</span><span class="sxs-lookup"><span data-stu-id="7c634-118">Create assets from pending assets</span></span>

1. <span data-ttu-id="7c634-119">Selezionare **Gestione cespiti** > **Comune** > **Cespiti** > **Cespiti in sospeso**.</span><span class="sxs-lookup"><span data-stu-id="7c634-119">Click **Asset management** > **Common** > **Assets** > **Pending Assets**.</span></span>
2. <span data-ttu-id="7c634-120">Vedrete un elenco aggiornato di ordini fornitore in base agli articoli selezionati **Elementi cespite**.</span><span class="sxs-lookup"><span data-stu-id="7c634-120">You will see an updated list of the purchase orders based on the items selected in **Asset items**.</span></span>
3. <span data-ttu-id="7c634-121">È possibile filtrare lo stato degli ordini fornitore per selezionare a quale stato del ciclo di vita il cespite deve essere creato.</span><span class="sxs-lookup"><span data-stu-id="7c634-121">You can filter the status of purchase orders to select at which lifecycle state the asset should be created.</span></span> <span data-ttu-id="7c634-122">Per esempio, è possibile creare cespiti solo quando un'entrata prodotti è stata registrata in un ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="7c634-122">For example, you may only want to create assets when a product receipt has been posted on a purchase order.</span></span>
4. <span data-ttu-id="7c634-123">Selezionare il collegamento **Numero di riferimento** in una riga ordine fornitore per visualizzare informazioni dettagliate sull'articolo.</span><span class="sxs-lookup"><span data-stu-id="7c634-123">Select the **Reference number** link on a purchase order line to view detailed information about the item.</span></span>
5. <span data-ttu-id="7c634-124">Per modificare le dimensioni visualizzate nella Scheda dettaglio **Dimensioni inventariali**, fare clic sul pulsante **Visualizza dimensioni** e selezionare le opzioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="7c634-124">If you want to edit which dimensions are displayed on the **Inventory dimensions** FastTab, click the **Display Dimensions** button, and make your selections.</span></span>
6. <span data-ttu-id="7c634-125">Se si desidera creare un cespite in base a una riga di ordine fornitore, selezionare la casella di controllo nella colonna **Contrassegna** per la riga nella pagina elenco e fare clic su **Crea cespiti**.</span><span class="sxs-lookup"><span data-stu-id="7c634-125">If you want to create an asset based on a purchase order line, select the check box in the **Mark** column for that line on the list page, and click **Create assets**.</span></span> <span data-ttu-id="7c634-126">Verrà visualizzato un messaggio in cui viene comunicato l'ID del cespite.</span><span class="sxs-lookup"><span data-stu-id="7c634-126">A message will be displayed informing you of the asset ID.</span></span>
7. <span data-ttu-id="7c634-127">Selezionare il cespite nell'elenco **Tutti i cespiti** e fare clic sul pulsante **Modifica** per aggiungere ulteriori informazioni sul cespite.</span><span class="sxs-lookup"><span data-stu-id="7c634-127">Select the asset in the **All assets** list and click **Edit** to add more information to the asset.</span></span>
8. <span data-ttu-id="7c634-128">In **Cespiti in sospeso**, se si desidera eliminare una riga poiché non si desidera creare un cespite, selezionare la casella di controllo nella colonna **Contrassegna** per la riga e clic su **Elimina cespiti in sospeso**.</span><span class="sxs-lookup"><span data-stu-id="7c634-128">In **Pending assets**, if you want to delete a line because you don't want to create an asset, select the check box in the **Mark** column for that line, and click **Discard pending assets**.</span></span> <span data-ttu-id="7c634-129">Verrà visualizzato un messaggio in cui viene comunicato l'ID del cespite.</span><span class="sxs-lookup"><span data-stu-id="7c634-129">A message will be displayed informing you of the asset ID.</span></span> <span data-ttu-id="7c634-130">Non si stanno eliminando l'ordine fornitore o l'ordine cliente, solo il record da cui è possibile creare un cespite in **Gestione cespiti**.</span><span class="sxs-lookup"><span data-stu-id="7c634-130">You are not deleting the purchase order or sales order, just the record from which you could have created an asset in **Asset Management**.</span></span>

>[!NOTE]
><span data-ttu-id="7c634-131">Tutte le dimensioni prodotto (dimensione, colore, configurazione e così via.) verranno trasferite automaticamente agli attributi del cespite.</span><span class="sxs-lookup"><span data-stu-id="7c634-131">All product dimensions (size, color, configuration etc.) are automatically transferred to the asset attributes.</span></span> <span data-ttu-id="7c634-132">Le dimensioni di tracciabilità (numero di serie) sono archiviate direttamente nel cespite quando il cespite è creato.</span><span class="sxs-lookup"><span data-stu-id="7c634-132">Tracking dimensions (serial number) are stored directly on the asset when the asset is created.</span></span>


## <a name="find-pending-assets"></a><span data-ttu-id="7c634-133">Trovare cespiti in sospeso</span><span class="sxs-lookup"><span data-stu-id="7c634-133">Find pending assets</span></span>

<span data-ttu-id="7c634-134">È possibile eseguire un **Conteggio cespiti in sospeso** per verificare i cespiti in sospeso.</span><span class="sxs-lookup"><span data-stu-id="7c634-134">You can run a **Pending asset count** to check for pending assets.</span></span> <span data-ttu-id="7c634-135">Ad esempio, questa funzione può essere utilizzata per la ricezione di una notifica ogni volta che un cespite in sospeso è pronto per essere creato come cespite.</span><span class="sxs-lookup"><span data-stu-id="7c634-135">For example, this function can be used for receiving a notification each time a pending asset is ready to be created as an asset.</span></span>

1. <span data-ttu-id="7c634-136">Selezionare **Gestione cespiti** > **Periodico** > **Cespiti** > **Conteggio cespiti in sospeso**.</span><span class="sxs-lookup"><span data-stu-id="7c634-136">Click **Asset management** > **Periodic** > **Assets** > **Pending asset count**.</span></span>
2. <span data-ttu-id="7c634-137">Fare clic **OK** per eseguire il processo e aggiornare l'elenco **Cespiti in sospeso**.</span><span class="sxs-lookup"><span data-stu-id="7c634-137">Click **OK** to run the job and update the list in **Pending assets**.</span></span>
3. <span data-ttu-id="7c634-138">È possibile impostare il processo per l'esecuzione come processo batch, ad esempio, una volta ogni giorno.</span><span class="sxs-lookup"><span data-stu-id="7c634-138">You can set up this job to run as a batch job, for example, once each day.</span></span>

<span data-ttu-id="7c634-139">**Attenzione:** Se i dati vengono modificati in un ordine fornitore *dopo* aver creato un cespite in base all'articolo pertinente, le modifiche non verranno riflesse nel cespite.</span><span class="sxs-lookup"><span data-stu-id="7c634-139">**Caution:** If data is changed on a purchase order *after* you have created an asset based on the appertaining item, those changes will not be reflected on the asset.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
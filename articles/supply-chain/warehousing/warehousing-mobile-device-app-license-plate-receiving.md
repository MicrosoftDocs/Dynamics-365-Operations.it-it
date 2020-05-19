---
title: Ricezione della targa tramite l'app del magazzino
description: Questo argomento spiega come configurare l'app del magazzino per supportare l'utilizzo di un processo di ricezione della targa per ricevere l'inventario fisico.
author: perlynne
manager: tfehr
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-03-31
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 7d5ac6598ab80ece0164d7c92f5d84e91d21b385
ms.sourcegitcommit: ffd845d4230646499b6f074cb43e69ab95787671
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "3346378"
---
# <a name="license-plate-receiving-via-the-warehousing-app"></a><span data-ttu-id="b7f1a-103">Ricezione della targa tramite l'app del magazzino</span><span class="sxs-lookup"><span data-stu-id="b7f1a-103">License plate receiving via the warehousing app</span></span>

<span data-ttu-id="b7f1a-104">Questo argomento spiega come configurare l'app del magazzino in modo che supporti l'utilizzo di un processo di ricezione della targa per ricevere l'inventario fisico.</span><span class="sxs-lookup"><span data-stu-id="b7f1a-104">This topic explains how to set up the warehousing app so that it supports using a license plate receiving process to receive physical inventory.</span></span>

<span data-ttu-id="b7f1a-105">È possibile utilizzare questa funzionalità per registrare rapidamente l'entrata di inventario in entrata correlata a un avviso di spedizione anticipata (ASN).</span><span class="sxs-lookup"><span data-stu-id="b7f1a-105">You can use this functionality to quickly record the receipt of inbound inventory that is related to an advance ship notice (ASN).</span></span> <span data-ttu-id="b7f1a-106">Il sistema crea automaticamente un ASN quando i processi di gestione del magazzino vengono utilizzati per spedire un ordine di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="b7f1a-106">The system automatically creates an ASN when warehouse management processes are used to ship a transfer order.</span></span> <span data-ttu-id="b7f1a-107">Per il processo dell'ordine fornitore, un ASN può essere registrato manualmente oppure può essere importato automaticamente utilizzando un processo dell'entità dati ASN in entrata.</span><span class="sxs-lookup"><span data-stu-id="b7f1a-107">For the purchase order process, an ASN can be manually recorded, or it can be automatically imported by using an inbound ASN data entity process.</span></span>

<span data-ttu-id="b7f1a-108">I dati ASN sono collegati a carichi e spedizioni tramite le *strutture di imballaggio*, dove i pallet (targhe padre) possono contenere casi (targhe nidificate).</span><span class="sxs-lookup"><span data-stu-id="b7f1a-108">The ASN data is linked to loads and shipments via the *packing structures*, where pallets (parent license plates) can contain cases (nested license plates).</span></span>

> [!NOTE]
> <span data-ttu-id="b7f1a-109">Per ridurre il numero di transazioni di inventario quando vengono utilizzate strutture di imballaggio con targhe nidificate, il sistema registra l'inventario fisico disponibile sulla targa padre.</span><span class="sxs-lookup"><span data-stu-id="b7f1a-109">To reduce the number of inventory transactions when packing structures that have nested license plates are used, the system records the physical on-hand inventory on the parent license plate.</span></span> <span data-ttu-id="b7f1a-110">Per attivare il movimento dell'inventario fisico disponibile dalla targa padre alle targhe nidificate, in base ai dati della struttura dell'imballaggio, il dispositivo mobile deve fornire una voce di menu basata sul processo di creazione del lavoro *Imballa in targhe nidificate*.</span><span class="sxs-lookup"><span data-stu-id="b7f1a-110">To trigger the movement of the physical on-hand inventory from the parent license plate to the nested license plates, based on the packing structure data, the mobile device must provide a menu item that is based on the *Pack to nested license plates* work creation process.</span></span>

<!-- To be used later (will require further editing):
## Warehousing mobile device app processing

When a worker scans an incoming license plate ID, the system initializes a license plate receiving process. Based on this information, the content of the license plate (data coming from the ASN) gets physically registered at the inbound dock location. The flows that follow will depend your business process needs.

## Work policies

As with (for example) the *Report as finished* mobile device menu item process, the license plate receiving process supports several workflows based on the defined setup.

### Work policies with work creation

Registration of physical on-hand where either the same warehouse worker immediately process a put-away work process following the inbound receiving (License plate receiving and put away) or where the registration and put away process gets handled as two different warehouse operations (License plate receiving) following the processing of the put-away work by using the existing work process via another mobile device menu item.

## Work policies without work creation

You can use the license plate receiving process without creating work by using the *License plate receiving without creating work* feature.

By defining **Work policies** with a **Work order type** of *Transfer receipt* and/or *Purchase orders*, and using the **Process** for **License plate receiving (and put away)**, the two Warehousing app process:

- License plate receiving
- License plate receiving and put away

will not create work, but only register the inbound physical inventory on the license plate at the inbound receiving dock.

For more information about the *Report as finished* production scenario, see the [Warehouse work policies overview](warehouse-work-policies.md).

-->

## <a name="show-or-skip-the-receiving-summary-page"></a><span data-ttu-id="b7f1a-111">Visualizzare o ignorare la pagina di riepilogo di ricezione</span><span class="sxs-lookup"><span data-stu-id="b7f1a-111">Show or skip the receiving summary page</span></span>

<span data-ttu-id="b7f1a-112">È possibile utilizzare la funzionalità *Controlla se visualizzare una pagina di riepilogo di ricezione su dispositivi mobili* per sfruttare un ulteriore flusso dettagliato dell'app di magazzino come parte del processo di ricezione della targa.</span><span class="sxs-lookup"><span data-stu-id="b7f1a-112">You can use the *Control whether to display a receiving summary page on mobile devices* feature to take advantage of an additional detailed warehousing app flow as part of the license plate receiving process.</span></span>

<span data-ttu-id="b7f1a-113">Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema.</span><span class="sxs-lookup"><span data-stu-id="b7f1a-113">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="b7f1a-114">Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla.</span><span class="sxs-lookup"><span data-stu-id="b7f1a-114">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="b7f1a-115">Nell'area di lavoro **Gestione funzionalità**, questa funzione è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="b7f1a-115">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="b7f1a-116">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="b7f1a-116">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="b7f1a-117">**Nome della funzione:** *Controlla se visualizzare una pagina di riepilogo di ricezione su dispositivi mobili*</span><span class="sxs-lookup"><span data-stu-id="b7f1a-117">**Feature name:** *Control whether to display a receiving summary page on mobile devices*</span></span>

<span data-ttu-id="b7f1a-118">Quando questa funzione è attivata, le voci di menu del dispositivo mobile per la ricezione della targa o la ricezione e la memorizzazione della targa forniranno l'impostazione **Visualizza la pagina di riepilogo di ricezione**.</span><span class="sxs-lookup"><span data-stu-id="b7f1a-118">When this feature is turned on, mobile device menu items for license plate receiving or license plate receiving and put-away will provide a **Display receiving summary page** setting.</span></span> <span data-ttu-id="b7f1a-119">Questa impostazione ha le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="b7f1a-119">This setting has the following options:</span></span>

- <span data-ttu-id="b7f1a-120">**Visualizza un riepilogo dettagliato** - Durante la ricezione della targa, i lavoratori vedranno una pagina aggiuntiva che mostra le informazioni ASN complete.</span><span class="sxs-lookup"><span data-stu-id="b7f1a-120">**Display a detailed summary** – During license plate receiving, workers will see an extra page that shows the full ASN information.</span></span>
- <span data-ttu-id="b7f1a-121">**Ignora il riepilogo** - I lavoratori non vedranno le informazioni ASN complete.</span><span class="sxs-lookup"><span data-stu-id="b7f1a-121">**Skip the summary** – Workers won't see the full ASN information.</span></span> <span data-ttu-id="b7f1a-122">Inoltre, gli addetti al magazzino non saranno in grado di impostare un codice smaltimento o aggiungere eccezioni durante il processo di ricezione.</span><span class="sxs-lookup"><span data-stu-id="b7f1a-122">Warehouse workers also won't be able to set a disposition code or add exceptions during the receiving process.</span></span>

## <a name="prevent-transfer-ordershipped-license-plates-from-being-used-at-warehouses-other-than-the-destination-warehouse"></a><span data-ttu-id="b7f1a-123">Impedire che le targhe spedite dall'ordine di trasferimento vengano utilizzate in magazzini diversi dal magazzino di destinazione</span><span class="sxs-lookup"><span data-stu-id="b7f1a-123">Prevent transfer order–shipped license plates from being used at warehouses other than the destination warehouse</span></span>

<span data-ttu-id="b7f1a-124">Un processo di ricezione della targa non può essere utilizzato se un ASN contiene un ID targa già esistente e ha dati fisici disponibili in una posizione del magazzino diversa dalla posizione del magazzino in cui si sta verificando la registrazione della targa.</span><span class="sxs-lookup"><span data-stu-id="b7f1a-124">A license plate receiving process can't be used if an ASN contains a license plate ID that already exists and has physical on-hand data at a warehouse location other than the warehouse location where the license plate registration is occurring.</span></span>

<span data-ttu-id="b7f1a-125">Per gli scenari di ordine di trasferimento in cui il magazzino di transito non tiene traccia delle targhe (e quindi non tiene traccia dell'inventario fisico disponibile per targa), è possibile utilizzare la funzione *Impedisci che le targhe spedite dall'ordine di trasferimento vengano utilizzate su altri magazzini diversi dal magazzino di destinazione* per impedire aggiornamenti fisici disponibili delle targhe in transito.</span><span class="sxs-lookup"><span data-stu-id="b7f1a-125">For transfer order scenarios where the transit warehouse doesn't track license plates (and therefore also doesn't track physical on-hand inventory per license plate), you can use the *Prevent transfer order shipped license plates from being used on other warehouses than the destination warehouse* feature to prevent physical on-hand updates of license plates that are in transit.</span></span>

<span data-ttu-id="b7f1a-126">Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema.</span><span class="sxs-lookup"><span data-stu-id="b7f1a-126">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="b7f1a-127">Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla.</span><span class="sxs-lookup"><span data-stu-id="b7f1a-127">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="b7f1a-128">Nell'area di lavoro **Gestione funzionalità**, questa funzione è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="b7f1a-128">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="b7f1a-129">**Modulo:** *Gestione magazzino*</span><span class="sxs-lookup"><span data-stu-id="b7f1a-129">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="b7f1a-130">**Nome della funzione:** *Impedisci che le targhe spedite dall'ordine di trasferimento vengano utilizzate su altri magazzini diversi dal magazzino di destinazione*</span><span class="sxs-lookup"><span data-stu-id="b7f1a-130">**Feature name:** *Prevent transfer order shipped license plates from being used on other warehouses than the destination warehouse*</span></span>

<span data-ttu-id="b7f1a-131">Per gestire la funzionalità quando questa funzione è disponibile, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="b7f1a-131">To manage the functionality when this feature is available, follow these steps.</span></span>

1. <span data-ttu-id="b7f1a-132">Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino**.</span><span class="sxs-lookup"><span data-stu-id="b7f1a-132">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="b7f1a-133">Nella scheda **Generale**, nella scheda dettaglio **Targhe**, impostare il campo **Criteri targa del magazzino in transito** su uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b7f1a-133">On the **General** tab, on the **License plates** FastTab, set the **Transit warehouse license plate policy** field to one of the following values:</span></span>

    - <span data-ttu-id="b7f1a-134">**Consenti il riutilizzo di una targa non tracciata** – Il sistema funziona come quando la funzione *Impedisci che le targhe spedite dall'ordine di trasferimento vengano utilizzate su altri magazzini diversi dal magazzino di destinazione* non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="b7f1a-134">**Allow reuse of non-tracked license plate** – The system works the same way that it works when the *Prevent transfer order shipped license plates from being used on other warehouses than the destination warehouse* feature isn't available.</span></span> <span data-ttu-id="b7f1a-135">Questo valore è l'impostazione predefinita quando si attiva per la prima volta la funzione.</span><span class="sxs-lookup"><span data-stu-id="b7f1a-135">This value is the default setting when you first activate the feature.</span></span>
    - <span data-ttu-id="b7f1a-136">**Impedisci il riutilizzo della targa non tracciata** - Solo gli aggiornamenti disponibili relativi a una targa di spedizione spedita saranno consentiti nel magazzino di destinazione fino alla ricezione dell'ordine di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="b7f1a-136">**Prevent reuse of non-tracked license plate** – Only on-hand updates that are related to a shipped license plate will be allowed at the destination warehouse until the transfer order has been received.</span></span>

## <a name="more-information"></a><span data-ttu-id="b7f1a-137">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="b7f1a-137">More information</span></span>

<!-- To read more about inbound loads, see [Link for Inbound load (Olga's doc.)] -->

<span data-ttu-id="b7f1a-138">Per ulteriori informazioni sulle voci di menu dei dispositivi mobili, vedere [Configurare i dispositivi mobili per il lavoro di magazzino](configure-mobile-devices-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="b7f1a-138">For more information about mobile device menu items, see [Set up mobile devices for warehouse work](configure-mobile-devices-warehouse.md).</span></span>

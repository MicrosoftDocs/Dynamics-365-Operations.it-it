---
title: Impostare i magazzini per gli ordini di trasferimento
description: In questo argomento viene descritto come impostare magazzini per gli ordini di trasferimento.
author: Mirzaab
manager: AnnBe
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 8111601cb2948c66097b0f5b2f261b7462b279f9
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567080"
---
# <a name="set-up-warehouses-for-transfer-orders"></a><span data-ttu-id="79d2c-103">Impostare i magazzini per gli ordini di trasferimento</span><span class="sxs-lookup"><span data-stu-id="79d2c-103">Set up warehouses for transfer orders</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="79d2c-104">Utilizzando i livelli magazzino è possibile creare una gerarchia per supportare gli ordini di trasferimento tra magazzini.</span><span class="sxs-lookup"><span data-stu-id="79d2c-104">You can use warehouse levels to create a hierarchy that supports transfer orders between warehouses.</span></span> <span data-ttu-id="79d2c-105">In base a questa impostazione, tramite la programmazione generale vengono calcolale le richieste articoli a livello di singolo magazzino e vengono generati gli ordini di trasferimento pianificati da un magazzino di origine assegnato per soddisfare tali richieste.</span><span class="sxs-lookup"><span data-stu-id="79d2c-105">Based on this setup, master scheduling calculates item requirements at the individual warehouse level and generates planned transfer orders from an assigned source warehouse to fulfill them.</span></span>

1.  <span data-ttu-id="79d2c-106">Fare clic su **Gestione inventario > Impostazioni > Suddivisione scorte > Magazzino**.</span><span class="sxs-lookup"><span data-stu-id="79d2c-106">Click **Inventory management > Setup > Inventory breakdown > Warehouses**.</span></span>

2.  <span data-ttu-id="79d2c-107">Selezionare il magazzino che si desidera ricaricare.</span><span class="sxs-lookup"><span data-stu-id="79d2c-107">Select the warehouse that you want to refill.</span></span>

3.  <span data-ttu-id="79d2c-108">Nella scheda dettaglio **Pianificazione generale**, selezionare la casella di controllo **Ricaricamento**.</span><span class="sxs-lookup"><span data-stu-id="79d2c-108">On the **Master planning** FastTab, select the **Refilling** check box.</span></span>

4.  <span data-ttu-id="79d2c-109">Nel campo **Magazzino principale** selezionare il magazzino che si desidera assegnare come magazzino di ricaricamento.</span><span class="sxs-lookup"><span data-stu-id="79d2c-109">In the **Main warehouse** field, select the warehouse that you want to assign as the refilling warehouse.</span></span> <span data-ttu-id="79d2c-110">Tramite la programmazione generale viene calcolato un fabbisogno di trasferimento per il magazzino selezionato e viene generato un ordine di trasferimento pianificato dal campo **Magazzino principale** assegnato.</span><span class="sxs-lookup"><span data-stu-id="79d2c-110">Master scheduling calculates a transfer requirement for the selected warehouse and generates a planned transfer order from the assigned **Main warehouse**.</span></span>
   
    > [!NOTE]
    > <P><span data-ttu-id="79d2c-111">Se si deseleziona la casella di controllo <STRONG>Ricaricamento</STRONG>, al magazzino selezionato verrà assegnato un livello di magazzino in relazione all'opzione selezionata in <STRONG>Magazzino principale</STRONG>, ma il <STRONG>Magazzino principale</STRONG> non viene impostato come magazzino di ricaricamento.</span><span class="sxs-lookup"><span data-stu-id="79d2c-111">If you clear the <STRONG>Refilling</STRONG> check box, the selected warehouse is assigned a warehouse level in regard to the <STRONG>Main warehouse</STRONG>, but the <STRONG>Main warehouse</STRONG> is not set up as a refilling warehouse.</span></span></P>

5.  <span data-ttu-id="79d2c-112">Chiudere la pagina per applicare la nuova impostazione.</span><span class="sxs-lookup"><span data-stu-id="79d2c-112">Close the page to apply the new setup.</span></span>


> [!TIP]
> <P><span data-ttu-id="79d2c-113">Se si desidera assegnare un magazzino per il ricaricamento, è necessario impostarlo prima come dimensione di immagazzinamento nella pagina modulo <STRONG>Gruppi di dimensioni di immagazzinamento</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="79d2c-113">If you want to assign a warehouse for refilling, you must first set up the warehouse as a storage dimension on the <STRONG>Storage dimension groups</STRONG> page.</span></span> <span data-ttu-id="79d2c-114">In questa pagina, selezionare i campi <STRONG>Attivo</STRONG> e <STRONG>Piano di copertura per dimensione</STRONG> per il magazzino.</span><span class="sxs-lookup"><span data-stu-id="79d2c-114">On this page, select the <STRONG>Active</STRONG> field and the <STRONG>Coverage plan by dimension</STRONG> field for the warehouse.</span></span></P>

## <a name="set-up-transport-lead-time"></a><span data-ttu-id="79d2c-115">Impostare il lead time di spedizione</span><span class="sxs-lookup"><span data-stu-id="79d2c-115">Set up transport lead time</span></span>

<span data-ttu-id="79d2c-116">È inoltre necessario impostare il lead time di spedizione tra magazzini nella pagina **Giorni di spedizione**.</span><span class="sxs-lookup"><span data-stu-id="79d2c-116">You must also set up the transport lead time between the warehouses on the **Transport days** page.</span></span> 
1. <span data-ttu-id="79d2c-117">Passare a **Gestione inventario > Impostazioni > Distribuzione > Giorni di spedizione**.</span><span class="sxs-lookup"><span data-stu-id="79d2c-117">Go to **Inventory management > Setup > Distribution > Transport days**.</span></span>
2. <span data-ttu-id="79d2c-118">Nel campo **Punto di ricevimento** selezionare il **magazzino**.</span><span class="sxs-lookup"><span data-stu-id="79d2c-118">In the **Receiving point** field, select **warehouse**.</span></span>
3. <span data-ttu-id="79d2c-119">Selezionare **Magazzino di spedizione**, **Magazzino ricevente** e **Giorni di spedizione**.</span><span class="sxs-lookup"><span data-stu-id="79d2c-119">Select the **Shipping warehouse**, **Receiving warehouse**, and **Transport days**.</span></span> 
4. <span data-ttu-id="79d2c-120">(Facoltativo) È inoltre possibile impostare il tempo di spedizione, a seconda della modalità di consegna, nella scheda **Giorni di spedizione per modalità di consegna**.</span><span class="sxs-lookup"><span data-stu-id="79d2c-120">(Optional) You can also set transport time, depending on the mode of delivery, under the **Transport days per mode of delivery** tab.</span></span>

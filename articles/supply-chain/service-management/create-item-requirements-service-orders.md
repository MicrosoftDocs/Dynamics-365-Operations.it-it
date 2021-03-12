---
title: Creare richieste articoli per gli ordini di assistenza
description: Se è necessario prenotare articoli specifici per un ordine di assistenza, è possibile creare le richieste articolo di magazzino.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ae44088a1b53ac5e7e9ba09ed7ff611a08d2ed0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996701"
---
# <a name="create-item-requirements-for-service-orders"></a><span data-ttu-id="f25d9-103">Creare richieste articoli per gli ordini di assistenza</span><span class="sxs-lookup"><span data-stu-id="f25d9-103">Create item requirements for service orders</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="f25d9-104">È possibile creare un ordine di assistenza per tenere traccia dei e gestire i servizi forniti ai clienti.</span><span class="sxs-lookup"><span data-stu-id="f25d9-104">You can create a service order to track and manage services that you provide to your customers.</span></span> <span data-ttu-id="f25d9-105">Se è necessario prenotare articoli specifici per un ordine di assistenza, è possibile creare le richieste articolo di magazzino.</span><span class="sxs-lookup"><span data-stu-id="f25d9-105">If you need to reserve specific items for a service order, you can create inventory item requirements for it.</span></span> <span data-ttu-id="f25d9-106">Una richiesta articolo può essere immediatamente utilizzata dal magazzino oppure può avviare un ordine di produzione per l'articolo.</span><span class="sxs-lookup"><span data-stu-id="f25d9-106">An item requirement can be immediately consumed from inventory, or it can initiate a production order for the item.</span></span>

<span data-ttu-id="f25d9-107">Le richieste articoli consentono, rispetto alle transazioni articolo, di pianificare la consegna per il momento immediatamente precedente l'utilizzo effettivo dell'articolo, di creare un ordine fornitore, di includere l'articolo all'interno di un accordo commerciale e di includere la richiesta articolo nella pianificazione della produzione.</span><span class="sxs-lookup"><span data-stu-id="f25d9-107">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span>

<span data-ttu-id="f25d9-108">Le richieste articoli per gli ordini di assistenza vengono elaborati nel corso di un progetto.</span><span class="sxs-lookup"><span data-stu-id="f25d9-108">Item requirements for service orders are processed through a project.</span></span> <span data-ttu-id="f25d9-109">Per creare una richiesta articolo in un ordine di assistenza, è necessario che l'ordine di assistenza sia assegnato a un progetto.</span><span class="sxs-lookup"><span data-stu-id="f25d9-109">To create an item requirement on a service order, the service order must be assigned to a project.</span></span> <span data-ttu-id="f25d9-110">Una volta creata una richiesta articolo per un ordine di assistenza, è possibile visualizzare la richiesta articolo nel modulo **Progetti** per il progetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="f25d9-110">After you create an item requirement for a service order, you can view the item requirement in the **Projects** form for the selected project.</span></span>

## <a name="create-an-item-requirement-for-a-service-order"></a><span data-ttu-id="f25d9-111">Creare una richiesta articoli per un ordine di assistenza</span><span class="sxs-lookup"><span data-stu-id="f25d9-111">Create an item requirement for a service order</span></span>

1.  <span data-ttu-id="f25d9-112">Fare clic su **Gestione assistenza** \> **Comune** \> **Ordini di assistenza** \> **Ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="f25d9-112">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="f25d9-113">Selezionare l'ordine di assistenza per cui si desidera creare una richiesta di articoli.</span><span class="sxs-lookup"><span data-stu-id="f25d9-113">Select the service order that you want to create an item requirement for.</span></span>

3.  <span data-ttu-id="f25d9-114">Nel **riquadro azioni** fare clic su **Richiesta articolo** nella scheda **Spedisci**.</span><span class="sxs-lookup"><span data-stu-id="f25d9-114">On the **Action Pane**, on the **Dispatch** tab, click **Item requirement**.</span></span>

4.  <span data-ttu-id="f25d9-115">Nel modulo **Richieste articoli** immettere le informazioni relative all'articolo richiesto.</span><span class="sxs-lookup"><span data-stu-id="f25d9-115">In the **Item requirements** form, enter information for the required item.</span></span> <span data-ttu-id="f25d9-116">Per ulteriori informazioni su specifici campi, consultare [Richieste articoli (modulo)](https://technet.microsoft.com/library/aa552021\(v=ax.60\)).</span><span class="sxs-lookup"><span data-stu-id="f25d9-116">For more information about the specific fields, see [Item requirements (form)](https://technet.microsoft.com/library/aa552021\(v=ax.60\)).</span></span>

## <a name="create-an-item-requirement-for-a-service-agreement"></a><span data-ttu-id="f25d9-117">Creare una richiesta di articoli per un contratto di assistenza</span><span class="sxs-lookup"><span data-stu-id="f25d9-117">Create an item requirement for a service agreement</span></span>

1.  <span data-ttu-id="f25d9-118">Fare clic su **Gestione assistenza** \> **Comune** \> **Contratti di assistenza** \> **Contratti di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="f25d9-118">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="f25d9-119">Aprire il contratto di assistenza per cui si desidera creare una richiesta di articoli.</span><span class="sxs-lookup"><span data-stu-id="f25d9-119">Open the service agreement for which you want to create an item requirement.</span></span>

3.  <span data-ttu-id="f25d9-120">Nella Scheda dettaglio **Righe** fare clic su **Aggiungi** per creare una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="f25d9-120">On the **Lines** FastTab, click **Add** to create a new line.</span></span>

4.  <span data-ttu-id="f25d9-121">Nel campo **Tipo di transazione**, selezionare **Articolo**.</span><span class="sxs-lookup"><span data-stu-id="f25d9-121">In the **Transaction type** field, select **Item**.</span></span>

5.  <span data-ttu-id="f25d9-122">Nel campo **Impostazioni articolo**, selezionare **Richiesta articolo**.</span><span class="sxs-lookup"><span data-stu-id="f25d9-122">In the **Item setup** field, select **Item requirement**.</span></span>

6.  <span data-ttu-id="f25d9-123">Nel campo **Numero articolo** selezionare l'articolo necessario per il contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="f25d9-123">In the **Item number** field, select the item that is required for the service agreement.</span></span>

7.  <span data-ttu-id="f25d9-124">Nella Scheda dettaglio **Dettagli riga**, nel campo **Sito** della scheda **Dimensioni prodotto**, selezionare il sito di magazzino per l'articolo.</span><span class="sxs-lookup"><span data-stu-id="f25d9-124">On the **Line details** FastTab, on the **Product dimensions** tab, in the **Site** field, select the inventory site for the item.</span></span>

8.  <span data-ttu-id="f25d9-125">Per creare un ordine di assistenza dalla riga contratto, nella Scheda dettaglio **Righe** fare clic su **Crea ordini di assistenza**, quindi immettere le informazioni rilevanti nel modulo **Crea ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="f25d9-125">To create a service order from the agreement line, on the **Lines** FastTab, click **Create service orders**, and then enter the relevant information in the **Create service orders** form.</span></span> 


## <a name="see-also"></a><span data-ttu-id="f25d9-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f25d9-126">See also</span></span>

<span data-ttu-id="f25d9-127">[Creare ordini di assistenza automaticamente](create-service-orders-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="f25d9-127">[Create service orders automatically](create-service-orders-automatically.md).</span></span>

  



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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 18484b637723cef43cad288c08ddfe53cddf9e03
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431272"
---
# <a name="create-item-requirements-for-service-orders"></a><span data-ttu-id="a823f-103">Creare richieste articoli per gli ordini di assistenza</span><span class="sxs-lookup"><span data-stu-id="a823f-103">Create item requirements for service orders</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="a823f-104">È possibile creare un ordine di assistenza per tenere traccia dei e gestire i servizi forniti ai clienti.</span><span class="sxs-lookup"><span data-stu-id="a823f-104">You can create a service order to track and manage services that you provide to your customers.</span></span> <span data-ttu-id="a823f-105">Se è necessario prenotare articoli specifici per un ordine di assistenza, è possibile creare le richieste articolo di magazzino.</span><span class="sxs-lookup"><span data-stu-id="a823f-105">If you need to reserve specific items for a service order, you can create inventory item requirements for it.</span></span> <span data-ttu-id="a823f-106">Una richiesta articolo può essere immediatamente utilizzata dal magazzino oppure può avviare un ordine di produzione per l'articolo.</span><span class="sxs-lookup"><span data-stu-id="a823f-106">An item requirement can be immediately consumed from inventory, or it can initiate a production order for the item.</span></span>

<span data-ttu-id="a823f-107">Le richieste articoli consentono, rispetto alle transazioni articolo, di pianificare la consegna per il momento immediatamente precedente l'utilizzo effettivo dell'articolo, di creare un ordine fornitore, di includere l'articolo all'interno di un accordo commerciale e di includere la richiesta articolo nella pianificazione della produzione.</span><span class="sxs-lookup"><span data-stu-id="a823f-107">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span>

<span data-ttu-id="a823f-108">Le richieste articoli per gli ordini di assistenza vengono elaborati nel corso di un progetto.</span><span class="sxs-lookup"><span data-stu-id="a823f-108">Item requirements for service orders are processed through a project.</span></span> <span data-ttu-id="a823f-109">Per creare una richiesta articolo in un ordine di assistenza, è necessario che l'ordine di assistenza sia assegnato a un progetto.</span><span class="sxs-lookup"><span data-stu-id="a823f-109">To create an item requirement on a service order, the service order must be assigned to a project.</span></span> <span data-ttu-id="a823f-110">Una volta creata una richiesta articolo per un ordine di assistenza, è possibile visualizzare la richiesta articolo nel modulo **Progetti** per il progetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="a823f-110">After you create an item requirement for a service order, you can view the item requirement in the **Projects** form for the selected project.</span></span>

## <a name="create-an-item-requirement-for-a-service-order"></a><span data-ttu-id="a823f-111">Creare una richiesta articoli per un ordine di assistenza</span><span class="sxs-lookup"><span data-stu-id="a823f-111">Create an item requirement for a service order</span></span>

1.  <span data-ttu-id="a823f-112">Fare clic su **Gestione assistenza** \> **Comune** \> **Ordini di assistenza** \> **Ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="a823f-112">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="a823f-113">Selezionare l'ordine di assistenza per cui si desidera creare una richiesta di articoli.</span><span class="sxs-lookup"><span data-stu-id="a823f-113">Select the service order that you want to create an item requirement for.</span></span>

3.  <span data-ttu-id="a823f-114">Nel **riquadro azioni** fare clic su **Richiesta articolo** nella scheda **Spedisci**.</span><span class="sxs-lookup"><span data-stu-id="a823f-114">On the **Action Pane**, on the **Dispatch** tab, click **Item requirement**.</span></span>

4.  <span data-ttu-id="a823f-115">Nel modulo **Richieste articoli** immettere le informazioni relative all'articolo richiesto.</span><span class="sxs-lookup"><span data-stu-id="a823f-115">In the **Item requirements** form, enter information for the required item.</span></span> <span data-ttu-id="a823f-116">Per ulteriori informazioni su specifici campi, consultare [Richieste articoli (modulo)](https://technet.microsoft.com/library/aa552021\(v=ax.60\)).</span><span class="sxs-lookup"><span data-stu-id="a823f-116">For more information about the specific fields, see [Item requirements (form)](https://technet.microsoft.com/library/aa552021\(v=ax.60\)).</span></span>

## <a name="create-an-item-requirement-for-a-service-agreement"></a><span data-ttu-id="a823f-117">Creare una richiesta di articoli per un contratto di assistenza</span><span class="sxs-lookup"><span data-stu-id="a823f-117">Create an item requirement for a service agreement</span></span>

1.  <span data-ttu-id="a823f-118">Fare clic su **Gestione assistenza** \> **Comune** \> **Contratti di assistenza** \> **Contratti di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="a823f-118">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="a823f-119">Aprire il contratto di assistenza per cui si desidera creare una richiesta di articoli.</span><span class="sxs-lookup"><span data-stu-id="a823f-119">Open the service agreement for which you want to create an item requirement.</span></span>

3.  <span data-ttu-id="a823f-120">Nella Scheda dettaglio **Righe** fare clic su **Aggiungi** per creare una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="a823f-120">On the **Lines** FastTab, click **Add** to create a new line.</span></span>

4.  <span data-ttu-id="a823f-121">Nel campo **Tipo di transazione**, selezionare **Articolo**.</span><span class="sxs-lookup"><span data-stu-id="a823f-121">In the **Transaction type** field, select **Item**.</span></span>

5.  <span data-ttu-id="a823f-122">Nel campo **Impostazioni articolo**, selezionare **Richiesta articolo**.</span><span class="sxs-lookup"><span data-stu-id="a823f-122">In the **Item setup** field, select **Item requirement**.</span></span>

6.  <span data-ttu-id="a823f-123">Nel campo **Numero articolo** selezionare l'articolo necessario per il contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="a823f-123">In the **Item number** field, select the item that is required for the service agreement.</span></span>

7.  <span data-ttu-id="a823f-124">Nella Scheda dettaglio **Dettagli riga**, nel campo **Sito** della scheda **Dimensioni prodotto**, selezionare il sito di magazzino per l'articolo.</span><span class="sxs-lookup"><span data-stu-id="a823f-124">On the **Line details** FastTab, on the **Product dimensions** tab, in the **Site** field, select the inventory site for the item.</span></span>

8.  <span data-ttu-id="a823f-125">Per creare un ordine di assistenza dalla riga contratto, nella Scheda dettaglio **Righe** fare clic su **Crea ordini di assistenza**, quindi immettere le informazioni rilevanti nel modulo **Crea ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="a823f-125">To create a service order from the agreement line, on the **Lines** FastTab, click **Create service orders**, and then enter the relevant information in the **Create service orders** form.</span></span> 


## <a name="see-also"></a><span data-ttu-id="a823f-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a823f-126">See also</span></span>

<span data-ttu-id="a823f-127">[Creare ordini di assistenza automaticamente](create-service-orders-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="a823f-127">[Create service orders automatically](create-service-orders-automatically.md).</span></span>

  



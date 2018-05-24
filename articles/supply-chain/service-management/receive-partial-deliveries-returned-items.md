---
title: Ricevere consegne parziali relative a resi
description: Le consegne parziali vengono definite in termini di righe, non in termini di spedizioni dell'ordine di reso.
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
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
ms.openlocfilehash: f9f596d31f2438a353b02bf939786b284937db86
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---

# <a name="receive-partial-deliveries-of-returned-items"></a><span data-ttu-id="9c3ce-103">Ricevere consegne parziali relative a resi</span><span class="sxs-lookup"><span data-stu-id="9c3ce-103">Receive partial deliveries of returned items</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="9c3ce-104">Le consegne parziali vengono definite in termini di righe, non in termini di spedizioni dell'ordine di reso.</span><span class="sxs-lookup"><span data-stu-id="9c3ce-104">Partial deliveries are defined in terms of return order lines, not return order shipments.</span></span>

<span data-ttu-id="9c3ce-105">Ciò significa che, se si riceve l'intera quantità indicata in una singola riga dell'ordine di reso ma non si riceve niente di quanto specificato nelle altre righe dell'ordine, la consegna non è da considerarsi parziale.</span><span class="sxs-lookup"><span data-stu-id="9c3ce-105">This means that if you receive the full quantity that is indicated on one return order line, but you receive nothing from the other lines in the return order, the delivery is not a partial delivery.</span></span> <span data-ttu-id="9c3ce-106">Se tuttavia una riga dell'ordine di reso fa riferimento ad esempio a dieci unità di un determinato articolo da restituire, ma si ricevono solo quattro unità, la consegna è parziale.</span><span class="sxs-lookup"><span data-stu-id="9c3ce-106">However, if a return order line requires 10 units of a particular item to be returned, but you receive only four, it is a partial delivery.</span></span>

<span data-ttu-id="9c3ce-107">Se una spedizione di reso contiene una quantità inferiore all'intera quantità di una riga dell'ordine di reso, è possibile accantonare la spedizione e attendere l'arrivo della quantità rimanente oppure registrare e contabilizzare la quantità parziale.</span><span class="sxs-lookup"><span data-stu-id="9c3ce-107">If a return shipment contains less than the full quantity of a return order line, you can set the shipment aside and wait for the rest of the returned quantity to arrive, or you can register and post the partial quantity.</span></span>

## <a name="register-and-post-a-partial-quantity"></a><span data-ttu-id="9c3ce-108">Registrare e contabilizzare una quantità parziale</span><span class="sxs-lookup"><span data-stu-id="9c3ce-108">Register and post a partial quantity</span></span>

1.  <span data-ttu-id="9c3ce-109">Dopo avere selezionato un ordine di reso per l'arrivo nel modulo **Panoramica arrivi - Magazzino: %1, Banchina: %2, Nome giornale di registrazione: %3**, fare clic su **Inizia arrivo** per creare il giornale di registrazione arrivi e fare clic su **Giornali di registrazione** \> **Mostra arrivi da ricevimenti** per aprire il modulo **Giornale di registrazione ubicazioni**.</span><span class="sxs-lookup"><span data-stu-id="9c3ce-109">After you select a return order for arrival on the **Arrival overview - Warehouse: %1, Dock: %2, Journal name: %3** form, click **Start arrival** to create the arrival journal, and then click **Journals** \> **Show arrivals from receipts** to open the **Location journal** form.</span></span>

2.  <span data-ttu-id="9c3ce-110">Selezionare la riga del giornale di registrazione che si desidera utilizzare, quindi fare clic su **Righe** per aprire il modulo **Righe giornale di registrazione, ubicazioni**.</span><span class="sxs-lookup"><span data-stu-id="9c3ce-110">Select the line of the journal that you want to work with, and then click **Lines** to open the **Journal lines, locations** form.</span></span>

3.  <span data-ttu-id="9c3ce-111">Selezionare la riga relativa al numero di articolo per il quale è arrivata solo una quantità parziale, quindi fare clic su **Funzioni** \> **Dividi** per aprire il modulo **Dividi**.</span><span class="sxs-lookup"><span data-stu-id="9c3ce-111">Select the line of the item number for which only a partial quantity has arrived, and then click **Functions** \> **Split** to open the **Split** form.</span></span>

4.  <span data-ttu-id="9c3ce-112">Nel campo **Dividi quantità** digitare la quantità relativa al numero totale di articoli ricevuti, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c3ce-112">In the **Split quantity** field, enter the quantity for the total number of items that have been received, and then click **OK**.</span></span>

5.  <span data-ttu-id="9c3ce-113">Nel modulo **Righe giornale di registrazione, ubicazioni** selezionare la riga relativa alla quantità di articoli arrivata, quindi fare clic su **Registra**.</span><span class="sxs-lookup"><span data-stu-id="9c3ce-113">On the **Journal lines, locations** form, select the line for the quantity of items that has arrived, and then click **Post**.</span></span> <span data-ttu-id="9c3ce-114">La riga relativa alla quantità aggiuntiva potrà essere registrata dopo l'arrivo degli articoli.</span><span class="sxs-lookup"><span data-stu-id="9c3ce-114">You can post the line for the additional quantity after the items have arrived.</span></span>






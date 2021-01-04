---
title: Aggiornamenti dei documenti di trasporto per i resi
description: Affinché i resi possano essere ricevuti nel magazzino, è necessario aggiornare il documento di trasporto relativo all'ordine a cui essi si riferiscono.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPackingSlipJournalHistory, SalesParmPackingSlipTrackingInformation
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e7f5bf5adb603d7edb40960b70cb71e25a2f0456
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431174"
---
# <a name="packing-slip-updates-for-returns"></a><span data-ttu-id="06ab5-103">Aggiornamenti dei documenti di trasporto per i resi</span><span class="sxs-lookup"><span data-stu-id="06ab5-103">Packing slip updates for returns</span></span>  

[!include [banner](../includes/banner.md)]


<span data-ttu-id="06ab5-104">Affinché i resi possano essere ricevuti nel magazzino, è necessario aggiornare il documento di trasporto relativo all'ordine a cui essi si riferiscono.</span><span class="sxs-lookup"><span data-stu-id="06ab5-104">Before returned items can be received into inventory, the packing slip for the order to which they belong must be updated.</span></span> <span data-ttu-id="06ab5-105">Come il processo di aggiornamento della fattura rappresenta l'aggiornamento per la transazione finanziaria, il processo di aggiornamento del documento di trasporto rappresenta l'aggiornamento fisico del record di magazzino. In altre parole, consente di eseguire il commit delle modifiche nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="06ab5-105">Just as the invoice update process is the update to the financial transaction, the packing slip update process is the physical update of the inventory record, which means that it commits the changes to inventory.</span></span> <span data-ttu-id="06ab5-106">Nel caso dei resi, i passaggi assegnati all'azione di smaltimento vengono implementati durante l'aggiornamento del documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="06ab5-106">In the case of returns, the steps that are assigned to the disposition action are implemented during the packing slip update.</span></span>

<span data-ttu-id="06ab5-107">L'aggiornamento del documento di trasporto può essere elaborato nel giornale di registrazione arrivi articoli o nell'ordine di reso.</span><span class="sxs-lookup"><span data-stu-id="06ab5-107">The packing slip update can be processed in either the item arrival journal or the return order.</span></span>

<span data-ttu-id="06ab5-108">Durante il processo di registrazione del documento di trasporto, è possibile associare il numero di riferimento del documento di trasporto indicato nei documenti di spedizione del cliente alle righe dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="06ab5-108">As part of the process for posting packing slips, the packing slip reference number from the customer’s shipping documents can be associated with the order lines.</span></span> <span data-ttu-id="06ab5-109">Questa associazione facoltativa serve solo a scopo di riferimento</span><span class="sxs-lookup"><span data-stu-id="06ab5-109">This association is optional and for reference only.</span></span> <span data-ttu-id="06ab5-110">e non comporta l'esecuzione di aggiornamenti transazionali.</span><span class="sxs-lookup"><span data-stu-id="06ab5-110">It does not create any transactional updates.</span></span>

<span data-ttu-id="06ab5-111">Se non sono arrivati tutti i resi previsti, includere solo la quantità ricevuta nell'aggiornamento del documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="06ab5-111">If not all of the expected return items have arrived, you should include only the quantity that has been received in the packing slip update.</span></span> <span data-ttu-id="06ab5-112">e lasciare gli articoli rimanenti nell'ordine fino a quando non arriverà la restante parte della spedizione dei resi.</span><span class="sxs-lookup"><span data-stu-id="06ab5-112">Leave the remaining items on the order until the rest of the return shipment has arrived.</span></span>

<span data-ttu-id="06ab5-113">Se un articolo viene rinviato dalla quarantena al reparto addetto alle spedizioni e ai ricevimenti, ad esempio quando l'addetto alle ispezioni della quarantena non sa dove posizionare l'articolo nel magazzino, è necessario aggiornare il documento di trasporto corrispondente per registrare correttamente il codice smaltimento specificato a causa della quarantena ed eseguire un'azione appropriata.</span><span class="sxs-lookup"><span data-stu-id="06ab5-113">If an item is sent back from quarantine to the Shipping and Receiving department, such as when the quarantine inspector does not know where to store the item in inventory, the corresponding packing slip must be updated to correctly register and act on the disposition code that is specified as a result of the quarantine.</span></span>

<span data-ttu-id="06ab5-114">Quando si aggiorna un documento di trasporto per un reso che deriva da un contratto di vendita, l'impegno del contratto di vendita per tale articolo viene aggiornato automaticamente per riflettere la modifica nella quantità o nell'importo.</span><span class="sxs-lookup"><span data-stu-id="06ab5-114">When you update a packing slip for a returned item that is from a sales agreement, the sales agreement commitment for that item is automatically updated to reflect the change in the quantity or the amount.</span></span> 

## <a name="see-also"></a><span data-ttu-id="06ab5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06ab5-115">See also</span></span>

[<span data-ttu-id="06ab5-116">Eseguire aggiornamenti di fatture per i resi</span><span class="sxs-lookup"><span data-stu-id="06ab5-116">Perform invoice updates for returns</span></span>](perform-invoice-updates-for-returns.md)

  



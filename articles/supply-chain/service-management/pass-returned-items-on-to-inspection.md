---
title: Trasferire i resi al servizio di ispezione
description: Quando si esegue la registrazione di un reso, determinare se l'articolo deve essere sottoposto a ispezione prima di essere restituito al magazzino oppure se deve essere smaltito in altro modo.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSJournalTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 04b27a5560b6126fde3028f653a89059bb765844
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254967"
---
# <a name="pass-returned-items-on-to-inspection"></a><span data-ttu-id="f16ce-103">Trasferire i resi al servizio di ispezione</span><span class="sxs-lookup"><span data-stu-id="f16ce-103">Pass returned items on to inspection</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="f16ce-104">Quando si esegue la registrazione di un reso, è possibile determinare se l'articolo deve essere sottoposto a ispezione prima di essere restituito al magazzino oppure se deve essere smaltito in altro modo.</span><span class="sxs-lookup"><span data-stu-id="f16ce-104">When registering a returned item, you may determine that an item should be sent for inspection before it is returned to inventory or disposed of in some other way.</span></span>

1.  <span data-ttu-id="f16ce-105">Fare clic su **Gestione inventario** \> **Giornali di registrazione** \> **Arrivo articoli** \> **Arrivo articoli**.</span><span class="sxs-lookup"><span data-stu-id="f16ce-105">Click **Inventory management** \> **Journals** \> **Item arrival** \> **Item arrival**.</span></span>
    
    <span data-ttu-id="f16ce-106">\-oppure</span><span class="sxs-lookup"><span data-stu-id="f16ce-106">\-or-</span></span>
    
    <span data-ttu-id="f16ce-107">Fare clic su **Gestione inventario** \> **Giornali di registrazione** \> **Arrivo articoli** \> **Entrata produzione**.</span><span class="sxs-lookup"><span data-stu-id="f16ce-107">Click **Inventory management** \> **Journals** \> **Item arrival** \> **Production input**.</span></span>

2.  <span data-ttu-id="f16ce-108">Nel modulo **Giornale di registrazione ubicazioni** registrare l'entrata di un articolo in base alla normale procedura.</span><span class="sxs-lookup"><span data-stu-id="f16ce-108">On the **Location journal** form, register the receipt of an item as usual.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="f16ce-109">Per informazioni sulla registrazione del ricevimento di resi, vedere <A href="register-the-receipt-of-returned-items.md">Registrare il ricevimento di resi</A>.</span><span class="sxs-lookup"><span data-stu-id="f16ce-109">For information about registering the receipt of returned items, see <A href="register-the-receipt-of-returned-items.md">Register the receipt of returned items</A></span></span></P>



3.  <span data-ttu-id="f16ce-110">Nella scheda **Valori predefiniti**, nell'area **Modalità di movimentazione**, selezionare la casella **Gestione quarantena**.</span><span class="sxs-lookup"><span data-stu-id="f16ce-110">On the **Default values** tab, in the **Mode of handling** area, select the **Quarantine management** box.</span></span>

<span data-ttu-id="f16ce-111">Verrà creato automaticamente un ordine di quarantena, a cui la persona o il reparto addetto alle ispezioni risponderà utilizzando il modulo **Ordine di quarantena**.</span><span class="sxs-lookup"><span data-stu-id="f16ce-111">This will prompt the system to create a quarantine order, and the person or department that performs inspections will respond to this order using the **Quarantine order** form.</span></span>

## <a name="see-also"></a><span data-ttu-id="f16ce-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f16ce-112">See also</span></span>

[<span data-ttu-id="f16ce-113">Sottoporre a ispezione i resi</span><span class="sxs-lookup"><span data-stu-id="f16ce-113">Take returned items through inspection</span></span>](take-returned-items-through-inspection.md)

[<span data-ttu-id="f16ce-114">Specificare la modalità di smaltimento dei resi</span><span class="sxs-lookup"><span data-stu-id="f16ce-114">Specify how to dispose of returned items</span></span>](specify-how-to-dispose-of-returned-items.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
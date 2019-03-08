---
title: Trasferire i resi al servizio di ispezione
description: Quando si esegue la registrazione di un reso, determinare se l'articolo deve essere sottoposto a ispezione prima di essere restituito al magazzino oppure se deve essere smaltito in altro modo.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSJournalTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 70aafb752b2c847d5d48236fd5d201a73e088c24
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "334084"
---
# <a name="pass-returned-items-on-to-inspection"></a><span data-ttu-id="b0e5e-103">Trasferire i resi al servizio di ispezione</span><span class="sxs-lookup"><span data-stu-id="b0e5e-103">Pass returned items on to inspection</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="b0e5e-104">Quando si esegue la registrazione di un reso, è possibile determinare se l'articolo deve essere sottoposto a ispezione prima di essere restituito al magazzino oppure se deve essere smaltito in altro modo.</span><span class="sxs-lookup"><span data-stu-id="b0e5e-104">When registering a returned item, you may determine that an item should be sent for inspection before it is returned to inventory or disposed of in some other way.</span></span>

1.  <span data-ttu-id="b0e5e-105">Fare clic su **Gestione inventario** \> **Giornali di registrazione** \> **Arrivo articoli** \> **Arrivo articoli**.</span><span class="sxs-lookup"><span data-stu-id="b0e5e-105">Click **Inventory management** \> **Journals** \> **Item arrival** \> **Item arrival**.</span></span>
    
    <span data-ttu-id="b0e5e-106">\-oppure</span><span class="sxs-lookup"><span data-stu-id="b0e5e-106">\-or-</span></span>
    
    <span data-ttu-id="b0e5e-107">Fare clic su **Gestione inventario** \> **Giornali di registrazione** \> **Arrivo articoli** \> **Entrata produzione**.</span><span class="sxs-lookup"><span data-stu-id="b0e5e-107">Click **Inventory management** \> **Journals** \> **Item arrival** \> **Production input**.</span></span>

2.  <span data-ttu-id="b0e5e-108">Nel modulo **Giornale di registrazione ubicazioni** registrare l'entrata di un articolo in base alla normale procedura.</span><span class="sxs-lookup"><span data-stu-id="b0e5e-108">On the **Location journal** form, register the receipt of an item as usual.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="b0e5e-109">Per informazioni sulla registrazione del ricevimento di resi, vedere <A href="register-the-receipt-of-returned-items.md">Registrare il ricevimento di resi</A>.</span><span class="sxs-lookup"><span data-stu-id="b0e5e-109">For information about registering the receipt of returned items, see <A href="register-the-receipt-of-returned-items.md">Register the receipt of returned items</A></span></span></P>



3.  <span data-ttu-id="b0e5e-110">Nella scheda **Valori predefiniti**, nell'area **Modalità di movimentazione**, selezionare la casella **Gestione quarantena**.</span><span class="sxs-lookup"><span data-stu-id="b0e5e-110">On the **Default values** tab, in the **Mode of handling** area, select the **Quarantine management** box.</span></span>

<span data-ttu-id="b0e5e-111">Verrà creato automaticamente un ordine di quarantena, a cui la persona o il reparto addetto alle ispezioni risponderà utilizzando il modulo **Ordine di quarantena**.</span><span class="sxs-lookup"><span data-stu-id="b0e5e-111">This will prompt the system to create a quarantine order, and the person or department that performs inspections will respond to this order using the **Quarantine order** form.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0e5e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0e5e-112">See also</span></span>

[<span data-ttu-id="b0e5e-113">Sottoporre a ispezione i resi</span><span class="sxs-lookup"><span data-stu-id="b0e5e-113">Take returned items through inspection</span></span>](take-returned-items-through-inspection.md)

[<span data-ttu-id="b0e5e-114">Specificare la modalità di smaltimento dei resi</span><span class="sxs-lookup"><span data-stu-id="b0e5e-114">Specify how to dispose of returned items</span></span>](specify-how-to-dispose-of-returned-items.md)


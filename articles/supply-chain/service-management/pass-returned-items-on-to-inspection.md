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
# <a name="pass-returned-items-on-to-inspection"></a>Trasferire i resi al servizio di ispezione 

[!include [banner](../includes/banner.md)]


Quando si esegue la registrazione di un reso, è possibile determinare se l'articolo deve essere sottoposto a ispezione prima di essere restituito al magazzino oppure se deve essere smaltito in altro modo.

1.  Fare clic su **Gestione inventario** \> **Giornali di registrazione** \> **Arrivo articoli** \> **Arrivo articoli**.
    
    \-oppure
    
    Fare clic su **Gestione inventario** \> **Giornali di registrazione** \> **Arrivo articoli** \> **Entrata produzione**.

2.  Nel modulo **Giornale di registrazione ubicazioni** registrare l'entrata di un articolo in base alla normale procedura.
    

    > [!NOTE]
    > <P>Per informazioni sulla registrazione del ricevimento di resi, vedere <A href="register-the-receipt-of-returned-items.md">Registrare il ricevimento di resi</A>.</P>



3.  Nella scheda **Valori predefiniti**, nell'area **Modalità di movimentazione**, selezionare la casella **Gestione quarantena**.

Verrà creato automaticamente un ordine di quarantena, a cui la persona o il reparto addetto alle ispezioni risponderà utilizzando il modulo **Ordine di quarantena**.

## <a name="see-also"></a>Vedere anche

[Sottoporre a ispezione i resi](take-returned-items-through-inspection.md)

[Specificare la modalità di smaltimento dei resi](specify-how-to-dispose-of-returned-items.md)


---
title: Creare e fatturare un ordine fornitore interaziendale per uso interno
description: In questo articolo viene illustrato come creare e fatturare un ordine fornitore interaziendale per uso interno
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchLineOpenOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 2260128c276ab7b712f7c97945b188ea42099fb4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877539"
---
# <a name="create-and-invoice-an-intercompany-purchase-order-for-internal-use"></a>Creare e fatturare un ordine fornitore interaziendale per uso interno

[!include [banner](../../includes/banner.md)]

È possibile creare un ordine fornitore interaziendale per un fornitore interaziendale. Un ordine cliente interaziendale viene automaticamente creato presso il fornitore interaziendale.

![Processo di acquisto interno interaziendale](media/intercompanypurchaseprocess.png)

## <a name="create-an-intercompany-purchase-order-and-a-corresponding-intercompany-sales-order"></a>Creare un ordine fornitore interaziendale e un ordine cliente interaziendale corrispondente

Eseguire questi passaggi per la persona giuridica AAA, come illustrato nella figura.

1. Selezionare **Contabilità fornitori** \> **Ordini fornitore** \> **Tutti gli ordini fornitore**.
1. Nella pagina elenco **Tutti gli ordini fornitore** viene creato un ordine fornitore per un fornitore interaziendale. I valori dei campi vengono copiati dal conto fornitore all'ordine fornitore.

    Poiché si sta utilizzando un fornitore interaziendale, un ordine cliente interaziendale viene creato nella persona giuridica corrispondente al fornitore. Il numero dell'ordine cliente interaziendale può corrispondere al numero dell'ordine fornitore interaziendale e può includere l'ID della persona giuridica. La struttura di numero utilizzata dipende dalla selezione effettuata nel campo **Numerazione ordine cliente** della pagina **Interaziendale**. Ad esempio, se si crea l'ordine fornitore 00029\_064 nella persona giuridica AAA, il numero di ordine cliente nella persona giuridica BBB è AAA00029\_64.

    In un messaggio informativo è indicato che sono stati creati un ordine fornitore interaziendale e un ordine cliente interaziendale Il messaggio include il numero dell'ordine cliente interaziendale, a scopo informativo.

1. Aggiungere articoli all'ordine fornitore. Le voci corrispondenti vengono aggiunte automaticamente all'ordine cliente interaziendale. Se un articolo non è presente nell'altra persona giuridica, verrà visualizzato un messaggio e non sarà possibile aggiungere l'articolo all'ordine fornitore. Per risolvere questo problema, passare all'altra persona giuridica e rilasciare il prodotto su questa. L'articolo sarà disponibile per essere aggiunto agli ordini cliente in tale persona giuridica. Quindi, passare alla persona giuridica dell'ordine fornitore e continuare ad aggiungere gli articoli.
1. Dopo aver immesso le informazioni per l'ordine fornitore, confermarlo.

## <a name="process-the-intercompany-packing-slip-and-customer-invoice"></a>Elaborare il documento di trasporto interaziendale e la fattura cliente

Eseguire questi passaggi per la persona giuridica BBB, come illustrato nella figura.

1. Andare a **Contabilità clienti \> Ordini cliente \> Tutti gli ordini cliente**.
1. Nella pagina elenco **Tutti gli ordini cliente**, selezionare l'ordine cliente interaziendale.
1. Nel riquadro Azioni, selezionare la scheda **Preleva e imballa**, quindi selezionare **Documento di trasporto**.
1. Selezionare la casella di controllo **Registrazione**.
1. Selezionare **OK**. Il documento di trasporto viene registrato nella persona giuridica BBB.
1. Nella pagina elenco **Tutti gli ordini cliente**, selezionare l'ordine cliente interaziendale.
1. Nel riquadro Azioni, selezionare la scheda **Fattura**, quindi selezionare **Fattura**.
1. Selezionare la casella di controllo **Registrazione**.
1. Selezionare **OK**.

    La fattura cliente per l'ordine cliente interaziendale viene registrata nella persona giuridica BBB.

## <a name="process-the-intercompany-product-receipt-and-vendor-invoice"></a>Elaborare l'entrata prodotti e la fattura fornitore interaziendali

Eseguire questi passaggi per la persona giuridica AAA, come illustrato nella figura.

1. Vai a **Contabilità fornitori \> Ordini fornitore \> Tutti gli ordini fornitore**.
1. Nella pagina elenco **Tutti gli ordini fornitore**, selezionare l'ordine fornitore interaziendale.
1. Nel riquadro Azioni, selezionare la scheda **Ricevi**, quindi selezionare **Entrata prodotti**. L'entrata prodotti viene creata. Il numero dell'entrata prodotti corrisponde al numero del documento di trasporto interaziendale.
1. Selezionare la casella di controllo **Registrazione**.
1. Selezionare **OK**.
1. Nella pagina elenco **Tutti gli ordini fornitore**, selezionare l'ordine fornitore interaziendale.
1. Nel riquadro Azioni selezionare **Fattura**, quindi selezionare **Fattura**. La fattura fornitore verrà creata. Il numero della fattura fornitore corrisponde al numero di fattura cliente interaziendale.
1. Completare l'immissione della fattura fornitore e quindi registrarlo.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

---
title: Creare un ordine cliente interaziendale per uso interno
description: In questo argomento viene illustrato come creare un ordine cliente interaziendale per uso interno
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 9b4d2dc450fb5996e0e08c92836c1d1942a05b73
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673692"
---
# <a name="create-an-intercompany-sales-order-for-internal-use"></a>Creare un ordine cliente interaziendale per uso interno

[!include [banner](../../includes/banner.md)]

In genere, un ordine cliente interaziendale viene creato automaticamente in base a un ordine fornitore interaziendale. È possibile anche creare manualmente un ordine cliente interaziendale, che quindi genera un ordine fornitore interaziendale nella persona giuridica del cliente interaziendale.

![Processo di vendita interna interaziendale](media/intercompanyinternalsalesprocess.png)

## <a name="create-an-intercompany-sales-order-manually"></a>Creare manualmente un ordine cliente interaziendale

Eseguire questi passaggi per la persona giuridica B, come illustrato nella figura.

1. Andare a **Contabilità clienti \> Ordini cliente \> Tutti gli ordini cliente**.
1. Sul riquadro Azioni, selezionare **Ordine cliente** per creare un ordine cliente.
1. Nella pagina **Crea ordine cliente**, selezionare un conto cliente. Assicurarsi che la casella di controllo **Interaziendale** sia selezionata nella Scheda dettaglio **Generale**. Ciò indica che il cliente selezionato è un cliente interaziendale.
1. Immettere o modificare le informazioni, selezionare **OK** e quindi completare le righe ordine nel modo abituale.

    Il valore del campo **Indirizzo di consegna** viene copiato dall'intestazione dell'ordine cliente interaziendale all'intestazione dell'ordine fornitore interaziendale. Il valore del campo **Numero articolo**, incluse le dimensioni prodotto e i valori dei campi **Data di consegna** e **Codice valuta** vengono copiati dalle righe ordine cliente interaziendale alle righe ordine fornitore interaziendale.

1. Nell'intestazione ordine, selezionare **Interaziendale** per visualizzare l'ordine fornitore interaziendale correlato.
1. Nelle righe ordine, selezionare **Interaziendale** per visualizzare le informazioni sulle scorte disponibili per il commercio interaziendale.

> [!TIP]
> È possibile visualizzare gli ordini cliente interaziendali nella pagina **Ordini interaziendali**.

> [!NOTE]
> Quando si lavora in modalità interaziendale, è consigliabile deselezionare la casella di controllo **Elimina ordine dopo la fatturazione** nella pagina **Parametri contabilità clienti**. In caso contrario, l'ordine fornitore correlato verrà eliminato. È consigliabile inoltre deselezionare la casella di controllo **Elimina ordine fornitore dopo la fatturazione** nella pagina **Parametri contabilità fornitori**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

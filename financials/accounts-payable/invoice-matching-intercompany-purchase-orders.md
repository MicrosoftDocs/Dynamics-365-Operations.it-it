---
title: Abbinamento fatture e sugli ordini fornitore interaziendali
description: "La persona giuridica acquirente coinvolta in una transazione di commercio interaziendale può essere impostata per l&quot;utilizzo dell&quot;abbinamento fatture contabilità fornitori. In questo caso, affinché vengano registrate le fatture relative agli ordini fornitore interaziendali, devono essere soddisfatti i requisiti di registrazione sia per il commercio interaziendale sia per l&quot;abbinamento fatture contabilità fornitori."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchLineMatchingPolicy
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3101
ms.assetid: 9c7c2e44-45f8-4325-b6de-a09fe790f9cf
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 07c101b886d33fa5fc9e8129230ca270f48c5217
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="invoice-matching-and-intercompany-purchase-orders"></a>Abbinamento fatture e sugli ordini fornitore interaziendali

[!include[banner](../includes/banner.md)]


La persona giuridica acquirente coinvolta in una transazione di commercio interaziendale può essere impostata per l'utilizzo dell'abbinamento fatture contabilità fornitori. In questo caso, affinché vengano registrate le fatture relative agli ordini fornitore interaziendali, devono essere soddisfatti i requisiti di registrazione sia per il commercio interaziendale sia per l'abbinamento fatture contabilità fornitori.

Negli esempi riportati in questo argomento vengono utilizzate le seguenti impostazioni per il commercio interaziendale:
-   Fabrikam Purchase è la persona giuridica acquirente.
-   Fabrikam Sales è la persona giuridica venditrice.
-   Il cliente 4020 è presente in Fabrikam Sales.
-   Il fornitore 3024 è presente in Fabrikam Purchase.
-   In Fabrikam Purchase, le informazioni interaziendali vengono specificate per il fornitore 3024. Fabrikam Sales è specificata come società cliente e il cliente 4020 è specificato come conto cliente corrispondente alla persona giuridica Fabrikam Purchase.
-   In Fabrikam Sales, le informazioni interaziendali vengono specificate per il cliente 4020. Fabrikam Purchase è specificata come società fornitore e il fornitore 3024 è specificato come conto fornitore corrispondente alla persona giuridica Fabrikam Sales.

Negli esempi vengono utilizzate la seguenti impostazioni per l'abbinamento fatture contabilità fornitori per Fabrikam Purchase:
-   Nella pagina Parametri contabilità fornitori, è selezionata l'opzione Abilita convalida abbinamento fatture.
-   Nella pagina Parametri contabilità fornitori, il campo Registra fattura con discrepanze è impostato su Richiedi approvazione.
-   La percentuale di tolleranza prezzi per la persona giuridica è pari al 2%.

## <a name="example-price-matching-and-intercompany-trade"></a>Esempio: abbinamento prezzi e commercio interaziendale
Gli importi netti per la fattura fornitore interaziendale e la fattura cliente interaziendale devono essere uguali. Tale requisito ha la priorità su qualsiasi approvazione di abbinamento fatture o percentuale di tolleranza prezzi applicabile. Ad esempio, attenersi alla procedura descritta di seguito.
1.  Creare l'ordine cliente SO888 per il cliente 4020 in Fabrikam Purchase. L'ordine fornitore interaziendale ICPO222 viene creato automaticamente per il fornitore 3024 in Fabrikam Purchase, mentre l'ordine cliente ICSO888 viene creato automaticamente in Fabrikam Sales.
2.  In Fabrikam Sales registrare la ricezione degli articoli e un documento di trasporto. Lo stato di ICSO888 diventa Consegnato. Lo stato di ICPO222 diventa Ricevuto.
3.  In Fabrikam Sales eseguire un aggiornamento della fattura per ICSO888. Il prezzo unitario è 0,45 e vengono aggiornati 100 articoli.
4.  In Fabrikam Purchase creare una fattura per ICPO222. Il prezzo netto viene modificato accidentalmente da 45,00 a 54,00. Viene visualizzata un'icona per indicare che il prezzo supera la tolleranza prezzi consentita del 2%.
5.  Nella pagina dei dettagli di abbinamento fatture, selezionare l'opzione per approvare la registrazione con discrepanze di abbinamento. Nella pagina Fattura fornitore, fare clic su OK. Se la fattura fornitore non fosse una fattura interaziendale, la registrazione avrebbe esito positivo. Tuttavia, poiché si utilizza una fattura fornitore interaziendale, la registrazione ha esito negativo. Per il commercio interaziendale, i totali fattura nell'ordine cliente interaziendale devono essere uguali ai totali fattura nell'ordine fornitore interaziendale corrispondente. Per risolvere questo problema, è necessario correggere il prezzo netto della fattura modificando il prezzo netto per riportarlo all'importo predefinito, ossia 45,00.

## <a name="example-quantity-matching-with-intercompany-trade"></a>Esempio: abbinamento quantità con il commercio interaziendale
Le quantità dell'ordine fornitore interaziendale e dell'ordine cliente interaziendale devono corrispondere. Tale requisito ha la priorità su qualsiasi approvazione di abbinamento fatture applicabile. In questo esempio viene utilizzata la seguente impostazione aggiuntiva per il commercio interaziendale:
-   In Fabrikam Purchase i criteri delle azioni dell'ordine fornitore per il fornitore 3024 vengono impostati per registrare automaticamente sia la fattura cliente originale sia la fattura fornitore interaziendale.

In questo esempio viene utilizzata la seguente impostazione aggiuntiva per l'abbinamento fatture contabilità fornitori per Fabrikam Purchase:
-   Nella pagina dei gruppi di modelli di articoli per il gruppo di modelli utilizzato per l'articolo B-R14 è selezionata l'opzione Requisiti ricevimento.
-   La quantità disponibile per l'articolo B-R14 è pari a 0 (zero).

Ad esempio, attenersi alla procedura descritta di seguito.
1.  Creare l'ordine cliente SO999 per il cliente 4020 in Fabrikam Purchase. L'ordine contiene una voce: 100 batterie (articolo B-R14) a un prezzo unitario di 1,00. L'ordine fornitore interaziendale ICPO333 viene creato automaticamente per il fornitore 3024 in Fabrikam Purchase, mentre l'ordine cliente ICSO999 viene creato automaticamente in Fabrikam Sales.
2.  In Fabrikam Sales eseguire un aggiornamento della fattura per ICSO999. La registrazione ha esito negativo perché l'articolo non è disponibile e non è stato ancora ricevuto, pertanto le informazioni finanziarie non possono essere aggiornate.
3.  In Fabrikam Sales registrare la ricezione degli articoli e un documento di trasporto per ICSO999. In Fabrikam Purchase viene automaticamente registrata un'entrata prodotti per ICPO333 e la quantità ricevuta per l'articolo B-R14 diventa pari a 100.
4.  In Fabrikam Sales eseguire un aggiornamento della fattura per ICSO999. La registrazione ha esito positivo in entrambe le persone giuridiche. In Fabrikam Purchase, la quantità acquistata per l'articolo B-R14 diventa pari a 100.







---
title: Registrare una fattura fornitore nel giornale di registrazione fatture
description: Questa guida attività indicherà come registrare le fatture fornitore non associate a ordini fornitore.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 775f3764d34cecbfc071ff7420d32c7832b42308
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556348"
---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a>Registrare una fattura fornitore nel giornale di registrazione fatture

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa guida attività indicherà come registrare le fatture fornitore non associate a ordini fornitore. Gli esempi di questo tipo di fattura includono le spese per le forniture o i servizi.  Questa registrazione utilizza la società dimostrativa USMF.

1. Andare a Contabilità fornitori > Aree di lavoro > Inserimento fatture fornitore.
2. Fare clic su Nuovo giornale di registrazione fatture.
3. Fare clic su Nuovo.
4. Nel campo Nome immettere il nome del giornale di registrazione o fare clic sul pulsante a discesa per aprire la ricerca.
5. Nel campo Descrizione digitare un valore.
6. Fare clic su Righe.
    * Nel campo Data, immettere la data di registrazione che aggiornerà la contabilità generale.  
7. Nel campo Conto specificare il conto fornitore.
8. Nel campo Fattura immettere il numero di fattura.
9. Digitare un valore nel campo Descrizione.
10. Nel campo Credito immettere un numero.
11. Nel campo Conto di contropartita immettere il numero di conto o fare clic sul pulsante a discesa per aprire la ricerca.
    * Come fascia IVA predefinita verrà impostata quella del conto fornitore.  
    * Come fascia IVA articoli predefinita verrà impostata quella del conto principale specificata nel campo Conto di contropartita.  
    * La data di scadenza verrà calcolata in base ai Termini di pagamento.  
    * Come sconto di cassa predefinito verrà impostato quello del conto fornitore.  
12. Fare clic su Registra.
13. Chiudere la pagina.


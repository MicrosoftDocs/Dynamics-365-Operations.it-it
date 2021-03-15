---
title: Registrare una fattura fornitore nel giornale di registrazione fatture
description: Questa guida attività indicherà come registrare le fatture fornitore non associate a ordini fornitore.
author: abruer
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 18d8b74bd8783c23e548a3185414d1461bc1d869
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971830"
---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a>Registrare una fattura fornitore nel giornale di registrazione fatture

[!include [banner](../../includes/banner.md)]

Questa guida attività indicherà come registrare le fatture fornitore non associate a ordini fornitore. Gli esempi di questo tipo di fattura includono le spese per le forniture o i servizi.  Questa registrazione utilizza la società dimostrativa USMF.

1. Andare a **Pannello di navigazione > Moduli > Contabilità fornitori > Aree di lavoro > Inserimento fatture fornitore**.
2. Fare clic su **Nuovo giornale di registrazione fatture** nel **riquadro azioni**.
3. Fare clic su **Nuovo**.
4. Nel campo **Nome** immettere il nome del giornale di registrazione o fare clic sul pulsante a discesa per aprire la ricerca.
5. Digitare un valore nel campo **Descrizione**
6. Nel **riquadro azioni** fare clic su **Righe**. Nel campo **Data**, immettere la data di registrazione che aggiornerà la contabilità generale.  
7. Nel campo **Conto** specificare il **conto fornitore**.
8. Nel campo **Fattura** immettere il numero di fattura.
9. Digitare un valore nel campo **Descrizione**
10. Nel campo **Credito** immettere un numero.
11. Nel campo **Conto di contropartita** immettere il numero di conto o fare clic sul pulsante a discesa per aprire la ricerca.
    * Come **Fascia IVA** predefinita verrà impostata quella del conto fornitore.  
    * Come **fascia IVA articoli** predefinita verrà impostata quella del conto principale specificata nel campo **Conto di contropartita**.  
    * La **data di scadenza** verrà calcolata in base ai Termini di pagamento.  
    * Come **sconto di cassa** predefinito verrà impostato quello del conto fornitore.
12. Se è stato abilitato il flusso di lavoro del giornale di registrazione fatture fornitore, fai clic su **Flusso di lavoro > Invia**.
    * Quando l'invio viene approvato, la data verrà anticipata al primo giorno del successivo periodo di apertura, se la data di registrazione della transazione rientra in un periodo In sospeso o Chiuso per la registrazione contabile.
12. Fare clic su **Registra**.
13. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
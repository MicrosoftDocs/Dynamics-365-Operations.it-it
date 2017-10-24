--- 
title: Definire termini di pagamento fornitore
description: Impostare i termini di pagamento per le fatture fornitore.
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a00ca73b1bc301960132a86846749d12c39ed3f7
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="define-vendor-payment-terms"></a>Definire termini di pagamento fornitore

[!include[task guide banner](../../includes/task-guide-banner.md)]

Impostare i termini di pagamento per le fatture fornitore. In questa attività viene utilizzata la società dimostrativa USMF.

1. Andare a Contabilità fornitori > Impostazione pagamenti > Termini di pagamento.
2. Fare clic su Nuovo.
    * La pagina Termini di pagamento viene utilizzata per definire la modalità di calcolo della data di scadenza. Tale pagina viene utilizzata per definire come la data dello sconto di cassa verrà calcolata.  
3. Digitare un valore nel campo Termini di pagamento.
4. Nel campo Descrizione digitare un valore.
5. Nel campo Giorni immettere un numero.
    * Il numero immesso in questo campo verrà utilizzato per essere aggiunto alla data di scadenza o alla fine del periodo identificato nel Metodo di pagamento. Ad esempio, se si seleziona Netto, il numero verrà aggiunto alla data di scadenza. Se si seleziona Mese corrente, verrà aggiunto il numero all'ultimo giorno del mese corrente per calcolare la data di scadenza.  
6. Fare clic su Salva.
7. Chiudere la pagina.
8. Andare a Contabilità fornitori > Impostazione pagamenti > Sconti di cassa.
9. Fare clic su Nuovo.
10. Nel campo Sconto di cassa immettere un ID.
11. Nel campo Descrizione digitare un valore.
12. Se il fornitore offre più livelli di sconto, selezionare lo sconto di cassa successivo dopo che quello corrente è scaduto.
13. Chiudere la pagina.
14. Nel campo Giorni immettere un numero.
    * La quantità immessa nel campo Giorni verrà utilizzata per calcolare la data dello sconto di cassa in base all'opzione selezionata nel campo Netto/Corrente. Se è stato selezionato Netto, la quantità verrà aggiunta alla data della fattura per determinare la data dello sconto di cassa. Se è stato selezionato Mese corrente, la quantità verrà aggiunta alla fine del mese della valuta per determinare la data dello sconto di cassa.  
15. Immettere la percentuale dello sconto di cassa nel campo Sconto. 
16. Immettere il conto principale in cui verrà registrato lo sconto di cassa per le fatture cliente.
17. Immettere il conto principale in cui verrà registrato lo sconto di cassa per le fatture fornitore.
    * Se "conti di contropartita di sconto" viene impostato per l'utilizzo del conto principale per lo sconto fornitore, verrà utilizzato il conto principale.  Se l'opzione è impostata su Conti nelle righe fattura, lo sconto di cassa verrà registrato nei conti spese/cespite nelle righe della fattura fornitore.  
18. Fare clic su Salva.



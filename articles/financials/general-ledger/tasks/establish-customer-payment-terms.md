--- 
title: Definire condizioni di pagamento cliente
description: Questa procedura consente di definire un'impostazione dello sconto di cassa e della data di scadenza.
author: aprilolson
manager: AnnBe
ms.date: 10/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ef3cad6538d9efbd1c1881f4b7d771382d9b1ba8
ms.openlocfilehash: 04b45508047d26ef7c08ede5862be75835783ef5
ms.contentlocale: it-it
ms.lasthandoff: 10/26/2017

---
# <a name="establish-customer-payment-terms"></a>Definire condizioni di pagamento cliente

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura consente di definire un'impostazione dello sconto di cassa e della data di scadenza. Questa guida attività utilizza la società dimostrativa USMF.

1. Andare a Contabilità clienti > Impostazione pagamenti > Giorni di pagamento.
    * L'impostazione dei termini di pagamento viene condivisa per la contabilità clienti e la contabilità fornitori. Se viene definita nel modulo, sarà disponibile anche nell'altro modulo. Per questa guida attività tutti i termini di pagamento vengono impostati nella contabilità clienti.  
2. Fare clic su Nuovo.
    * Creare un giorno di pagamento se i termini di pagamento richiedono un determinato giorno della settimana (lunedì, martedì e così via) o una data specifica del mese (quinta, decima e così via).  
3. Nel campo Giorno di pagamento, immettere un ID per il giorno di pagamento nel campo Giorno di pagamento.
4. Nel campo Descrizione immettere una descrizione del giorno di pagamento.
5. Nel campo Settimana/Mese, selezionare Settimana o Mese.
    * Se si desidera immettere un giorno della settimana, ad esempio lunedì, selezionare Settimana. Se si desidera immettere una data del mese, ad esempio la decima, selezionare Mese. Selezionare Mese per questo esempio.  
6. Immettere una data nel campo Giorno del mese.
    * La data deve essere immessa come numero, ad esempio "10" e non come "decima".  
7. Fare clic su Salva.
8. Chiudere la pagina.
9. Andare a Contabilità clienti > Impostazione pagamenti > Condizioni di pagamento.
10. Fare clic su Nuovo.
    * I termini di pagamento vengono utilizzati per definire la modalità di calcolo delle date di scadenza. L'impostazione della data dello sconto di cassa viene definita in una pagina separata.  
11. Nel campo Termini di pagamento immettere un ID nel campo Termini di pagamento.
12. Nel campo Descrizione immettere una descrizione.
13. Selezionare un metodo di pagamento, ad esempio COD, Netto, Mese corrente e così via.
    * Il metodo di pagamento viene utilizzato per definire la modalità di calcolo delle date di scadenza.  Ad esempio, Netto viene utilizzato se la data di scadenza è sempre un determinato numero di mesi o di giorni dopo la data della fattura. COD può essere utilizzato quando il pagamento viene richiesto al ricevimento della fattura, in modo da non calcolare una data di scadenza. Selezionare Mese corrente per la guida attività.  
14. Selezionare un giorno di pagamento se un determinato giorno della settimana o una determinata data verranno inclusi nel calcolo.
    * A seconda dei termini di pagamento, è possibile immettere una quantità in Mesi o Giorni. Oppure è possibile utilizzare lo Scadenzario pagamenti o il Giorno di pagamento per "aggiungere" alla fine del Metodo di pagamento. Se la data di scadenza verrà sempre il decimo giorno del mese successivo, selezionare un giorno di pagamento del decimo giorno.  
15. Fare clic su Salva.
16. Chiudere la pagina.
17. Fare clic su Contabilità clienti > Impostazione pagamenti > Sconti di cassa.
18. Fare clic su Nuovo.
    * Questa pagina viene utilizzata per definire come la data dello sconto di cassa verrà calcolata.  
19. Nel campo Sconto di cassa, immettere un ID nel campo Sconto di cassa.
20. Nel campo Descrizione immettere una descrizione.
21. Se è è disponibile uno sconto di cassa a livelli, selezionare il codice sconto successivo rilevante dopo il nuovo sconto di cassa.
22. Immettere il numero di giorni utilizzati per calcolare la data dello sconto di cassa.
    * Se il principio Netto è selezionata, il numero di giorni verrà aggiunto alla data della fattura per calcolare la data dello sconto di cassa.  
23. Immettere la percentuale dello sconto di cassa.
24. Immettere il conto principale in cui verrà registrato lo sconto di cassa per le fatture cliente.
25. Selezionare un'opzione nel campo Conti di contropartita sconti.
    * Se si seleziona "conti nelle righe fattura", lo sconto di cassa verrà registrato nello stesso conto principale spese/cespite nelle righe della fattura fornitore. Se si seleziona "Utilizza conto principale per le fatture fornitore", lo sconto di cassa verrà registrato nel conto principale definito in "Conto principale per le fatture fornitore". Per questo esempio selezionare "Utilizza conto principale per le fatture fornitore".  
26. Immettere il conto principale in cui verrà registrato lo sconto di cassa per le fatture fornitore.
27. Fare clic su Salva.



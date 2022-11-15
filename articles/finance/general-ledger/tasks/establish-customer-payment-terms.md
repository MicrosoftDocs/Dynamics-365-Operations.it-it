---
title: Definire condizioni di pagamento cliente
description: Questa procedura consente di definire un'impostazione dello sconto di cassa e della data di scadenza.
author: aprilolson
ms.date: 08/29/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PaymDay, PaymTerm, CashDisc
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9b2ae5e63a2efb4bc913efa4d88c65a70133a2d9
ms.sourcegitcommit: f96e5dec5a808d9819d2a23b8e15ce00aeff475b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2022
ms.locfileid: "9752778"
---
# <a name="establish-customer-payment-terms"></a>Definire condizioni di pagamento cliente

[!include [banner](../../includes/banner.md)]

Questa procedura consente di definire un'impostazione dello sconto di cassa e della data di scadenza. Questa guida attività utilizza la società dimostrativa USMF.

1. Selezionare **Pannello di navigazione > Moduli > Contabilità clienti > Impostazione pagamenti > Giorni di pagamento**. L'impostazione dei **termini di pagamento** viene condivisa per la **contabilità clienti** e la **contabilità fornitori**. Se viene definita nel modulo, sarà disponibile anche nell'altro modulo. Per questa guida attività, vengono impostati tutti i termini di pagamento in **Contabilità clienti**.
2. Fare clic su **Nuovo**. Creare un giorno di pagamento se i termini di pagamento richiedono un determinato giorno della settimana (lunedì, martedì e così via) o una data specifica del mese (quinta, decima e così via). 
3. Nel campo **Giorno di pagamento** immettere un ID.
4. Nel campo **Descrizione** immettere una descrizione del giorno di pagamento.
5. Nel campo **Settimana/Mese**, selezionare "Settimana" o "Mese". Se si desidera immettere un giorno della settimana, ad esempio lunedì, selezionare Settimana. Se si desidera immettere una data del mese, ad esempio la decima, selezionare Mese. Selezionare Mese per questo esempio. 
6. Immettere una data nel campo **Giorno del mese**. La data deve essere immessa come numero, ad esempio "10" e non come "decima". 
7. Fare clic su **Salva**.
8. Chiudere la pagina.
9. Selezionare **Pannello di navigazione > Moduli > Contabilità clienti > Impostazione pagamenti > Termini di pagamento**. 

>[!NOTE] 
>Se **Termini di pagamento** è **Contanti**, il campo **Pagamento in contanti** della pagina **Termini di pagamento** deve essere **No**.

10. Fare clic su **Nuovo**. I **Termini di pagamento** vengono utilizzati per definire la modalità di calcolo delle date di scadenza. L'impostazione della data dello sconto di cassa viene definita in una pagina separata. 
11. Nel campo **Termini di pagamento** immettere un ID.
12. Nel campo **Descrizione** immettere una descrizione.
13. Selezionare un **Metodo di pagamento**, ad esempio **COD**, **Netto**, **Mese corrente** e così via. Il **Metodo di pagamento** viene utilizzato per definire la modalità di calcolo delle date di scadenza. Ad esempio, **Netto** viene utilizzato se la data di scadenza è sempre un determinato numero di mesi o di giorni dopo la data della fattura. **COD** può essere utilizzato quando il pagamento viene richiesto al ricevimento della fattura, in modo da non calcolare una data di scadenza. Selezionare **Mese corrente** per la guida attività.  
14. Selezionare un **giorno di pagamento** se un determinato giorno della settimana o una determinata data verranno inclusi nel calcolo. A seconda dei termini di pagamento, è possibile immettere una quantità in Mesi o Giorni. Oppure è possibile utilizzare lo **Scadenzario pagamenti** o il **Giorno di pagamento** da "aggiungere" alla fine del **Metodo di pagamento**. Se la data di scadenza verrà sempre il decimo giorno del mese successivo, selezionare un **giorno di pagamento** del decimo giorno. Se si usa un **Calendario pagamenti**, è possibile definire in che modo viene determinata la scadenza quando la data calcolata cade in un giorno non lavorativo. La scadenza iniziale viene calcolata in base ai giorni di calendario. Se la data calcolata cade in un giorno non lavorativo, è possibile modificare la data calcolata in base al giorno lavorativo successivo o precedente.
15. Fare clic su **Salva**.
16. Chiudi la pagina.
17. Selezionare **Contabilità clienti > Impostazione pagamenti > Sconti di cassa**.
18. Fare clic su **Nuovo**. Questa pagina viene utilizzata per definire come la data dello sconto di cassa verrà calcolata. 
19. Nel campo **Sconto di cassa** immettere un ID.
20. Nel campo **Descrizione** immettere una descrizione.
21. Se è è disponibile uno sconto di cassa a livelli, selezionare il **codice sconto successivo** rilevante dopo il nuovo sconto di cassa.
22. Nel campo **Giorni**, immettere il numero di giorni utilizzati per calcolare la data dello sconto di cassa. Se il principio **Netto** è selezionato, il numero di giorni verrà aggiunto alla data della fattura per calcolare la data dello sconto di cassa.  
23. Immettere la percentuale dello sconto di cassa nel campo **Percentuale sconto**.
24. In **Conto principale per sconti cliente**, immettere il conto principale in cui lo sconto di cassa verrà registrato per le fatture cliente.
25. Selezionare un'opzione nel campo **Conti di contropartita sconti**. Se si seleziona "conti nelle righe fattura", lo sconto di cassa verrà registrato nello stesso conto principale spese/cespite nelle righe della fattura fornitore. Se si seleziona **Utilizza conto principale per le fatture fornitore**, lo sconto di cassa verrà registrato nel conto principale definito in **Conto principale per le fatture fornitore**. Per questo esempio selezionare **Utilizza conto principale per le fatture fornitore**. 
26. Nel campo **Conto principale per sconti fornitore**, immettere il conto principale in cui lo sconto di cassa verrà registrato per le fatture fornitore.
27. Fare clic su **Salva**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

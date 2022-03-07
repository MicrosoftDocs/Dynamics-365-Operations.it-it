---
title: Impostare commissioni di pagamento per i pagamenti all'autorità TCS
description: In questo argomento viene illustrato come impostare commissioni di pagamento addebitate per i pagamenti all'autorità TDS.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 9213827ea1ad342beb7ac2fe586606651cfdcfa1
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "6358436"
---
# <a name="set-up-payment-fees-for-tds-authority-payments"></a>Impostare commissioni di pagamento per i pagamenti all'autorità TCS

[!include [banner](../includes/banner.md)]

In questo argomento viene illustrato come impostare commissioni di pagamento addebitate per i pagamenti all'autorità TDS.

1. Vai a **Contabilità fornitori \> Impostazione pagamenti \> Commissione di pagamento**.

    [![Pagina Commissione pagamento.](./media/apac-ind-TDS-28.png)](./media/apac-ind-TDS-28.png)

2. Seleziona **Nuovo** per creare una nuova commissione di pagamento e immetti i dettagli richiesti.
3. Nel campo **Tipo di commissione** seleziona il tipo di commissione pagamento:

    - **Nessuno**
    - **Interessi** - Gli interessi vengono addebitati sui pagamenti in ritardo effettuati al fornitore dell'autorità TDS.
    - **Altri** -Altri addebiti vengono addebitati sui pagamenti in ritardo effettuati al fornitore dell'autorità TDS.

    Se selezioni **Interessi** o **Altri**, il campo **Addebito** viene impostato automaticamente su **Contabilità generale**.

4. Se hai selezionato **Interessi** o **Altri** nel campo **Tipo di campo**, nel campo **Conto principale** seleziona il conto CoGe in cui registrare gli interessi o altri addebiti.
5. Immetti gli altri dettagli necessari.
6. Nel riquadro Azioni seleziona **Impostazione commissione pagamento** per aprire la pagina **Impostazione commissione pagamento**, dove è possibile impostare commissioni di pagamento per varie combinazioni di banche, metodi di pagamento, specifiche di pagamento, valute e intervalli di date.

    [![Pagina Impostazione commissione pagamento.](./media/apac-ind-TDS-21.png)](./media/apac-ind-TDS-21.png)

7. Nella scheda **Panoramica**, nel campo **Raggruppamenti**, specifica per quali banche stai impostando la commissione di pagamento:

    - **Tabella** - La commissione è valida per un conto bancario specifico.
    - **Gruppo** - La commissione è valida per un gruppo bancario specifico.
    - **Tutto** - La commissione è valida per tutti i conti bancari.

8. Se hai selezionato **Tabella** o **Gruppo** nel campo **Raggruppamenti**, nel campo **Relazione bancaria**, seleziona il conto bancario o il gruppo bancario specifico per cui stai impostando la commissione di pagamento.
9. Nel campo **Metodo di pagamento**, seleziona un metodo di pagamento per il pagamento delle commissioni.
10. Nel campo **Specifiche pagamento** seleziona o immetti il codice della specifica di pagamento che è stato generato nella pagina **Specifiche pagamento**.
    - La specifica di pagamento viene utilizzata con i metodi di trasferimento fondi attraverso sistemi di pagamento elettronici.
12. Nel campo **Valuta pagamento**, seleziona la valuta che attiva la commissione. Solo le transazioni che utilizzano la valuta selezionata possono attivare la commissione. Se lasci vuoto questo campo, tutte le valute attivano la commissione.
13. Nel campo **Percentuale/importo** seleziona il metodo di calcolo. Le opzioni sono **Importo**, **Percentuale** e **Intervallo**.
14. Nel campo **Importo commissione**, specifica l'importo della commissione come percentuale del pagamento o dell'importo di un pagamento.
15. Nel campo **Valuta commissioni**, specifica il codice valuta della commissione.
16. Seleziona la scheda **Generale** per visualizzare o modificare i dettagli del conto bancario selezionato.

    [![Scheda Generale.](./media/apac-ind-TDS-22.png)](./media/apac-ind-TDS-22.png)

16. Nel campo **Minimo** immetti l'importo minimo della transazione che attiva la commissione.
17. Nel campo **Massimo** immetti l'importo massimo della transazione che attiva la commissione.
18. Nei campi **Data iniziale** e **Data finale**, definisci un intervallo di date per il calcolo delle commissioni.
19. Nel campo **Commissione minima**, specifica l'importo della commissione come percentuale del pagamento o dell'importo di un pagamento.
20. Nel campo **Fascia IVA**, seleziona la fascia IVA da utilizzare per calcolare l'IVA per l'importo della commissione.
21. Nel campo **Fascia IVA articoli**, seleziona la fascia IVA articoli da utilizzare per calcolare l'IVA articoli per l'importo della commissione.
22. Seleziona la scheda **Intervallo**. 

    [![Scheda Intervallo.](./media/apac-ind-TDS-23.png)](./media/apac-ind-TDS-23.png)

23. Nel campo **Giorni**, immetti il numero di giorni compresi tra la data di registrazione (data di sconto) del pagamento e la data di scadenza dell'effetto passivo.
24. Nel campo **Percentuale/importo**, indica se la specifica è una percentuale o un importo fisso.
25. Nel campo **Importo commissione**, immetti l'importo della commissione come percentuale del pagamento o dell'importo di un pagamento.
26. Chiudi la pagina **Impostazione commissione pagamento**.
27. Chiudi la pagina **Commissione pagamento**.

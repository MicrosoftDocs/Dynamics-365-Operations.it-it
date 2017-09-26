--- 
title: Creare un nuovo mandato di addebito diretto per un cliente
description: "In questa guida attività viene illustrata la creazione di un mandato di addebito diretto e il suo utilizzo in una fattura."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: e1ac289c261922f013b679eecfb054390b8aef73
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a>Creare un nuovo mandato di addebito diretto per un cliente

[!include[task guide banner](../../includes/task-guide-banner.md)]

In questa guida attività viene illustrata la creazione di un mandato di addebito diretto e il suo utilizzo in una fattura.


## <a name="create-a-bank-account"></a>Creare un conto bancario
1. Andare a Contabilità clienti > Clienti > Tutti i clienti.
2. Selezionare, ad esempio, US-001
3. Nel riquadro azioni fare clic su Cliente.
4. Fare clic su Conti bancari.
5. Fare clic su Nuovo.
6. Digitare un valore nel campo Conto bancario.
7. Digitare un valore nel campo Nome.
8. Digitare un valore nel campo IBAN.
9. Digitare un valore nel campo Valuta.
10. Fare clic su Salva.
11. Chiudere la pagina.
12. Andare a Gestione cassa e banche > Conti bancari > Conti bancari.
13. Nell'elenco trovare e selezionare il record desiderato.
14. Nell'elenco fare clic sul collegamento nella riga selezionata.
15. Fare clic su Modifica.
16. Espandere la sezione Identificazione aggiuntiva.
17. Immettere un valore nel campo ID addebito diretto.
18. Digitare un valore nel campo IBAN.
19. Chiudere la pagina.
20. Chiudere la pagina.

## <a name="define-the-electronic-payment-method"></a>Definire il metodo di pagamento elettronico
1. Andare a Contabilità clienti > Impostazione pagamenti > Metodi di pagamento.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Metodo di pagamento.
4. Nel campo Descrizione digitare un valore.
5. Il tipo di pagamento per il metodo di pagamento mandato di addebito diretto deve essere pagamento elettronico.
6. Selezionare Sì nel campo Richiedi mandato.
7. Chiudere la pagina.

## <a name="add-a-direct-debit-mandate-to-a-customer"></a>Aggiungere un mandato di addebito diretto a un cliente.
1. Andare a Contabilità clienti > Clienti > Tutti i clienti.
2. Selezionare, ad esempio, US-001
3. Fare clic su Modifica.
4. Espandere la sezione Impostazioni predefinite pagamento.
5. Nel campo Metodo di pagamento immettere o selezionare un valore.
6. Espandere la sezione Impostazioni predefinite pagamento.
7. Espandere la sezione Mandati di addebito diretto.
8. Scegliere Aggiungi.
9. Nel campo Conto bancario immettere o selezionare un valore.
10. Nel campo Conto bancario del creditore immettere o selezionare un valore.
11. Immettere il numero di pagamenti che si prevede di elaborare per il mandato.
12. Fare clic su OK.
13. Fare clic su Stampa.
14. Fare clic su Report mandati.
15. Chiudere la pagina.
16. Fare clic su Modifica.
17. Immettere una data nel campo Data di firma.
18. Fare clic su Sì.
19. Immettere il luogo in cui è stato firmato il mandato.
20. Fare clic su OK.
21. Chiudere la pagina.

## <a name="create-a-free-text-invoice-with-mandate"></a>Creare una fattura a testo libero con mandato
1. Andare a Contabilità clienti > Fatture > Tutte le fatture a testo libero.
2. Fare clic su Nuovo.
3. Selezionare il cliente aggiunto al mandato.
4. Nel campo ID mandato di addebito diretto, immettere o selezionare un valore.



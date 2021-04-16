---
title: Creare un nuovo mandato di addebito diretto per un cliente
description: In questa guida attività viene illustrata la creazione di un mandato di addebito diretto e il suo utilizzo in una fattura.
author: ShivamPandey-msft
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, BankAccountTable, CustPaymMode, CustDirectDebitMandate, BankAccountTableLookUp, SrsReportViewerForm,  LogisticsAddressCityLookup, CustFreeInvoice, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e3bbf3703941255dfd82b8fb501ba8a9d1f3a2ec
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835078"
---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a>Creare un nuovo mandato di addebito diretto per un cliente

[!include [banner](../../includes/banner.md)]

In questa guida attività viene illustrata la creazione di un mandato di addebito diretto e il suo utilizzo in una fattura.


## <a name="create-a-bank-account"></a>Creare un conto bancario
1. Nel **pannello di navigazione**, andare a **Moduli > Contabilità clienti > Clienti > Tutti i clienti**.
2. Nell'elenco selezionare un record. Selezionare, ad esempio, US-001
3. Nel riquadro azioni fare clic su **Cliente**.
4. Fare clic su **Conti bancari**.
5. Fare clic su **Nuovo**.
6. Digitare un valore nel campo **Conto bancario**.
7. Digitare un valore nel campo **Nome**.
8. Digitare un valore nel campo **IBAN**.
9. Digitare un valore nel campo **Valuta**.
10. Fare clic su **Salva**.
11. Chiudere la pagina.
12. Nel **pannello di navigazione**, andare a **Moduli > Gestione cassa e banche > Conti bancari > Conti bancari**.
13. Nell'elenco trovare e selezionare il record desiderato.
14. Nell'elenco fare clic sul collegamento nella riga selezionata.
15. Fare clic su **Modifica**.
16. Espandere la Scheda dettaglio **Identificazione aggiuntiva**.
17. Immettere un valore nel campo **ID addebito diretto**.
18. Digitare un valore nel campo **IBAN**.
19. Chiudere la pagina.
20. Chiudere la pagina.

## <a name="define-the-electronic-payment-method"></a>Definire il metodo di pagamento elettronico
1. Nel **pannello di navigazione** andare a **Moduli > Crediti e riscossioni > Impostazione pagamenti > Metodi di pagamento**.
2. Fare clic su **Nuovo**.
3. Digitare un valore nel campo **Metodo di pagamento**.
4. Digitare un valore nel campo **Descrizione**
5. Nel campo **Tipo di pagamento** immettere "Pagamento elettronico". Il tipo di pagamento per il metodo di pagamento mandato di addebito diretto deve essere pagamento elettronico.
6. Selezionare Sì nel campo **Richiedi mandato**.
7. Chiudere la pagina.

## <a name="add-a-direct-debit-mandate-to-a-customer"></a>Aggiungere un mandato di addebito diretto a un cliente.
1. Nel **pannello di navigazione**, andare a **Moduli > Contabilità clienti > Clienti > Tutti i clienti**.
2. Nell'elenco selezionare un record. Selezionare, ad esempio, US-001
3. Fare clic su **Modifica**.
4. Espandere la Scheda dettaglio **Impostazioni predefinite pagamento**.
5. Nel campo **Metodo di pagamento** immettere o selezionare un valore.
6. Espandere la Scheda dettaglio **Impostazioni predefinite pagamento**.
7. Espandere la Scheda dettaglio **Mandati di addebito diretto**.
8. Scegliere **Aggiungi**.
9. Nel campo **Conto bancario** immettere o selezionare un valore.
10. Nel campo **Conto bancario del creditore** immettere o selezionare un valore.
11. Nel campo **Frequenza pagamenti**, immettere il numero di pagamenti che si prevede di elaborare per il mandato.
12. Fare clic su **OK**.
13. Fare clic su **Stampa**.
14. Fare clic su **Report mandati**.
15. Chiudere la pagina.
16. Fare clic su **Modifica**.
17. Immettere una data nel campo **Data di firma**.
18. Fare clic su **Sì**.
19. Immettere il luogo in cui è stato firmato il mandato.
20. Fare clic su **OK**.
21. Chiudere la pagina.

## <a name="create-a-free-text-invoice-with-mandate"></a>Creare una fattura a testo libero con mandato
1. Nel **pannello di navigazione** andare a **Moduli > Contabilità clienti > Fatture > Tutte le fatture a testo libero**.
2. Fare clic su **Nuovo**.
3. Selezionare il cliente aggiunto al mandato.
4. Nel campo **ID mandato di addebito diretto**, immettere o selezionare un valore.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
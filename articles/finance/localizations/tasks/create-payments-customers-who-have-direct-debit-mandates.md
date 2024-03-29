---
title: Creare pagamenti per un cliente con mandati di addebito diretto
description: In questa procedura viene illustrato come generare un file di pagamento in addebito diretto ISO20022 per un cliente che ha configurato l'addebito diretto e una fattura da pagare.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustFreeInvoice, CustTableLookup, CustPostInvoiceJob, LedgerJournalTable, LedgerJournalTransCustPaym, SysQueryForm, CustPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0ecc28cb11b8c34a438bb47b1cfa9a37e17297e421020b32030261af95b86a49
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6757936"
---
# <a name="create-payments-for-a-customer-who-have-direct-debit-mandates"></a>Creare pagamenti per un cliente con mandati di addebito diretto

[!include [banner](../../includes/banner.md)]

In questa procedura viene illustrato come generare un file di pagamento in addebito diretto ISO20022 per un cliente che ha configurato l'addebito diretto e una fattura da pagare. La creazione e registrazione di una fattura sono facoltativi. Anziché avere una fattura da pagare è possibile selezionare un mandato in un giornale di registrazione prima di generare un file di pagamento, per supportare uno scenario di pagamento anticipato del cliente.



La società di dati dimostrativi utilizzata per creare questa procedura è DEMF.



Si tratta della quinta di cinque procedure che illustrano il processo di pagamento cliente utilizzando le configurazioni di creazione di report elettronici. Per completare questa attività, è necessario completare le attività precedenti. È innanzitutto necessario importare le configurazioni per la creazione di report elettronici di pagamento cliente, configurare il metodo di pagamento e impostare le informazioni sulla società e sul cliente. 


## <a name="post-a-free-text-invoice-with-direct-debit-information"></a>Registrare una fattura a testo libero con le informazioni sull'addebito diretto
1. Andare a Contabilità clienti > Fatture > Tutte le fatture a testo libero.
2. Fare clic su Nuovo.
3. Nel campo Conto cliente, immettere o selezionare un valore.
    * Selezionare, ad esempio, DE-010.  
4. Nel campo Metodo di pagamento immettere o selezionare un valore.
    * Ad esempio, selezionare Elettronico.  
5. Nel campo ID mandato di addebito diretto, immettere o selezionare un valore.
6. Fare clic su Aggiungi riga.
7. Digitare un valore nel campo Descrizione.
8. Nel campo Conto principale, specificare i valori desiderati.
9. Nel campo Prezzo unitario immettere un numero.
10. Fare clic su Registra.
11. Fare clic su OK.

## <a name="create-a-payment"></a>Creare un pagamento
1. Andare a Contabilità clienti > Pagamenti > Giornale di registrazione pagamenti.
2. Fare clic su Nuovo.
3. Nel campo Nome immettere o selezionare un valore.
4. Fare clic su Righe.
5. Fare clic su Proposta di pagamento.
6. Fare clic su Crea proposta di pagamento.
7. Espandere la sezione Record da includere.
8. Fare clic su Filtro.
9. Nell'elenco, selezionare la riga relativa alla tabella delle transazioni cliente e il campo Metodo di pagamento.
    * È possibile applicare qualsiasi criterio per la selezione delle transazioni cliente per il pagamento. Per questo esempio, utilizzare Elettronico come metodo di pagamento per filtrare le transazioni.  
10. Nel campo Criteri immettere o selezionare un valore.
11. Fare clic su OK.
12. Fare clic su OK.
13. Fare clic su Crea pagamenti.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
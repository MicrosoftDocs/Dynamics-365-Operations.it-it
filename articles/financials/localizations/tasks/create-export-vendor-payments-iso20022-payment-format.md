--- 
title: Creare ed esportare i pagamenti fornitore usando il formato di pagamento ISO20022
description: Questa procedura descrive come creare righe di pagamento nel giornale di registrazione pagamenti fornitore e come generare un file di pagamento fornitore usando l'esempio di bonifico ISO2022.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym, SysQueryForm, VendPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7cc90bc86cd489b124a806c480632dd53ba47f3f
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a>Creare ed esportare i pagamenti fornitore usando il formato di pagamento ISO20022

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura descrive come creare righe di pagamento nel giornale di registrazione pagamenti fornitore e come generare un file di pagamento fornitore usando l'esempio di bonifico ISO2022. 

La società di dati dimostrativi utilizzata per creare questa procedura è DEMF.

Si tratta della quinta procedura di cinque, che illustra il processo di pagamento fornitore utilizzando le configurazioni di creazione di report elettronici. Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.


## <a name="create-payment-lines"></a>Creare righe pagamento
1. Andare a Contabilità fornitori > Pagamenti > Giornale di registrazione pagamenti.
2. Fare clic su Nuovo.
3. Nell'elenco contrassegnare la riga selezionata.
4. Nel campo Nome immettere o selezionare un valore.
5. Fare clic su Righe.
6. Fare clic su Proposta di pagamento.
7. Fare clic su Crea proposta di pagamento.
8. Espandere la sezione Record da includere.
9. Fare clic su Filtro.
10. Nell'elenco, selezionare la riga per la tabella Fornitori e il campo Conto fornitore.
11. Nel campo Criteri immettere o selezionare un valore.
    * È possibile applicare qualsiasi criterio per la selezione delle transazioni fornitore da pagare, per questo esempio utilizzare DE-001 come conto fornitore.  
12. Fare clic su OK.
13. Fare clic su OK.
14. Fare clic su Crea pagamenti.

## <a name="generate-an-iso20022-payment-file"></a>Generare un file di pagamento ISO20022



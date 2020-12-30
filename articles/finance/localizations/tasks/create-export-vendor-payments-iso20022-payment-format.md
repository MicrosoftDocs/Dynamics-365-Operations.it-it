---
title: Creare ed esportare i pagamenti fornitore usando il formato di pagamento ISO20022
description: Questa procedura descrive come creare righe di pagamento nel giornale di registrazione pagamenti fornitore e come generare un file di pagamento fornitore usando l'esempio di bonifico ISO2022.
author: mrolecki
manager: AnnBe
ms.date: 01/17/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym, SysQueryForm, VendPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ff8a2858bfa96eb1d4b0afa1e48ebd1b578a4431
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444883"
---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a>Creare ed esportare pagamenti fornitore usando il formato di pagamento ISO20022

[!include [banner](../../includes/banner.md)]

Questo argomento descrive come creare righe di pagamento nel giornale di registrazione pagamenti fornitore e come generare un file di pagamento fornitore usando l'esempio di bonifico ISO2022.

Si tratta della quinta procedura di cinque, che illustra il processo di pagamento fornitore utilizzando le configurazioni di creazione di report elettronici. Per completare questo esempio utilizzare i dati dimostrativi DEMF.

## <a name="example"></a>Esempio

1.    Passare a **Contabilità fornitori > Pagamenti > Giornale di registrazione pagamenti.**
2.    Fare clic su **Nuovo**.
3.    Nel campo **Nome** immettere o selezionare un valore.
4.    Fare clic su **Righe > Proposta di pagamento > Crea proposta di pagamento**.
5.    Espandere la sezione **Record da includere**.
6.    Fare clic su **Filtro**.
7.    Nell'elenco, selezionare la riga per la **tabella Fornitori** e il **campo Conto fornitore**.
8.    Nel campo **Criteri** immettere o selezionare un valore. È possibile applicare qualsiasi criterio per la selezione delle transazioni fornitore da pagare, per questo esempio utilizzare DE-001 come conto fornitore.
12.    Fare clic su **OK**.
13.    Fare clic su **OK**.
14.    Fare clic su **Crea pagamenti**.
15. Generare un file di pagamento ISO20022.
    1.    Fare clic su **Genera pagamenti**.
    2.    Nel campo **Metodo di pagamento** immettere o selezionare un valore.
    3.    Digitare un valore nel campo **Nome file**. Per questo esempio, in seguito al pagamento EUR, il file generato sarà conforme a SEPA. Il bonifico ISO20022 nonché altri formati di pagamento fornitore possono essere utilizzati per generare pagamenti in altre valute.
    4.    Nel campo **Conto bancario** immettere o selezionare un valore.


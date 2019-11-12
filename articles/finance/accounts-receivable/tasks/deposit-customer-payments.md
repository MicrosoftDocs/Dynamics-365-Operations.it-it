---
title: Depositare pagamenti clienti
description: Depositare pagamenti cliente.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustPaym, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 595d1b609ae83af8f1581caeff9ef7d3892a6207
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178514"
---
# <a name="deposit-customer-payments"></a>Depositare pagamenti clienti

[!include [task guide banner](../../includes/task-guide-banner.md)]

Depositare pagamenti cliente. In questa attività viene utilizzata la società dimostrativa USMF.

1. Andare a **Pannello di navigazione > Moduli > Contabilità clienti > Pagamenti > Giornale di registrazione pagamenti**.
2. Selezionare **Nuovo**.
3. Nel campo **Nome**, selezionare **CustPay** dal menu a discesa.
4. Selezionare **Righe**.
5. Nel campo **Conto** selezionare il cliente per il quale si sta registrando il pagamento.
6. Nel campo **Avere**, immettere l'importo del pagamento. È possibile scegliere di lasciare l'importo vuoto e farlo calcolare dal sistema selezionando le fatture che sono state pagate.  
7. Digitare un valore nel campo **Riferimento di pagamento**. Il riferimento di pagamento può essere il numero di assegno per il pagamento che si immette. Il riferimento di pagamento è necessario per includere il pagamento in una distinta di deposito.  
8. Contrassegnare la casella Utilizzo di una distinta di deposito. Se il pagamento deve essere incluso nel deposito, modificare questa impostazione su Sì.  
9. Selezionare **Nuovo**.
10. Nel campo **Conto** selezionare il cliente per il pagamento successivo.
11. Nel campo **Avere**, immettere l'importo del pagamento.
12. Digitare un valore nel campo **Riferimento di pagamento**.
13. Contrassegnare la casella **Utilizzo di una distinta di deposito**.
14. Selezionare **Registra**. I pagamenti devono essere registrati prima che la distinta di deposito possa essere generata. In questo modo è possibile garantire che i pagamenti non cambino dopo che la distinta di deposito viene generata.  
15. Selezionare **Funzioni**.
16. Selezionare **Distinta di deposito**.
17. Selezionare **OK**. La prima pagina viene utilizzata per creare la distinta di deposito.  
18. Selezionare **OK**. Il secondo passaggio è di stampare la distinta di deposito, ma questo passaggio non è obbligatorio.  

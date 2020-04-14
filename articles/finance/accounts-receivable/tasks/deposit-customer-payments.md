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
ms.openlocfilehash: 1d903f557fbaeb720dd4a34dc1c772be0dcb56eb
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140185"
---
# <a name="deposit-customer-payments"></a>Depositare pagamenti clienti

[!include [banner](../../includes/banner.md)]

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


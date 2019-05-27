---
title: Panoramica pagamenti cliente
description: Questa guida attività descrive vari metodi utilizzati per immettere i pagamenti cliente.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, CustPaymEntry, CustTableLookup, LedgerJournalTransCustPaym, CustOpenTrans, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6e82be0d68165f62bbdc72a70b0675c7418b14ae
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566135"
---
# <a name="customer-payment-overview"></a>Panoramica pagamenti cliente

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa guida attività descrive vari metodi utilizzati per immettere i pagamenti cliente. In questa attività viene utilizzata la società dimostrativa USMF.

1. Andare a Contabilità clienti > Pagamenti > Giornale di registrazione pagamenti.
2. Fare clic su Nuovo.
3. Selezionare il giornale di registrazione pagamenti in cui salvare i pagamenti cliente.
4. Selezionare il giornale di registrazione o immetterlo manualmente.
5. Fare clic su Pagamenti cliente.
    * L'opzione Pagamenti cliente si utilizza per registrare un pagamento cliente alla volta. Le informazioni di pagamento vengono immesse nella parte superiore, quindi è possibile contrassegnare le fatture pagate nella stessa pagina.  
6. Immettere il cliente da cui è stato ricevuto il pagamento.
    * Se non si conosce il cliente, ma si conosce una transazione che è stata pagata, è possibile utilizzare il campo Transazione per immettere il pagamento. Immettere o selezionare la fattura nel campo Transazione. Una volta selezionata la transazione verrà impostato il cliente predefinito.  
7. Nel campo Riferimento di pagamento immettere un riferimento.
    * Il riferimento di pagamento può essere il numero di assegno o un riferimento dal pagamento elettronico del cliente. Il riferimento di pagamento è necessario solo se si include il pagamento in una distinta di deposito.  
8. Selezionare se il pagamento verrà incluso in una distinta di deposito. 
9. Immettere l'importo del pagamento cliente.
    * L'importo del pagamento non viene impostato come valore predefinito, ma deve essere immesso manualmente.  
10. Contrassegnare le fatture pagate dal cliente.
    * Se il pagamento è un pagamento anticipato, non verrà chiesto di contrassegnare alcuna fattura per la liquidazione. Il pagamento può comunque essere salvato e registrato. La liquidazione di una fattura può essere eseguita in un secondo momento.  
11. Immettere l'importo del pagamento da liquidare rispetto alla fattura contrassegnata. 
    * Questo campo può essere utilizzato quando il pagamento è parziale. Se non si immette un importo, l'importo da liquidare verrà determinato automaticamente.  
12. Fare clic su Salva nel giornale di registrazione.
    * Prima di salvare il pagamento nel giornale di registrazione, verificare che il conto di contropartita sia definito. L'opzione Salva nel giornale di registrazione consente di salvare il pagamento e di spostarlo nel giornale di registrazione. È quindi possibile continuare con il pagamento successivo.  
13. Chiudere la pagina.
14. Fare clic su Righe.
    * Quando si aprono le righe, verranno visualizzati tutti i pagamenti registrati nella pagina Pagamenti cliente e salvati nel giornale di registrazione. È inoltre possibile utilizzare questa pagina per immettere nuovi pagamenti cliente o modificare un pagamento cliente esistente prima della registrazione.  
15. Fare clic su Nuovo per creare un altro pagamento. 
16. Selezionare il cliente da cui è stato ricevuto il pagamento.
    * Se non si conosce il cliente ma si conosce una fattura pagata tramite il pagamento, utilizzare il campo Fattura per immettere o selezionare manualmente la fattura. Una volta selezionata la fattura verrà impostato il cliente predefinito.  
17. Fare clic su Liquida transazioni per contrassegnare le fatture che sono state pagate.
    * Non verrà richiesto di liquidare il pagamento in alcuna fattura. Se il pagamento è anticipato o non si conosce la fattura pagata, è possibile immettere e registrare il pagamento. Il pagamento può essere liquidato in una fattura in un momento successivo.  
18. Contrassegnare le fatture pagate con il pagamento. 
19. Immettere l'importo del pagamento che verrà liquidato rispetto alla fattura.
20. Fare clic su OK.
21. Nel campo Riferimento di pagamento immettere un riferimento. .
    * Il riferimento di pagamento è necessario solo se si include il pagamento in una distinta di deposito.  
22. Registrare i pagamenti cliente. 


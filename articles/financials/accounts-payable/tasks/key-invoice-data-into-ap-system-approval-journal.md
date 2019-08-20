---
title: Dati principali della fattura in sistema di contabilità fornitori utilizzando il giornale di registrazione approvazioni
description: Questa guida attività indicherà come utilizzare il registro fatture per creare fatture e quindi per utilizzare il giornale di approvazione per aggiornare i conti spese.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0faece510cc85fd86113d8b62d54b71f3014b1db
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1837043"
---
# <a name="key-invoice-data-into-ap-system-using-approval-journal"></a>Dati principali della fattura in sistema di contabilità fornitori utilizzando il giornale di registrazione approvazioni

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa guida attività indicherà come utilizzare il registro fatture per creare fatture e quindi per utilizzare il giornale di approvazione per aggiornare i conti spese.


## <a name="create-and-post-and-invoice"></a>Creare e registrare una fattura
1. Andare a Contabilità fornitori > Fatture > Registro fatture.
2. Fare clic su Nuovo.
3. Selezionare il nome del registro fatture che si desidera utilizzare.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Fare clic su Righe per aprire il registro e immettere le righe di spesa.
6. Selezionare un fornitore. Ad esempio, immettere o selezionare US-104
7. Digitare un valore nel campo Fattura.
8. Digitare un valore nel campo Descrizione.
9. Nel campo Credito immettere un numero.
10. Nel campo Approvata da fare clic sul pulsante a discesa per aprire la ricerca.
11. Evidenzi un approvatore e fare clic su per selezionare tale approvatore.
12. Fare clic su Registra.
13. Chiudere la pagina.
14. Chiudere la pagina.

## <a name="approve-an-invoice"></a>Approvare una fattura
1. Andare a Contabilità fornitori > Fatture > Approvazione fattura.
2. Fare clic su Nuovo.
3. Selezionare il nome del giornale di approvazione fatture che si desidera utilizzare.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Fare clic sulle righe per visualizzare una pagina in cui sarà possibile selezionare le fatture che si desidera approvare.
6. Selezionare Trova giustificativi per visualizzare tutte le fatture pronte per l'approvazione.
7. Contrassegnare la fattura creata.
8. Fare clic su Seleziona.
    * I giustificativi selezionati in precedenza vengono spostati in questo elenco dopo che sono stati selezionati.  
9. Fare clic su OK.
10. Fare clic su nel campo relativo al numero di conto per aggiungere un conto spese nella fattura.
11. Immettere un numero di conto e uscire dal campo. Ad esempio, immettere 600120.
12. Fare clic su Registra.
13. Fare clic su Giustificativo per visualizzare le voci registrate.
    * Il conto di approvazione fatture in sospeso viene stornato e sostituito con il conto spese effettivo.  


---
title: Creare una scrittura contabile utilizzando un modello
description: I giustificativi giornale di registrazione registrati possono essere salvati come modelli di giustificativo e applicati a un nuovo giustificativo giornale di registrazione.
author: aprilolson
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransDaily, LedgerJournalTransVoucherTemplate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: babbc5ee067743d368680970556f8e5d3d8585f0
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178417"
---
# <a name="create-a-journal-entry-using-template"></a>Creare una scrittura contabile utilizzando un modello

[!include [task guide banner](../../includes/task-guide-banner.md)]

I giustificativi giornale di registrazione registrati possono essere salvati come modelli di giustificativo e applicati a un nuovo giustificativo giornale di registrazione. Questa procedura utilizza la società dimostrativa USMF.

1. Andare a **Pannello di navigazione > Moduli > Contabilità generale > Inserimenti nel giornale di registrazione > Giornali di registrazione generali**.
2. Fare clic su **Nuova** nel **riquadro azioni**. Questa procedura inizia con la creazione e la registrazione di un giustificativo giornale di registrazione, ma qualsiasi giustificativi giornale di registrazione registrato in precedenza può essere salvato come modello.  
3. Nel campo **Nome** fare clic sul pulsante a discesa per aprire la ricerca.
4. Trovare e selezionare il record desiderato nell'elenco.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Fare clic su **Righe**.
7. Nel campo **Tipo di conto**, digitare un valore.
8. Digitare un valore nel campo **Descrizione**
9. Nel campo **Dare** digitare un valore.
10. Fare clic su **Nuovo**.
11. Nel campo **Tipo di conto**, digitare un valore.
12. Digitare un valore nel campo **Descrizione**
13. Nel campo **Dare** digitare un valore.
14. Fare clic su **Nuovo**.
14. Nel campo **Conto**, specificare i valori desiderati.
15. Digitare un valore nel campo **Descrizione**
16. Nel campo **Avere** digitare un valore per bilanciare il giustificativo.
17. Nel **riquadro azioni** fare clic su **Registra**.
18. Fare clic su **Funzioni**.
19. Fare clic su **Salva modello giustificativo**.
20. In questa procedura si presuppone un tipo di **modello percentuale**. Fare clic su OK.
    - Percentuale: gli importi nel giustificativo vengono convertiti in fattori percentuali, che consente l'applicazione di qualsiasi importo quando viene selezionato il modello di giustificativo.
    - Importo: gli importi effettivi verranno archiviati e applicati.  
21. Fare clic su **Giornali di registrazione generali**.
22. Fare clic su **Nuovo**.
23. Nel campo **Nome** fare clic sul pulsante a discesa per aprire la ricerca.
24. Nell'elenco fare clic sul collegamento nella riga selezionata.
25. Fare clic su **Righe**.
26. Fare clic su **Funzioni**.
27. Fare clic su **Seleziona modello giustificativo**.
28. Trovare il modello creato in precedenza. Fare clic su **OK**. Può essere necessario fare clic su **Passaggio precedente** e quindi di selezionare il modello corretto se esistono altri modelli.  
29. Nel campo **Importo** immettere l'importo da applicare al giustificativo. Il campo **Importo** viene visualizzato solo se il modello di giustificativo è di tipo Percentuale.  
30. Fare clic su **OK**.

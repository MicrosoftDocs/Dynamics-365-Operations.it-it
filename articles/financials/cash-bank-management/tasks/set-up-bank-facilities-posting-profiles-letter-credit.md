--- 
title: Impostare le linee di credito bancarie e i profili registrazione per la lettera di credito
description: Questa procedura consente di creare una linea di credito bancaria e di registrare un profilo necessari per elaborare le lettere di credito.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 43422627f8529768ab9377c04568da531d6565c6
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letter-of-credit"></a>Impostare le linee di credito bancarie e i profili registrazione per la lettera di credito

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura consente di creare una linea di credito bancaria e di registrare un profilo necessari per elaborare le lettere di credito. 

In questa attività viene utilizzata la società dimostrativa "USMF".






## <a name="general-ledger-parameter"></a>Parametro di contabilità generale
1. Andare a Gestione cassa e banche > Impostazioni > Parametri di gestione cassa e banche.
2. Espandere la sezione Documento bancario.
3. Selezionare l'opzione Abilita lettera di credito di importazione.
4. Selezionare l'opzione Abilita lettera di credito di esportazione.
5. Fare clic su Salva.
6. Chiudere la pagina.

## <a name="create-bank-facility"></a>Creare una linea di credito bancaria
1. Andare a Gestione cassa e banche > Impostazioni > Linee di credito bancarie.
2. Fare clic su Nuovo.
3. Nel campo Gruppo di linee di credito immettere il nome del gruppo di linee di credito bancarie.
4. Nel campo Descrizione immettere la descrizione del gruppo di linee di credito bancarie.
5. Fare clic su Salva.
6. Fare clic sulla scheda Tipi di linee di credito.
7. Fare clic su Nuovo.
8. Nel campo Tipi di linee di credito immettere un codice univoco.
9. Nel campo Descrizione digitare un valore.
10. Nel campo Gruppo di linee di credito fare clic sul pulsante a discesa per aprire la ricerca.
11. Trovare e selezionare il record desiderato nell'elenco.
12. Nell'elenco fare clic sul collegamento nella riga selezionata.
13. Nel campo Natura linea di credito selezionare la natura della linea di credito bancaria.
14. Fare clic su Salva.
15. Chiudere la pagina.

## <a name="bank-posting-profile"></a>Profilo di registrazione bancaria
1. Andare a Gestione cassa e banche > Impostazioni > Profilo di registrazione documenti bancari.
2. Fare clic su Nuovo.
3. Nel campo Numero conto/gruppo fare clic sul pulsante a discesa per aprire la ricerca.
4. Trovare e selezionare il record desiderato nell'elenco.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Selezionare il conto principale per la liquidazione.
    * Tale conto viene utilizzato per il calcolo della previsione di cassa.  
7. Nel campo Conto spese selezionare il conto per le transazioni di spesa.
8. Nel campo Conto a margine selezionare il conto per le transazioni a margine.
    * Su questo conto viene effettuato un addebito quando il margine iniziale viene registrato e accreditato al momento della registrazione del pagamento.  
9. Fare clic su Salva.



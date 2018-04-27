--- 
title: Impostare le linee di credito bancarie e i profili registrazione per le lettere di garanzia
description: "Questa attività crea una linea di credito bancaria e un profilo di registrazione necessari per l'elaborazione di una lettera di garanzia."
author: kweekley
manager: AnnBe
ms.date: 02/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 022b5d411b8240390c543ba726fe0d6838752944
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letters-of-guarantee"></a>Impostare le linee di credito bancarie e i profili registrazione per le lettere di garanzia

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Questa attività crea una linea di credito bancaria e un profilo di registrazione necessari per l'elaborazione di una lettera di garanzia.



In questa attività viene utilizzata la società dimostrativa USMF. 




## <a name="general-ledger-parameter"></a>Parametro di contabilità generale
1. Andare a Gestione cassa e banche > Impostazioni > Parametri di gestione cassa e banche.
2. Espandere la sezione Documento bancario.
3. Selezionare l'opzione Abilita lettera di garanzia.
4. Nel campo Giornale di registrazione transazioni fare clic sul pulsante a discesa per aprire la ricerca.
5. Trovare e selezionare il record desiderato nell'elenco.
6. Nell'elenco fare clic sul collegamento nella riga selezionata.
7. Fare clic sulla scheda Sequenze numeriche.
    * Definire il codice di sequenza numerica per il numero della lettera di garanzia e i riferimenti di transazione della lettera di garanzia  
8. Fare clic su Salva.
9. Chiudere la pagina.

## <a name="create-bank-facility"></a>Creare una linea di credito bancaria
1. Andare a Gestione cassa e banche > Impostazioni > Linee di credito bancarie.
2. Fare clic su Nuovo.
3. Nel campo Gruppo di linee di credito immettere il nome del gruppo di linee di credito bancarie per la transazione della lettera di garanzia.
4. Nel campo Descrizione digitare un valore.
5. Fare clic su Salva.
6. Fare clic sulla scheda Tipi di linee di credito.
7. Fare clic su Nuovo.
8. Nel campo Tipo di linea di credito immettere il nome del tipo di linea di credito bancaria correlato al contratto per linea di credito bancaria.
9. Digitare un valore nel campo Descrizione.
10. Nel campo Gruppo di linee di credito fare clic sul pulsante a discesa per aprire la ricerca.
11. Trovare e selezionare il record desiderato nell'elenco.
12. Nell'elenco fare clic sul collegamento nella riga selezionata.
13. Selezionare un'opzione nel campo Natura linea di credito.
14. Fare clic su Salva.
15. Chiudere la pagina.

## <a name="bank-posting-profile"></a>Profilo di registrazione bancaria
1. Andare a Gestione cassa e banche > Impostazioni > Profilo di registrazione documenti bancari.
2. Fare clic su Nuovo.
3. Nel campo Numero conto/gruppo fare clic sul pulsante a discesa per aprire la ricerca.
4. Trovare e selezionare il record desiderato nell'elenco.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Nel campo Conto di liquidazione selezionare il conto principale per la liquidazione.
7. Nel campo Conto spese selezionare il conto per le transazioni di spesa.
8. Nel campo Conto a margine selezionare il conto per la transazione a margine.
9. Nel campo Conto di liquidazione selezionare il conto di liquidazione per la transazione della lettera di garanzia. 
10. Fare clic su Salva.
11. Chiudere la pagina.



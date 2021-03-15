---
title: Impostare le linee di credito bancarie e i profili registrazione per le lettere di garanzia
description: Questa attività crea una linea di credito bancaria e un profilo di registrazione necessari per l'elaborazione di una lettera di garanzia.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b6da3b9358192997de1d0231e5c9c8eaba92a23b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976268"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letters-of-guarantee"></a>Impostare le linee di credito bancarie e i profili registrazione per le lettere di garanzia

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
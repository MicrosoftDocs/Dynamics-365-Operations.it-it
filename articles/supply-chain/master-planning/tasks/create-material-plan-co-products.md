--- 
title: Creare un piano materiali per co-prodotti
description: Il pianificatore della produzione pianifica i fabbisogni di materiali per gli articoli che sono co-prodotti della formula.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c8805ca02525ae001fbd5e10ad9405fe60c7473e
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-material-plan-for-co-products"></a>Creare un piano materiali per co-prodotti

[!include [task guide banner](../../includes/task-guide-banner.md)]

Il pianificatore della produzione pianifica i fabbisogni di materiali per gli articoli che sono co-prodotti della formula. La società di dati dimostrativi utilizzata per creare questa procedura è USP2.


## <a name="create-requirement-for-a-co-product"></a>Creare il fabbisogno per un co-prodotto
1. Fare clic su Dashboard predefinito.
2. Fare clic su Elaborazione e richiesta di informazioni ordini cliente.
3. Fare clic su Nuovo.
4. Fare clic su Ordine cliente.
5. Digitare un valore nel campo Conto cliente.
    * Esempio: US-001  
6. Fare clic su OK.
7. Nel campo Numero articolo, digitare un valore.
    * Esempio: P6003  
8. Nel campo Quantità immettere un numero.
    * Esempio: 50000  
9. Fare clic su Salva.

## <a name="create-a-material-plan-for-co-products"></a>Creare un piano materiali per co-prodotti
1. Fare clic su Pianificazione generale.
2. Nel campo Piano fare clic sul pulsante a discesa per aprire la ricerca.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Esempio: MasterPlan  
4. Fare clic su Esegui.
5. Espandere o comprimere la sezione Record da includere.
6. Fare clic su Filtro.
7. Nell'elenco selezionare la riga per Campo = Numero articolo.
8. Digitare un valore nel campo Criteri.
    * Esempio: P6003  
9. Fare clic su OK.
10. Fare clic su OK.
11. Fare clic su Ordini pianificati.
12. Utilizzare il filtro rapido per trovare i record. Ad esempio, filtrare il campo Numero articolo con un valore "P6000".
    * Applicare un filtro in base all'articolo formula con co-prodotto dell'articolo per cui è stato creato un ordine cliente.  
13. Nell'elenco contrassegnare la riga selezionata.
    * Selezionare una delle righe restituite dal filtro.  
14. Nell'elenco fare clic sul collegamento nella riga selezionata.
15. Espandere o comprimere la sezione Pegging.
16. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * L'ordine pianificato viene sottoposto all'ordine cliente per il co-prodotto.  
17. Chiudere la pagina.



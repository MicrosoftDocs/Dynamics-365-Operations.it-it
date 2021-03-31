---
title: Creare un piano materiali per co-prodotti
description: Il pianificatore della produzione pianifica i fabbisogni di materiali per gli articoli che sono co-prodotti della formula.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2a87935f8f30d909f1a6a62ed7be00c83476a36a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5214372"
---
# <a name="create-a-material-plan-for-co-products"></a>Creare un piano materiali per co-prodotti

[!include [banner](../../includes/banner.md)]

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
1. Chiudere la pagina.
2. Chiudere la pagina.
3. Fare clic su Pianificazione generale.
4. Nel campo Piano fare clic sul pulsante a discesa per aprire la ricerca.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Esempio: MasterPlan  
6. Fare clic su Esegui.
7. Espandere o comprimere la sezione Record da includere.
8. Fare clic su Filtro.
9. Nell'elenco selezionare la riga per Campo = Numero articolo.
10. Digitare un valore nel campo Criteri.
    * Esempio: P6003  
11. Fare clic su OK.
12. Fare clic su OK.
13. Fare clic su Ordini pianificati.
14. Utilizzare il filtro rapido per trovare i record. Ad esempio, filtrare il campo Numero articolo con un valore "P6000".
    * Applicare un filtro in base all'articolo formula con co-prodotto dell'articolo per cui è stato creato un ordine cliente.  
15. Nell'elenco contrassegnare la riga selezionata.
    * Selezionare una delle righe restituite dal filtro.  
16. Nell'elenco fare clic sul collegamento nella riga selezionata.
17. Espandere o comprimere la sezione Pegging.
18. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * L'ordine pianificato viene sottoposto all'ordine cliente per il co-prodotto.  
19. Chiudere la pagina.

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
1. Nel campo Piano fare clic sul pulsante a discesa per aprire la ricerca.
2. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Esempio: MasterPlan  
3. Fare clic su Esegui.
4. Espandere o comprimere la sezione Record da includere.
5. Fare clic su Filtro.
6. Nell'elenco selezionare la riga per Campo = Numero articolo.
7. Digitare un valore nel campo Criteri.
    * Esempio: P6003  
8. Fare clic su OK.
9. Fare clic su OK.
10. Fare clic su Ordini pianificati.
11. Utilizzare il filtro rapido per trovare i record. Ad esempio, filtrare il campo Numero articolo con un valore "P6000".
    * Applicare un filtro in base all'articolo formula con co-prodotto dell'articolo per cui è stato creato un ordine cliente.  
12. Nell'elenco contrassegnare la riga selezionata.
    * Selezionare una delle righe restituite dal filtro.  
13. Nell'elenco fare clic sul collegamento nella riga selezionata.
14. Espandere o comprimere la sezione Pegging.
15. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * L'ordine pianificato viene sottoposto all'ordine cliente per il co-prodotto.  
16. Chiudere la pagina.
17. Fare clic su Pianificazione generale.
18. Andare a Pianificazione generale > Impostazioni > Parametri di pianificazione generale.
19. Selezionare No nel campo Disattiva tutti i processi di pianificazione.
20. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
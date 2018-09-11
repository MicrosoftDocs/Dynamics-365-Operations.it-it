--- 
title: Configurare i costi standard di manodopera e spese
description: In questa procedura viene illustrato come impostare i costi standard per la manodopera e le spese per un progetto.
author: KimANelson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjCostPriceHour, ProjSalesPriceHour, ProjCostPriceExpense, ProjSalesPriceCost
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 432b5b195b29fb03786cb0560e277735b531b7d7
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="configure-standard-costs-for-labor-and-expenses"></a>Configurare i costi standard di manodopera e spese

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura viene illustrato come impostare i costi standard per la manodopera e le spese per un progetto. Questa attività utilizza il set di dati dimostrativi USSI.

1. Passare a Gestione progetti e contabilità > Impostazioni > Prezzi > Prezzo di costo (ora).
2. Fare clic su Nuovo.
3. Nel campo Data di validità, immettere una data.
4. Immettere un numero nel campo Prezzo di costo.
    * È possibile impostare un prezzo di costo standard in base alla categoria del progetto oppure prezzi di costo per numero lavoratore, numero progetto, categoria, data o una qualsiasi combinazione di questi elementi. Il prezzo di costo applicato corrisponderà a quello associato al livello di dettaglio più alto.  
5. Fare clic su Salva.
6. Chiudere la pagina.
7. Passare a Gestione progetti e contabilità > Impostazioni > Prezzi > Prezzo di vendita (ora).
8. Fare clic su Nuovo.
9. Nel campo Data di validità, immettere una data.
10. Selezionare un'opzione nel campo Valido per.
11. Immettere un numero nel campo Determinazione prezzo.
    * È possibile impostare un prezzo di vendita standard per transazioni orarie o per una categoria di progetto. Inoltre è possibile impostare i prezzi di vendita in base al numero del lavoratore, al numero del progetto, alla categoria, alla data della transazione oppure a una combinazione di questi elementi. Il prezzo di vendita effettivo, che viene applicato quando un lavoratore immette una transazione nel giornale di registrazione ore, è il prezzo di vendita con il livello di dettagli più alto. Se vengono impostati, ad esempio, un prezzo di vendita generale e un prezzo di vendita specifico per un lavoratore, verrà utilizzato automaticamente quello specifico per il lavoratore.  
12. Fare clic su Salva.
13. Chiudere la pagina.
14. Passare a Gestione progetti e contabilità > Impostazioni > Prezzi > Prezzo di costo (spesa).
15. Fare clic su Nuovo.
16. Nel campo Data di validità, immettere una data.
17. Immettere un numero nel campo Prezzo di costo.
    * Più campi possono essere completati, ma questo è il minimo necessario per salvare il record.  
18. Fare clic su Salva.
19. Chiudere la pagina.
20. Passare a Gestione progetti e contabilità > Impostazioni > Prezzi > Prezzo di vendita (spesa).
21. Fare clic su Nuovo.
22. Nel campo Data di validità, immettere una data.
23. Selezionare un'opzione nel campo Valido per.
24. Immettere un numero nel campo Determinazione prezzo.
    * Il prezzo di vendita effettivo, applicato quando un lavoratore immette una transazione in un giornale di registrazione spese, corrisponde al prezzo di vendita con il più alto livello di dettaglio. Se vengono impostati, ad esempio, un prezzo di vendita generale e un prezzo di vendita specifico per un lavoratore, verrà selezionato automaticamente quello specifico per il lavoratore.  
25. Fare clic su Salva.



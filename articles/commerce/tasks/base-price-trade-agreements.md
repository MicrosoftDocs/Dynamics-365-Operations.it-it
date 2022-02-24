---
title: Prezzo di base e accordi commerciali
description: In questa procedura vengono descritti i passaggi per creare accordi commerciali sui prezzi di vendita specifici del canale.
author: josaw1
manager: AnnBe
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PriceDiscGroup, RetailStoreTable, RetailChannelPriceGroup, EcoResProductDetailsExtended, PriceDiscAdmTable, PriceDiscAdm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 44dc059f7bfc3ba83a375c197ce67f1378a9bc9b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413516"
---
# <a name="base-price-and-trade-agreements"></a>Prezzo di base e accordi commerciali

[!include [banner](../includes/banner.md)]

In questa procedura vengono descritti i passaggi per creare accordi commerciali sui prezzi di vendita specifici del canale. Questa procedura utilizza la società di dati dimostrativi USRT.

1. Nel **pannello di navigazione** andare a **Moduli > Retail e Commerce > Prezzi e sconti > Gruppi di prezzi > Tutti i gruppi di prezzi**. I gruppi di prezzi indicano come gli accordi commerciali sono assegnati ai canali specifici. Utilizzando i gruppi di prezzi per assegnare gli accordi commerciali a un canale si abilita la determinazione dei prezzi specifici del canale.  
2. Fare clic su **Nuovo**.
3. Digitare un valore nel campo **Gruppi di prezzi**.
4. Digitare un valore nel campo **Nome**.
5. Fare clic su **Salva**.
6. Chiudere la pagina.
7. Nel **pannello di navigazione**, andare a **Moduli > Retail e Commerce > Canali > Punti vendita > Tutti i punti vendita**.
8. Nell'elenco selezionare 'New York'.
9. Nel riquadro azioni fare clic su **Punto vendita**.
10. Fare clic su **Gruppi di prezzi**.
11. Fare clic su **Nuovo**.
12. Nel campo **Gruppi di prezzi** fare clic sul pulsante a discesa per aprire la ricerca.
13. Nell'elenco trovare e selezionare il record desiderato.
14. Fare clic su **Salva**.
15. Chiudere la pagina.
16. Chiudere la pagina.
17. Nel **pannello di navigazione** andare a **Moduli > Retail e Commerce > Prodotti e categorie > Prodotti rilasciati per categoria**.
18. Nell'elenco fare clic sul collegamento nella riga selezionata.
19. Fare clic su **Modifica**.
20. Espandere la Scheda dettaglio **Vendi**.
21. Immettere un numero nel campo **Prezzo**. Il prezzo viene utilizzato se non viene trovato alcun accordo commerciale applicabile.  
22. Fare clic su **Salva**.
23. Nel **riquadro azioni** fare clic su **Vendi**.
24. Fare clic su **Crea accordi commerciali**.
25. Fare clic su **Nuovo**.
26. Nel campo **Nome** fare clic sul pulsante a discesa per aprire la ricerca.
27. Nell'elenco selezionare **Commercio**. Nei dati dimostrativi, il nome del giornale di registrazione **Commercio** dispone della relazione predefinita di **Prezzo (vend.)**. Questo significa che per tutte le nuove righe create verranno utilizzati per impostazione predefinita gli accordi commerciali sui prezzi di vendita.  
28. Nel **riquadro azioni** fare clic su **Righe**.
29. Nel campo **Tipo di codice parte**, seleziona 'Gruppo'.
30. Nel campo **Selezione del conto** fare clic sul pulsante a discesa per aprire la ricerca.
31. Nell'elenco trovare e selezionare il record desiderato. In tal modo viene completato il collegamento dal canale al gruppo di prezzi all'accordo commerciale.  
32. Nel campo **Relazione articolo**, digitare un valore.
33. Nel campo **Importo in valuta** immettere un numero.
34. Nella Scheda dettaglio **Dettagli**, selezionare o deselezionare la casella di controllo **Trova successivo**. Quando **Trova successivo** è impostato su "Sì", il motore di determinazione dei prezzi continua la ricerca di accordi commerciali applicabili con un prezzo di vendita inferiore. Quando **Trova successivo** è impostato su "No" il motore dei determinazione dei prezzi non esegue alcuna ricerca e utilizza l'accordo commerciale.  
35. Fare clic su **Registra**.
36. Fare clic su **OK**.
37. Chiudere la pagina.
38. Nel **riquadro azioni** fare clic su Vendi.
39. Fare clic su **Prezzo di vendita**.


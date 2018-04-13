--- 
title: " Definire programmi fedeltà"
description: "In questa procedura vengono descritti i passaggi per impostare un programma fedeltà con due livelli di fedeltà."
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: a27a2367ac41e86a3038594261c080ad2515eb94
ms.contentlocale: it-it
ms.lasthandoff: 02/07/2018

---
# <a name="define-loyalty-programs"></a> Definire programmi fedeltà

[!INCLUDE [task guide banner](../includes/task-guide-banner.md)]

In questa procedura vengono descritti i passaggi per impostare un programma fedeltà con due livelli di fedeltà. Questa procedura utilizza la società di dati dimostrativi USRT.

1. Passare a Vendita al dettaglio e commercio  > Programmi fedeltà.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome.
4. Nel campo Descrizione digitare un valore.
5. Fare clic su Aggiungi riga.
6. Nel campo Livello immettere un numero.
7. Nel campo Livello immettere il nome del livello del programma fedeltà.
8. Digitare un valore nel campo Descrizione.
9. Nel campo Intervallo date fare clic sul pulsante a discesa per aprire la ricerca.
    * Questo intervallo di date deve estendersi nel futuro. Ad esempio, se l'intervallo di date selezionato per il livello oro è per un periodo di un anno, tutti i clienti qualificati per il livello oro possono ricevere i premi assegnati al livello oro per un anno. Se il cliente viene riqualificato per il livello oro mentre si trova in tale livello, la data in cui lo stato del livello scade viene prorogata di un altro anno a partire dalla data di riqualificazione.  
10. Nell'elenco fare clic sul collegamento nella riga selezionata.
11. Fare clic su Aggiungi riga.
12. Nel campo Livello immettere un numero.
13. Nel campo Livello immettere il nome del livello del programma fedeltà.
14. Digitare un valore nel campo Descrizione.
15. Nel campo Intervallo date fare clic sul pulsante a discesa per aprire la ricerca.
16. Nell'elenco fare clic sul collegamento nella riga selezionata.
17. Fare clic su Salva.
18. Nell'elenco trovare e selezionare il record desiderato.
    * Le regole livello definiscono il numero minimo di punti premio che devono essere acquisiti durante un periodo per avere diritto al livello.  
19. Attivare l'espansione della sezione Regole livello.
20. Fare clic su Nuovo.
    * È possibile disporre di più regole livello per ogni livello. Ad esempio, si potrebbe disporre di tre criteri diversi per acquisire un livello, in base alla spesa di $500 in un mese, in base alla spesa di $1000 in un anno e in base all'esecuzione di 20 transazioni in un anno. A questo scopo, è necessario creare regole a tre livelli.  
21. Nel campo Punto premio fare clic sul pulsante a discesa per aprire la ricerca.
    * Questo punto premio fedeltà non deve essere riscattabile.  
22. Nell'elenco fare clic sul collegamento nella riga selezionata.
23. Nel campo Numero minimo punti emessi immettere un numero.
    * Per il livello più basso, se tutti i clienti possono avere diritto semplicemente partecipando al programma, immettere '0'.  
24. Nel campo Intervallo date di valutazione fare clic sul pulsante a discesa per aprire la ricerca.
    * Questo intervallo di date deve estendersi nel passato. Solo i punti ottenuti durante questo intervallo di date verranno conteggiati per il raggiungimento del valore minimo di punti emessi.  
25. Nell'elenco fare clic sul collegamento nella riga selezionata.
26. Fare clic su Salva.
27. Nell'elenco trovare e selezionare il record desiderato.
28. Fare clic su Nuovo.
29. Nel campo Punto premio fare clic sul pulsante a discesa per aprire la ricerca.
30. Nell'elenco fare clic sul collegamento nella riga selezionata.
31. Nel campo Numero minimo punti emessi immettere un numero.
32. Nel campo Intervallo date di valutazione fare clic sul pulsante a discesa per aprire la ricerca.
    * Questo intervallo di date deve estendersi nel passato.  
33. Nell'elenco fare clic sul collegamento nella riga selezionata.
34. Fare clic su Salva.
35. Fare clic su Gruppi di prezzi.
    * Se si desiderano offrire sconti ai clienti programma fedeltà, sarà necessario assegnare uno o più gruppi di prezzi al programma di fedeltà e assegnare i gruppi di prezzi agli sconti. È consigliabile non combinare gruppi di prezzi tra diversi tipi di entità di sconto.  Ad esempio, non utilizzare lo stesso gruppo di prezzi per uno sconto del programma fedeltà e uno sconto del canale.  
36. Nel campo Gruppo di prezzi fare clic sul pulsante a discesa per aprire la ricerca.
    * Il collegamento Gruppi di prezzi nella parte superiore della pagina è per il programma di fedeltà. Il collegamento Gruppi di prezzi nella scheda dettaglio Livelli programma è per un solo livello specifico del programma fedeltà.  
37. Nell'elenco fare clic sul collegamento nella riga selezionata.
38. Fare clic su Salva.
39. Chiudere la pagina.
40. Fare clic su Salva.



--- 
title: Pianificare i carichi e le spedizioni utilizzando il workbench di pianificazione del carico
description: Questa procedura illustra come utilizzare il workbench di pianificazione del carico per creare un carico per un ordine cliente.
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 982c746de1329be435d9047d4057cba100475b1b
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a>Pianificare i carichi e le spedizioni utilizzando il workbench di pianificazione del carico

[!include[task guide banner](../../includes/task-guide-banner.md)]

Questa procedura illustra come utilizzare il workbench di pianificazione del carico per creare un carico per un ordine cliente. Come prerequisito, è necessario creare prima l'ordine cliente. Questa procedura è parte delle attività giornaliere per il coordinatore dei trasporti. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.


## <a name="create-a-sales-order"></a>Crea un ordine cliente
1. Andare a Contabilità clienti > Ordini > Tutti gli ordini cliente.
2. Fare clic su Nuovo.
3. Nel campo Conto cliente fare clic sul pulsante a discesa per aprire la ricerca.
4. Selezionare il conto US-004.
5. Fare clic su OK.
6. Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.
7. Selezionare l'articolo A0001.
    * A0001 è abilitato per la gestione trasporto.  
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
9. Nel campo Quantità immettere un numero.
10. Nel campo Magazzino digitare "24".
    * In questo esempio selezionare il magazzino 24. Tale magazzino è abilitato per la gestione trasporto e la gestione avanzata del magazzino.  
11. Fare clic su Salva.
12. Chiudere la pagina.

## <a name="create-a-new-load"></a>Creare un nuovo carico
1. Andare a Gestione trasporto > Pianificazione > Workbench pianificazione carico.
2. Fare clic sulla scheda Righe di vendita.
    * Verrà creato il carico per l'ordine cliente creato. I carichi possono essere creati in base all'offerta e alla domanda da ordini fornitore, ordini di trasferimento e ordini cliente.  
3. Nel riquadro azioni fare clic su Domanda e offerta.
4. Fare clic su Al nuovo carico.
5. Nel campo ID modello carico fare clic sul pulsante a discesa per aprire la ricerca.
    * Il modello di carico definisce le misure massime per il peso e il volume dell'intero carico. Ad esempio, il modello di carico può rappresentare la dimensione di un container o di un camion.  
6. Nell'elenco fare clic sul collegamento nella riga selezionata.
7. Fare clic su OK.

## <a name="rate-and-route-the-load"></a>Assegnare una tariffa e un percorso al carico
1. Fare clic su Valutazione e distribuzione.
2. Fare clic su Tariffa workbench ciclo di lavorazione.
3. Fare clic su Strumento tariffe.
4. Nell'elenco trovare e selezionare il record desiderato.
5. Fare clic su Assegna.
6. Chiudere la pagina.
7. Chiudere la pagina.



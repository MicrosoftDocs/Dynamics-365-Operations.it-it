--- 
title: Associare un indice carburante a un vettore come spesa accessoria
description: Questa guida illustra creare un'assegnazione di spese accessorie, di spese accessorie per il vettore spedizione e di spese accessorie principali per il supplemento carburante e come associare un indice carburante a un vettore.
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a2b8534231c5fa50b1e0f709e09d318bb8202a43
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="associate-a-fuel-index-with-a-carrier-as-an-accessorial-charge"></a>Associare un indice carburante a un vettore come spesa accessoria

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa guida illustra creare un'assegnazione di spese accessorie, di spese accessorie per il vettore spedizione e di spese accessorie principali per il supplemento carburante e come associare un indice carburante a un vettore. Prima di eseguire questa guida. è necessario aver impostato un indice carburante vettore. A tale scopo, è possibile utilizzare la guida "Impostare un indice carburante vettore". Queste attività di impostazione in genere vengono effettuate da un responsabile della logistica. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.


## <a name="create-an-accessorial-master"></a>Creare spese accessorie principali
1. Andare a Gestione trasporto > Impostazioni > Valutazione > Rappresentazioni generali accessorie.
2. Fare clic su Nuovo.
3. Nel campo Spese accessorie principali digitare un valore.
4. Digitare un valore nel campo Nome.
5. Fare clic su Salva.

## <a name="create-a-carrier-accessorial-charge"></a>Creare spese accessorie vettore
1. Andare a Gestione trasporto > Impostazioni > Valutazione > Spese accessorie vettore.
2. Fare clic su Nuovo.
3. Nel campo ID spese accessorie vettore digitare un valore.
4. Nel campo Vettore spedizione fare clic sul pulsante a discesa per aprire la ricerca.
5. Nell'elenco trovare e selezionare il record desiderato.
    * In questo esempio scegliere Truck Carrier.  
6. Nell'elenco fare clic sul collegamento nella riga selezionata.
7. Nel campo Servizio trasporto fare clic sul pulsante a discesa per aprire la ricerca.
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
9. Nel campo Spese accessorie principali fare clic sul pulsante a discesa per aprire la ricerca.
10. Nell'elenco trovare e selezionare il record desiderato.
    * In questo esempio scegliere le spese accessorie principali create.  
11. Fare clic su Salva.

## <a name="create-an-accessorial-assignment"></a>Creare un'assegnazione di spese accessorie
1. Fare clic su Assegnazioni spese accessorie.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome.
4. Attivare/disattivare l'espansione della sezione Criteri.
    * Nei criteri è possibile scegliere di applicare sempre il supplemento carburante, anche se per questo esempio è possibile scegliere di applica solo all'interno di un paese specifico.  
5. Digitare un valore nel campo Da codice postale (CAP).
6. Digitare un valore nel campo A codice postale (CAP).
7. Attivare/disattivare l'espansione della sezione Calcolo.
    * Nella sezione di calcolo è possibile specificare la modalità di calcolo del supplemento carburante. Questo calcolo dipende dall'unità di spese accessorie scelta come base per il calcolo.  
8. Nel campo per il tipo di commissioni per le spese accessorie selezionare "Supplemento carburante".
9. Nel campo Unità di spese accessorie selezionare "Chilometraggio".
10. Nel campo Paese fare clic sul pulsante a discesa per aprire la ricerca.
11. Nell'elenco fare clic sul collegamento nella riga selezionata.
12. Fare clic su Salva.

## <a name="update-the-carrier-rating-profile"></a>Aggiornare il profilo di valutazione vettore
1. Andare a Gestione trasporto > Impostazioni > Vettori > Vettori spedizione.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Attivare/disattivare l'espansione della sezione Profili valutazione.
4. Fare clic su Modifica.
5. Nel campo Indice carburante vettore fare clic sul pulsante a discesa per aprire la ricerca.
6. Nell'elenco fare clic sul collegamento nella riga selezionata.
7. Fare clic su Salva.



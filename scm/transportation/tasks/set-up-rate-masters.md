--- 
title: Impostare i dati master tariffe
description: Questa procedura mostra come impostare dati master tariffe.
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
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 263c912594dcf61985094dab30eab8f72cd731e9
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="set-up-rate-masters"></a>Impostare i dati master tariffe

[!include[task guide banner](../../includes/task-guide-banner.md)]

Questa procedura mostra come impostare dati master tariffe. Il responsabile della logistica in genere imposta i dati master tariffe, a seconda dei contratti firmati con i vettori. In questo scenario verranno impostati dati master per una compagnia aerea. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.


## <a name="set-up-rate-master"></a>Impostare dati master tariffe
1. Passare a Gestione trasporto > Impostazioni > Valutazione > Tariffa principale.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Tariffa principale.
4. Digitare un valore nel campo Nome.
5. Nel campo dell'ID di valutazione dei metadati fare clic sul pulsante a discesa per aprire la ricerca.
    * L'ID dei metadati di valutazione determinerà i dati necessari per i dati master tariffe, perché definisce i metadati previsti dal motore TMS che utilizza tali dati master.  
6. Per questo esempio, selezionare l'opzione P2P
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Fare clic su Salva.

## <a name="set-up-rate-base"></a>Impostare una base tariffa
1. Fare clic su Base tariffa.
    * La base della tariffa determina la tariffa del vettore e può essere utilizzata per impostare una struttura tariffaria perché organizza le tariffe in punti di interruzione definiti nei dati master di interruzione.  
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Base tariffa.
4. Digitare un valore nel campo Nome.
5. Nel campo Interruzione principale fare clic sul pulsante a discesa per aprire la ricerca.
    * I dati master di interruzione vengono utilizzati per definire la struttura dei prezzi e i relativi punti di interruzione. La struttura dei prezzi utilizza livelli di prezzo basati su dimensioni fisiche.  
6. Per questo esempio, utilizzare il peso
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Attivare/disattivare l'espansione della sezione Dettagli.
9. Fare clic su Nuovo.
10. Nel campo CAP consegna da digitare "30301".
11. Nel campo CAP consegna A digitare "30318".
12. Nel campo Paese consegna digitare "USA".
13. Nel campo <1,00 kg, digitare '100'.
    * Inserire la tariffa per chilogrammi se il peso totale del carico è inferiore a 1 chilogrammo.  
14. Nel campo <5,00 kg digitare "300".
    * Inserire la tariffa per chilogrammi se il peso totale del carico è inferiore a 5 chilogrammi.  
15. Nel campo <20,00 kg digitare "500".
    * Inserire la tariffa per chilogrammi se il peso totale del carico è inferiore a 20 chilogrammi.  
16. Nel campo <100,00 kg digitare "1000".
    * Inserire la tariffa per chilogrammi se il peso totale del carico è inferiore a 100 chilogrammi.  
17. Nel campo <1.000,00 kg digitare "3000".
    * Inserire la tariffa per chilogrammi se il peso totale del carico è inferiore a 1000 chilogrammi.  
18. Fare clic su Salva.
19. Chiudere la pagina.

## <a name="assign-rate-base"></a>Assegnare una base tariffa
1. Attivare/disattivare l'espansione della sezione Assegnazioni base tariffa.
2. Fare clic su Nuovo.
    * È possibile includere più assegnazioni di base della tariffa per ogni dato master tariffa. Ciò consente di creare prezzi diversi per ogni vettore a seconda delle destinazioni, dei servizi e delle diverse basi di tariffa. In questa procedura verrà creata solo un'assegnazione di base della tariffa.  
3. Digitare un valore nel campo Nome.
4. Nel campo Base tariffa fare clic sul pulsante a discesa per aprire la ricerca.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Nel campo Servizio fare clic sul pulsante a discesa per aprire la ricerca.
7. Trovare e selezionare il record desiderato nell'elenco.
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
9. Nel campo CAP prelievo digitare "98052".
    * Specificare il codice postale da cui questa assegnazione di base della tariffa deve essere valida.    
10. Nel campo Paese prelievo digitare "USA".
11. Fare clic su Salva.



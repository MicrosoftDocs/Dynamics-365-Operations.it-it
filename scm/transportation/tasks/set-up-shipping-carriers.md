--- 
title: Impostare vettori di spedizione
description: "Questa procedura descrive come impostare un vettore di spedizione e come definire dettagli quali servizio, modalità di spedizione, metodo di pagamento del trasporto, vincoli di trasporto e tariffa di trasporto."
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
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: eec121859b7135741ccf204fd507ef0790f1c8d4
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="set-up-shipping-carriers"></a>Impostare vettori di spedizione

[!include[task guide banner](../../includes/task-guide-banner.md)]

Questa procedura descrive come impostare un vettore di spedizione e come definire dettagli quali servizio, modalità di spedizione, metodo di pagamento del trasporto, vincoli di trasporto e tariffa di trasporto. Un coordinatore dei trasporti può quindi assegnare un vettore di spedizione a un carico in entrata o in uscita.


## <a name="create-a-new-shipping-carrier"></a>Creare un nuovo vettore di spedizione
1. Andare a Gestione trasporto > Impostazioni > Vettori > Vettori spedizione.
2. Fare clic su Nuovo.
3. Nel campo Vettore spedizione digitare un valore.
4. Digitare un valore nel campo Nome.
5. Nel campo Modalità fare clic sul pulsante a discesa per aprire la ricerca.
6. Nell'elenco trovare e selezionare il record desiderato.
7. Nell'elenco fare clic sul collegamento nella riga selezionata.

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a>Inserire le informazioni generali per il vettore di spedizione
1. Attivare/disattivare l'espansione della sezione Panoramica.
2. Selezionare o deselezionare la casella di controllo Attiva vettore di spedizione.
3. Nel campo Fornitore fare clic sul pulsante a discesa per aprire la ricerca.
    * Selezionare il conto fornitore a cui assegnare il vettore di spedizione.  
4. Nell'elenco trovare e selezionare il record desiderato.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Nel campo Tipo di pagamento trasporto selezionare un'opzione.
    * Selezionare Manuale per utilizzare la pagina Metodo di pagamento trasporto o selezionare EDI per aggiornare il metodo di pagamento utilizzando il formato EDI (Electronic Data Interchange).  
7. Selezionare o deselezionare la casella di controllo Attiva valutazione vettore.

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a>Creare i servizi necessari per il vettore di spedizione
1. Attivare/disattivare l'espansione della sezione Servizi.
2. Fare clic su Nuovo.
3. Nell'elenco contrassegnare la riga selezionata.
4. Nel campo Servizio trasporto digitare un valore.
5. Digitare un valore nel campo Nome.
6. Nel campo Metodo di trasporto fare clic sul pulsante a discesa per aprire la ricerca.
7. Nell'elenco trovare e selezionare il record desiderato.
8. Nell'elenco fare clic sul collegamento nella riga selezionata.

## <a name="set-up-the-address-for-the-carrier-optional"></a>Impostare l'indirizzo del vettore (facoltativo)
1. Attiva/disattiva l'espansione della sezione Indirizzi.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome o Descrizione.
4. Nel campo Paese fare clic sul pulsante a discesa per aprire la ricerca.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Nel campo Codice postale (CAP) fare clic sul pulsante a discesa per aprire la ricerca.
7. Trovare e selezionare il record desiderato nell'elenco.
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
9. Digitare un valore nel campo Via.
10. Fare clic su OK.

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a>Impostare il profilo di valutazione per il vettore di spedizione
1. Attivare/disattivare l'espansione della sezione Profili valutazione.
2. Fare clic su Nuovo.
3. Nell'elenco contrassegnare la riga selezionata.
4. Nel campo Profilo valutazione digitare un valore.
5. Digitare un valore nel campo Nome.
6. Nel campo Sito fare clic sul pulsante a discesa per aprire la ricerca.
7. Trovare e selezionare il record desiderato nell'elenco.
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
9. Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.
10. Trovare e selezionare il record desiderato nell'elenco.
11. Nell'elenco fare clic sul collegamento nella riga selezionata.
12. Nel campo Motore tariffe fare clic sul pulsante a discesa per aprire la ricerca.
    * Selezionare il motore tariffe in base al contratto stipulato con il vettore.  
13. Nell'elenco trovare e selezionare il record desiderato.
14. Nell'elenco fare clic sul collegamento nella riga selezionata.
15. Nel campo Tariffa principale fare clic sul pulsante a discesa per aprire la ricerca.
16. Trovare e selezionare il record desiderato nell'elenco.
17. Nell'elenco fare clic sul collegamento nella riga selezionata.
18. Nel campo Motore tempo di transito fare clic sul pulsante a discesa per aprire la ricerca.
19. Nell'elenco fare clic sul collegamento nella riga selezionata.
20. Fare clic su Salva.



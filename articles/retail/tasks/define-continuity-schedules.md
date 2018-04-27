--- 
title: " Definire programmazioni di continuità"
description: "In questo argomento si descrive l'impostazione di un programma di continuità (altrimenti detto ordini ricorrenti)."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 5ac333989dd987fd3cb1d2b2769fbcdb93bdb4bd
ms.contentlocale: it-it
ms.lasthandoff: 02/07/2018

---
# <a name="define-continuity-schedules"></a> Definire programmazioni di continuità

[!INCLUDE [task guide banner](../includes/task-guide-banner.md)]

In questo argomento si descrive l'impostazione di un programma di continuità (altrimenti detto ordini ricorrenti). Questo argomento utilizza la società USRT nei dati dimostrativi.


## <a name="create-continuity-program"></a>Creare un programma di continuità
1. Passare a Vendita al dettaglio e commercio > Continuità > Programmi di continuità.
2. Fare clic su Nuovo.
3. Nel campo ID programmazione, digitare l'ID programmazione di continuità.
4. Nel campo Inizio ordine selezionare 'Primo evento'.
    * Se un cliente effettua un nuovo ordine per il programma di continuità, sono disponibili due opzioni per cui il prodotto verrà spedito:  1 Primo evento: il primo prodotto nel programma di continuità verrà spedito.  2 Evento esistente: il prodotto corrente verrà spedito. Ad esempio, tre mesi nel programma, il cliente riceverà il terzo nel programma.  
5. Selezionare 'Sì' per richiedere la data di inizio dell'ordine.
6. Fare clic su Aggiungi riga.
7. Nel campo Numero articolo digitare il numero di articolo per il primo prodotto ('0013').
8. Digitare 'CP'.
9. Immettere la data in cui il primo prodotto sarà disponibile per l'ordine.
10. Fare clic su Aggiungi riga.
11. Nel campo Numero articolo digitare '0014'.
12. Nel campo Codice intervallo date, cancellare il valore in modo che il campo è vuoto.
    * Per questa procedura, deselezionare l'intervallo di date. Fisserete la data come incrementale dalla data di inizio del primo articolo.  
13. Qui immettere l'intervallo a cui i prodotti sono spediti. Digitare '30'.
    * Per un programma mensile, immettere 30 giorni per l'intervallo.  
14. Fare clic su Aggiungi riga.
15. Nel campo Numero articolo digitare '0015'.
16. Digitare 'Fine'.
17. Fare clic su Salva.

## <a name="assign-to-continuity-item"></a>Assegnare all'articolo di continuità
1. Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.
2. Selezionare l'articolo '0016'.
    * Per questa procedura, selezionerete il numero di articolo 0016. In genere, si sarà creato un prodotto rilasciato a cui è applicata la logica di business di continuità aggiuntiva quando viene inserito in un ordine cliente nel servizio clienti.  
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Fare clic su Modifica.
5. Espandere o comprimere la sezione Vendi.
6. Qui immettere il programma di continuità che l'articolo rappresenta. Immettere l'ID programmazione creato in precedenza.
    * Quando l'articolo viene venduto da un servizio clienti, la logica di business aggiuntiva viene applicata dal programma di continuità selezionato.  
7. Fare clic su Salva.



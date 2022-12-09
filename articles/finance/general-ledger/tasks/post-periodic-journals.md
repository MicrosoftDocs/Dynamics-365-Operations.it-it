---
title: Registrare giornali periodici
description: I giornali di registrazione periodici vengono talvolta denominati giornali ricorrenti poiché l'importo, il testo e altre informazioni vengono ripetuti ogni volta che il giornale di registrazione periodico viene recuperato.
author: aprilolson
ms.date: 11/21/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransPeriodic, LedgerJournalTransDaily
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bdc1d9f67a515e3cdc45e173b88982feceb0ebfd
ms.sourcegitcommit: fb9b6969218f2b82f0a4c72bfad75387fe00395c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2022
ms.locfileid: "9799388"
---
# <a name="post-periodic-journals"></a>Registrare giornali periodici

[!include [banner](../../includes/banner.md)]

I giornali di registrazione periodici vengono talvolta denominati giornali ricorrenti poiché l'importo, il testo e altre informazioni vengono ripetuti ogni volta che il giornale di registrazione periodico viene recuperato. Quando si crea il giornale di registrazione periodico si specifica l'intervallo periodico per la ricorrenza, ad esempio giorni o mesi. Questa guida attività consentirà di creare un giornale di registrazione periodico con una ricorrenza mensile.

1. Andare al **pannello di navigazione > Moduli > Contabilità generale > Attività periodiche > Giornali di registrazione periodici**.
2. Fare clic su **Nuovo**.
3. Nel campo **Nome** immettere o selezionare un valore.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Digitare un valore nel campo **Descrizione** La descrizione consisterà nel nome del giornale di registrazione periodico quando viene recuperato in un momento successivo, quindi assicurarsi di scegliere un nome pertinente.
6. Nel **riquadro azioni** fare clic su **Righe**. Un giornale di registrazione periodico in genere includerà più righe giornale di registrazione. Questa guida attività tuttavia consentirà di aggiungere una sola riga.
7. Nel campo **Data** immettere una data. Il campo **Data** contiene la data di registrazione per il successivo trasferimento nel giornale di registrazione giornaliero. Per i giornali di registrazione che verranno recuperati ogni mese si consiglia di utilizzare la data del mese in cui verranno registrati. Si tratta in genere della prima o dell'ultima data del periodo. Usando il campo **Data vuota**, è possibile lasciare vuoto il campo **Data** e immettere una data in cui il giornale di registrazione viene recuperato. Il campo verrà aggiornato alla data ricorrente successiva in cui le transazioni vengono recuperate. 
8. Nel campo **Conto**, specificare i valori desiderati.
9. Nel campo **Descrizione** selezionare un valore.
10. Chiudere la pagina.
11. Nel campo **Dare** immettere un numero.
12. Nel campo **Conto di contropartita**, specificare i valori desiderati.
13. Nel campo **Unità** selezionare **Mesi**.
14. Nel campo **Numero di unità** immetti **1**.
15. Nel campo **Ultima data** immettere una data. L'immissione dell'ultima data nel periodo precedente impedirà che il giornale di registrazione ricorrente venga per errore creato nel periodo iniziale sbagliato. L'ultima data verrà successivamente aggiornata ogni volta che il giornale di registrazione periodico viene recuperato. 
16. Fare clic su **Salva**.
17. Andare a **Pannello di navigazione > Moduli > Contabilità generale > Inserimenti nel giornale di registrazione > Giornali di registrazione generali**.
18. Fare clic su **Nuovo**.
19. Nel campo **Nome** immettere o selezionare un valore.
20. Nell'elenco trovare e selezionare il record desiderato.
21. Nell'elenco fare clic sul collegamento nella riga selezionata.
22. Digitare un valore nel campo **Descrizione**
23. Nel **riquadro azioni** fare clic su **Righe**.
24. Nel **Riquadro azioni** fare clic su **Giornale di registrazione periodico**.
25. Fare clic su **Recupera giornale di registrazione**.
26. Nel campo **Al** immettere una data. La **data finale** funge da data limite per le righe periodiche di giustificativo. In base all'impostazione della ricorrenza, **Ultima data** e **Data finale**, la stessa riga può essere inclusa più volte nel giornale di registrazione risultante. La **Data finale** viene automaticamente aggiornata in base alla data della sessione in cui è stato effettuato l'ultimo trasferimento della riga del giornale di registrazione periodico in un giornale di registrazione. 
27. Nel campo **Numero giornale di registrazione periodico** immettere o selezionare un valore.
28. Nell'elenco fare clic sul collegamento nella riga selezionata.
29. Fare clic su **OK**. Il giornale di registrazione periodico può ora essere rivisto, approvato o registrato a seconda del fabbisogno e dell'impostazione.   


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

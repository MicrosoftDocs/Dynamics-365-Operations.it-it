--- 
title: Registrare giornali periodici
description: "I giornali di registrazione periodici vengono talvolta denominati giornali ricorrenti poiché l'importo, il testo e altre informazioni vengono ripetuti ogni volta che il giornale di registrazione periodico viene recuperato."
author: aprilolson
manager: AnnBe
ms.date: 02/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 8eae11e0501db78e467e517b29a2bc19f5765e75
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="post-periodic-journals"></a>Registrare giornali periodici

[!include [task guide banner](../../includes/task-guide-banner.md)]

I giornali di registrazione periodici vengono talvolta denominati giornali ricorrenti poiché l'importo, il testo e altre informazioni vengono ripetuti ogni volta che il giornale di registrazione periodico viene recuperato. Quando si crea il giornale di registrazione periodico si specifica l'intervallo periodico per la ricorrenza, ad esempio giorni o mesi. Questa guida attività consentirà di creare un giornale di registrazione periodico con una ricorrenza mensile.



1. Fare clic su Contabilità generale > Attività periodiche > Giornali di registrazione periodici.
2. Fare clic su Nuovo.
3. Nel campo Nome immettere o selezionare un valore.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Nel campo Descrizione digitare un valore.
    * La descrizione consisterà nel nome del giornale di registrazione periodico quando viene recuperato in un momento successivo, quindi assicurarsi di scegliere un nome pertinente.  
6. Fare clic su Righe.
    * Un giornale di registrazione periodico in genere includerà più righe giornale di registrazione. questa guida attività tuttavia consentirà di aggiungere una sola riga.  
7. Nel campo Data immettere una data.
    * Il campo Data contiene la data di registrazione per il successivo trasferimento nel giornale di registrazione giornaliero. Per i giornali di registrazione che verranno recuperati ogni mese si consiglia di utilizzare la data del mese in cui verranno registrati, in genere la prima o l'ultima data del periodo. È possibile lasciare vuoto il campo Data e immettere una data in cui il giornale di registrazione viene recuperato, utilizzando il campo data Vuoto.    Il campo viene aggiornato automaticamente alla data ricorrente successiva in cui le transazioni vengono recuperate.  
8. Nel campo Conto, specificare i valori desiderati.
9. Nel campo Descrizione digitare un valore.
10. Chiudere la pagina.
11. Nel campo Dare immettere un numero.
12. Nel campo Conto di contropartita, specificare i valori desiderati.
13. Nel campo Unità selezionare "Mesi".
14. Nel campo Numero di unità immettere "1".
15. Nel campo Ultima data immettere una data.
    * L'immissione dell'ultima data nel periodo precedente impedirà che il giornale di registrazione ricorrente venga per errore creato nel periodo iniziale sbagliato. L'ultima data verrà successivamente aggiornata ogni volta che il giornale di registrazione periodico viene recuperato.  
16. Fare clic su Salva.
17. Fare clic su Dashboard predefinito.
18. Fare clic su Contabilità generale > Scritture contabili > Giornali di registrazione generali.
19. Fare clic su Nuovo.
20. Nel campo Nome immettere o selezionare un valore.
21. Nell'elenco trovare e selezionare il record desiderato.
22. Nell'elenco fare clic sul collegamento nella riga selezionata.
23. Nel campo Descrizione digitare un valore.
24. Fare clic su Righe.
25. Fare clic su Giornale di registrazione periodico.
26. Fare clic su Recupera giornale di registrazione.
27. Nel campo Data finale immettere una data.
    * La data finale funge da data limite per le righe periodiche di giustificativo. In base all'impostazione della ricorrenza, l'ultima data e la data finale, la stessa riga può essere inclusa più volte nel giornale di registrazione risultante. La data finale viene automaticamente aggiornata in base alla data della sessione in cui è stato effettuato l'ultimo trasferimento della riga del giornale di registrazione periodico in un giornale di registrazione.  
28. Nel campo Numero giornale di registrazione periodico immettere o selezionare un valore.
29. Nell'elenco fare clic sul collegamento nella riga selezionata.
30. Fare clic su OK.
    * Il giornale di registrazione periodico può ora essere rivisto, approvato o registrato a seconda del fabbisogno e dell'impostazione.  



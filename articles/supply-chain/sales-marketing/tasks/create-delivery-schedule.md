---
title: Creare una programmazione consegna
description: Questa procedura dimostra come creare una programmazione consegna per un ordine cliente.
author: omulvad
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesDeliverySchedule, SalesEditLines,  SrsReportViewerForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 79fa41df07bc09f24e31900a52f4905db6d1c63e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836424"
---
# <a name="create-delivery-schedule"></a>Creare una programmazione consegna

[!include [banner](../../includes/banner.md)]

Questa procedura dimostra come creare una programmazione consegna per un ordine cliente. Una programmazione consegna viene utilizzata quando si richiede che una quantità di un ordine o di un'offerta venga consegnata in più spedizioni. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.


## <a name="create-delivery-schedule"></a>Creare una programmazione consegna
1. Fare clic su Tutti gli ordini cliente.
2. Fare clic su Nuovo.
3. Nel campo Conto cliente, immettere o selezionare un valore.
4. Fare clic su OK.
5. Nel campo Numero di articoli immettere o selezionare un valore.
6. Nel campo Quantità, immettere un numero maggiore di 1.
7. Fare clic su Riga ordine cliente.
8. Fare clic su Programmazione consegna.
    * La pagina Programmazione consegna è il luogo in cui è possibile specificare il numero di spedizioni in cui la quantità totale della riga ordine verrà consegnata al cliente.    
    * Per impostazione predefinita, il sistema copia la quantità totale e altri dettagli di consegna della riga di vendita originale nella prima riga di programmazione consegna. In questo esempio creeremo una programmazione per due spedizioni, con uno scostamento della data della seconda spedizione di una settimana rispetto alla prima.  
9. Nel campo Quantità, immettere un numero appartenente alla quantità totale.
10. Fare clic su Nuovo.
11. Nel campo Quantità immettere la quantità rimanente.
12. Nel campo Data di spedizione richiesta, immettere una data che sia una settimana dopo a partire dalla data della prima riga di consegna.
    * Le due opzioni della Scheda dettaglio Conversione spese controllano la modalità di distribuzione delle spese tra le righe di programmazione consegna, una volta assegnate alla riga ordine originale. Se si seleziona Copia importi lordi, lo stesso importo di spesa viene copiato in ciascuna riga. L'opzione Assegna a righe consegna divide equamente la spesa tra le righe consegna.  
    * Solo le spese fisse possono essere divise, mentre quelle variabili vengono sempre copiate nelle righe.  
13. Spostare il cursore lontano dalla seconda riga di consegna per aggiornare la pagina.
    * È possibile tenere traccia della quantità totale che viene allocata alle righe di programmazione consegna guardando i campi Totale e Rimanente. Se la quantità rimanente da zero, la quantità totale della riga originale è stata allocata alla programmazione.   
14. Fare clic su OK.
    * La programmazione consegna ora è stata copiata nelle righe ordine.   
    * La riga ordine originale, denominata riga commerciale, è stata convertita in riga ordine con più consegne. È contrassegnata con un'icona distinta e funge da intestazione delle righe consegna.  
    * Le due nuove righe, denominate righe consegna, costituiscono una programmazione consegna. L'ordine verrà elaborato rispetto a queste righe e non alla riga originale. Se i documenti ad esempio i documenti di conferma, le distinte di prelievo, i documenti di trasporto o le fatture vengono stampati, verranno visualizzate solo le righe consegna.   
    * Le righe consegna possono avere date di consegna, quantità, modalità di consegna e dimensioni di immagazzinamento diverse, ad esempio sito e magazzino. Tuttavia, le dimensioni prodotto devono corrispondere sempre a quelle nella riga commerciale e non possono essere modificate.  
15. Nel campo Quantità, immettere un numero maggiore di quello corrente.
16. Selezionare la riga commerciale per visualizzare l'effetto del ricalcolo della quantità.
17. Nel riquadro azioni fare clic su Preleva e imballa.
18. Fare clic su Registra documento di trasporto.
19. Espandere la sezione Parametri.
20. Nel campo Quantità selezionare "Tutto".
    * Si noti che il documento di trasporto verrà creato per le due righe di programmazione consegna e non per la riga ordine originale.  
21. Selezionare Sì nel campo Stampa documento di trasporto.
22. Fare clic su OK.
23. Fare clic su Sì.
24. Chiudere la pagina.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
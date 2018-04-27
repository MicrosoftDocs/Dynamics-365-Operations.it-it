--- 
title: Definire le regole di copertura per gli articoli
description: "La società di dati dimostrativi utilizzata per creare questa procedura è USMF."
author: YuyuScheller
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 76334f7ee4efe33df4a86aaa11a59748387cec89
ms.openlocfilehash: fe92393cc264df68f084db6974f7d4607d37d3ab
ms.contentlocale: it-it
ms.lasthandoff: 11/02/2017

---
# <a name="define-coverage-rules-for-items"></a>Definire le regole di copertura per gli articoli

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Questa procedura mostra come creare le regole di copertura e ignorare le impostazioni di copertura per un articolo specifico. Viene inoltre illustrato come specificare le impostazioni predefinite di magazzino.


## <a name="create-a-coverage-group"></a>Creare un gruppo di copertura
1. Fare clic su Gruppi di copertura
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Gruppo di copertura.
4. Digitare un valore nel campo Nome.
5. Digitare un valore nel campo Calendario.
    * Selezionare il calendario utilizzato dalla pianificazione generale per creare i suggerimenti di rifornimento per gli articoli inclusi nel gruppo.  
6. Nel campo Codice copertura selezionare un'opzione.
    * Selezionare Fabbisogno per questa procedura.  
7. Nel campo Intervallo temporale di copertura (giorni) immettere "90".
    * Per gli articoli inclusi nel gruppo, la pianificazione generale creerà i suggerimenti di rifornimento per i fino a 90 giorni nel futuro.  
8. Nel campo Giorni negativi immettere "1".
9. Nel campo Giorni positività immettere "1".
10. Espandere o comprimere la sezione Altro.
11. Nel campo Margine su entrata in magazzino aggiunto dalla data del fabbisogno immettere "1".
    * Ad esempio, se il margine sull'entrata in magazzino è impostato su 1 giorno e una riga ordine fornitore è programmata per l'entrata il 15 maggio, la programmazione generale calcola come data di entrata rettificata il giorno 16 maggio.  
12. Nel campo Margine su uscita da magazzino detratto dalla data del fabbisogno immettere "1".
    * Ad esempio, se il margine di sicurezza è impostato su 1 giorno e una riga ordine cliente è programmata per la consegna il 15 maggio, la programmazione generale calcola come data rettificata il giorno 14 maggio.  
13. Nel campo Margine di riordino aggiunto al lead time dell'articolo immettere "1".
14. Fare clic su Salva.

## <a name="create-a-new-product"></a>Crea un nuovo prodotto
1. Fare clic su Prodotti rilasciati.
2. Fare clic su Nuovo.
3. Nel campo Numero prodotto, digitare un valore.
4. Digitare un valore nel campo Nome prodotto.
5. Nel campo Gruppo di modelli di articoli fare clic sul pulsante a discesa per aprire la ricerca.
6. Trovare e selezionare il record desiderato nell'elenco.
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Nel campo Gruppo di articoli fare clic sul pulsante a discesa per aprire la ricerca.
9. Trovare e selezionare il record desiderato nell'elenco.
10. Nell'elenco fare clic sul collegamento nella riga selezionata.
11. Nel campo Gruppo di dimensioni di immagazzinamento fare clic sul pulsante a discesa per aprire la ricerca.
12. Trovare e selezionare il record desiderato nell'elenco.
13. Nell'elenco fare clic sul collegamento nella riga selezionata.
14. Nel campo Gruppo di dimensioni di tracciabilità fare clic sul pulsante a discesa per aprire la ricerca.
15. Nell'elenco trovare e selezionare il record desiderato.
16. Nell'elenco fare clic sul collegamento nella riga selezionata.
17. Fare clic su OK.

## <a name="setup-default-order-settings"></a>Configura impostazioni ordine predefinite
1. Nel riquadro azioni fare clic su Piano.
2. Fare clic su Impostazioni ordine predefinite.
3. Nel campo Sito acquisto, immettere il sito utilizzato come valore predefinito quando vengono creati gli ordini fornitore.
4. Nel campo Sito magazzino immettere il sito in cui è immagazzinato l'articolo.
5. Espandere o comprimere la sezione Inventario.
6. Imposta Multiplo su "10".
7. Impostare la quantità ordine minima su "10".
8. Impostare quantità ordine ordine minima massima su "100".
9. Imposta la quantità ordine standard su "10".
10. Nel campo Lead time acquisto immettere un numero.
11. Selezionare o deselezionare la casella di controllo Giorni lavorativi.
12. Fare clic su Salva.
13. Nel campo Tipo di ordine predefinito selezionare "Ordine acquisto".
14. Fare clic su Salva.
15. Chiudere la pagina.
    * Chiudere la pagina Impostazioni ordine predefinite.  

## <a name="add-an-item-to-a-coverage-group"></a>Aggiunge un articolo a un gruppo di copertura
1. Espandere o comprimere la sezione Piano.
2. Nel campo Gruppo di copertura fare clic sul pulsante a discesa per aprire la ricerca.
3. Nell'elenco, individuare il gruppo di copertura creato.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.

## <a name="create-item-coverage-rules"></a>Crea le regole copertura articoli
1. Nel riquadro azioni fare clic su Piano.
2. Fare clic su Copertura articoli.
3. Fare clic su Nuovo.
4. Fare clic sulla scheda Generale.
5. Selezionare la casella nell'intestazione di Ignora impostazioni gruppo di copertura.
6. Nel campo Intervallo temporale di copertura (giorni) immettere "60".
    * Anche se gli articoli nel gruppo di copertura Fabbisogno sono pianificati 90 giorni in anticipo, l'articolo verrà pianificato 60 giorni in anticipo.  
7. Nel campo Giorni negativi immettere "2".
8. Nel campo Giorni positività immettere "2".
9. Fare clic sulla scheda Lead time.
10. Selezionare la casella sull'intestazione di Acquisto.
11. Nel campo Ora dell'acquisto immettere "5".
12. Fare clic su Salva.



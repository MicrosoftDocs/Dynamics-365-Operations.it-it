--- 
title: Creare e modificare offerte di vendita
description: Questa procedura dimostra come creare e aggiornare un'offerta di vendita.
author: omulvad
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 8e7d2198b4976a6f60f05690d7b6f11f3da55e28
ms.openlocfilehash: 7ffa4fe8d87db5b3f8293ec9dbc042496d09d6e3
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---
# <a name="create-and-edit-sales-quotations"></a>Creare e modificare offerte di vendita

[!include[task guide banner](../../includes/task-guide-banner.md)]

Questa procedura dimostra come creare e aggiornare un'offerta di vendita. È possibile eseguire questa procedura sui propri dati o nella società di dati dimostrativi USMF.


## <a name="create-a-sales-quotation"></a>Creare un'offerta di vendita
1. Passare a Vendite e marketing > Offerte di vendita > Tutte le offerte.
2. Fare clic su Nuovo.
3. Nel campo Tipo di conto selezionare 'Prospect'.
4. Nel campo Prospect immettere o selezionare un valore.
5. Espandere la sezione Generale.
    * Poiché è stato scelto di creare un'offerta dall'area Vendita e marketing, il tipo viene automaticamente impostato su Offerta di vendita. Per creare un'offerta per un progetto è necessario accedervi dal modulo Gestione progetti e contabilità.   
6. Fare clic su OK.
    * I campi e le azioni sulle righe dell'offerta sono simili a quelli delle righe ordine cliente.   Analogamente agli ordini cliente, le offerte possono essere create per un articolo specifico o, se il numero articolo non è definito o non esiste al momento della creazione dell'offerta, le offerte possono essere create per una categoria di vendita.  
7. Nel campo Articolo immettere o selezionare un valore.
8. Digitare un valore nel campo Articolo.
9. Chiudere la pagina.
10. Nel campo Quantità immettere un numero.
    * Se sono presenti contratti commerciali validi per l'articolo selezionato nella riga, il prezzo e gli sconti applicabili verranno automaticamente copiati nella riga dell'offerta. Verificare che il campo Prezzo unitario contenga un valore ed è possibile immettere i valori di sconto se desiderato.  
11. Fare clic su Salva.
12. Nel riquadro azioni fare clic su Offerta di vendita.
13. Fare clic su Totali.
14. Fare clic su OK.
15. Fare clic su Riga offerta di vendita.
16. Fare clic su Prezzi.
    * Nella pagina Esegui simulazione prezzo è possibile sperimentare la rettifica dei ricavi o della redditività previsti per l'offerta in base al prezzo unitario, l'importo di sconto, la percentuale di sconto, l'importo totale, il margine o il rapporto di contribuzione desiderato.   Al termine, applicare il suggerimento alla riga dell'offerta e i campi relativi al prezzo verranno aggiornati di conseguenza.  
    * È possibile creare qualsiasi numero di simulazioni di prezzo. Quando si fa clic su Nuovo, i termini del prezzo dalla riga offerta corrente vengono copiati nella pagina. È quindi possibile modificare i valori dei campi relativi al prezzo impostando quelli di destinazione. Una modifica in uno dei campi avvierà il ricalcolo in tutti gli altri campi. Affinché il sistema calcoli il margine di vendita e il rapporto di contribuzione, il costo unitario del prodotto deve essere noto. Utilizzare la scheda Prezzi simulati per una visualizzazione dettagliata dei prezzi originali, le modifiche proposte e i relativi effetti nei totali dell'offerta.   In genere, quando una simulazione che imposta un nuovo importo viene applicata alla riga offerta, il sistema ricalcola e immette un nuovo valore nel campo Prezzo unitario. Se la simulazione si basa su un nuovo margine o un nuovo rapporto di contribuzione, solo il campo Importo netto viene aggiornato e il campo Prezzo unitario risulterà vuoto. In entrambi i casi, gli eventuali sconti inclusi nella riga dell'offerta prima della simulazione vengono eliminati.  
17. Chiudere la pagina.
18. Nel riquadro azioni fare clic su Offerta.
19. Fare clic su Invia offerta.
20. Selezionare Sì nel campo Stampa offerta.
21. Fare clic su OK.
    * La generazione del report può richiedere un minuto. Non chiudere la pagina finché non termina l'operazione.  
22. Chiudere la pagina.

## <a name="update-a-sales-quotation"></a>Aggiornare un'offerta di vendita
1. Nel riquadro azioni fare clic su Follow-up.
2. Fare clic su Converti in cliente.
3. Digitare un valore nel campo Conto cliente.
4. Fare clic su Verifica.
    * Verificare che venga visualizzato un messaggio indicante che il numero di conto immesso può essere utilizzato.  
5. Fare clic su OK.
    * Il sistema ora ha creato un nuovo conto cliente per il prospect dell'offerta.  
6. Chiudere la pagina.
7. Nel riquadro azioni fare clic su Follow-up.
8. Fare clic su Conferma.
9. Nel campo Motivo immettere o selezionare un valore.
10. Fare clic su OK.
11. Nel riquadro azioni fare clic su Generale.
12. Fare clic su Ordini cliente.
13. Chiudere la pagina.



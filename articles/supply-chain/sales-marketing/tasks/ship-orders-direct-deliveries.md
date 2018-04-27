--- 
title: Spedire ordini come consegne dirette
description: Questa procedura dimostra come si crea una consegna diretta per un ordine cliente.
author: omulvad
manager: AnnBe
ms.date: 02/12/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f674de4877dd2d6e6f1ff02f16a68cb4805d9864
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="ship-orders-as-direct-deliveries"></a>Spedire ordini come consegne dirette

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura dimostra come si crea una consegna diretta per un ordine cliente. Si utilizza la consegna diretta se si desidera spedire merci al cliente direttamente dal fornitore, anziché spedirle prima al proprio magazzino. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati. Per eseguire correttamente la seconda attività secondaria "Creare consegne dirette dal workbench", assicurarsi che l'articolo che si sceglie nell'ordine cliente abbia un fornitore predefinito specificato nella scheda dettaglio Acquisto della rappresentazione generale del prodotto rilasciato.


## <a name="set-an-individual-order-for-direct-delivery"></a>Impostare un singolo ordine per la consegna diretta
1. Fare clic su Tutti gli ordini cliente.
2. Fare clic su Nuovo.
3. Nel campo Conto cliente, immettere o selezionare un valore.
    * Se si utilizza USMF, è possibile selezionare il conto US-001.  
4. Fare clic su OK.
5. Nel campo Numero di articoli immettere o selezionare un valore.
    * Se si utilizza USMF, è possibile selezionare l'articolo T0020.  
6. Fare clic su Salva.
7. Nel riquadro azioni fare clic su Ordine cliente.
8. Fare clic su Consegna diretta.
    * Nella pagina Crea consegna è visualizzato l'elenco di tutte le righe ordine cliente aperte come copiate dall'ordine cliente. È possibile esaminare i dettagli dell'ordine e se necessario, è possibile modificare i dettagli quali la quantità di acquisto e i termini per la determinazione del prezzo prima di creare la consegna diretta.  
9. Selezionare Sì nel campo Includi tutto.
    * Se si desidera generare una consegna diretta solo per un sottoinsieme delle righe di ordine cliente, selezionarle singolarmente.  
    * Il campo Conto fornitore potrebbe essere già popolato con un numero fornitore. Se il fornitore predefinito è impostato per il prodotto (nella copertura articoli associata), questo fornitore verrà copiato nella riga. In caso contrario, è necessario immettere manualmente un fornitore. In questo esempio, verrà selezionato un nuovo fornitore al prossimo passaggio, anche se il campo è già popolato.   
10. Nel campo Conto fornitore, immettere o selezionare un valore.
    * Se si utilizza USMF, è possibile selezionare il conto 1001.  
11. Fare clic su OK.
    * Il messaggio informa che l'ordine fornitore è stato creato.   
12. Espandere la sezione Dettagli riga.
13. Fare clic sulla scheda Consegna.
    * Il campo Consegna diretta è impostato su Sì.  
    * Lo stato Consegna diretta mostra l'ordine acquisto creato.   
14. Nel riquadro azioni fare clic su Generale.
15. Fare clic su Ordini correlati.
16. Fare clic per seguire il collegamento nel campo Ordine fornitore.
17. Espandere la sezione Dettagli riga.
18. Fare clic sulla scheda Indirizzo.
    * Si noti che l'indirizzo di consegna per la riga ordine fornitore è l'indirizzo di consegna del cliente e non l'indirizzo della società.  
    * Se si modifica l'indirizzo di consegna nella riga dell'ordine acquisto o nella riga dell'ordine cliente originale, l'indirizzo nella riga dell'ordine corrispondente verrà aggiornato automaticamente.  
19. Fare clic sulla scheda Consegna.
    * Analogamente alla riga ordine cliente, il tipo di riga ordine fornitore associato verrà impostato su Consegna diretta.  
    * La data di consegna e la data di consegna confermata della riga ordine fornitore sono impostate sulla data di ricevimento richiesta e sulla data di ricevimento confermata della riga ordine cliente di origine rispettivamente.   
    * Se si aggiorna una di queste date nella riga di acquisto o nella riga di vendita, le date nell'ordine corrispondente verranno automaticamente aggiornate.     
    * L'ordine fornitore impostato per consegnare le merci direttamente al cliente è collegato all'ordine cliente di origine per mezzo di un'associazione speciale. Questa associazione impone la regola secondo cui l'aggiornamento del documento di trasporto dell'ordine cliente non può essere eseguito dall'ordine cliente stesso e deve essere effettuato utilizzando l'ordine fornitore. Tuttavia, la fatturazione cliente deve essere eseguita dall'ordine cliente.  
20. Nel riquadro azioni fare clic su Acquisti.
21. Fare clic su Conferma.
22. Fare clic su OK.
23. Nel riquadro azioni fare clic su Ricevimento.
24. Fare clic su Entrata prodotti.
25. Digitare un valore nel campo Entrata prodotti.
26. Fare clic su OK.
27. Nel riquadro azioni fare clic su Generale.
28. Fare clic su Ordini correlati.
29. Nell'elenco contrassegnare la riga selezionata.
    * Dopo che l'ordine fornitore è stato aggiornato come ricevuto, ovvero dopo che il fornitore ha consegnato le merci all'indirizzo del cliente, lo stato dell'ordine cliente di origine viene aggiornato automaticamente su Consegnato.  
    * L'ordine cliente può ora essere fatturato.    
30. Fare clic su OK.
31. Chiudere la pagina.
32. Fare clic su OK.

## <a name="create-direct-deliveries-from-the-workbench"></a>Creare consegne dirette dal workbench
1. Chiudere la pagina.
2. Chiudere la pagina.
3. Fare clic su Tutti gli ordini cliente.
4. Fare clic su Nuovo.
5. Nel campo Conto cliente, immettere o selezionare un valore.
6. Fare clic su OK.
7. Nel campo Numero di articoli immettere o selezionare un valore.
8. Espandere la sezione Dettagli riga.
9. Fare clic sulla scheda Consegna.
    * Anziché creare una consegna diretta come parte dell'elaborazione dell'ordine cliente come nella procedura precedente, è possibile scegliere di eseguire questa attività per un professionista degli acquisti. Per includere la riga ordine cliente nel processo di gestione consegna diretta, è necessario contrassegnare la riga per la consegna diretta.  
10. Selezionare Sì nel campo Consegna diretta.
    *   Se l'articolo è già stato impostato per la consegna diretta per impostazione predefinita, il campo verrà impostato automaticamente su Sì alla voce della riga ordine. È possibile impostare un articolo per la consegna diretta nella rappresentazione generale prodotto impostando l'opzione Consegna diretta su Sì e selezionando un magazzino consegna diretta.  
    * Poiché l'ordine acquisto non è ancora stato creato, lo stato della consegna diretta è impostato su Per consegna diretta.   
11. Chiudere la pagina.
12. Chiudere la pagina.
13. Passare a Consegna diretta.
    * La pagina Consegna diretta agisce da workbench che fornisce all'addetto acquisti una panoramica di tutte le righe ordine cliente che devono essere consegnate direttamente e permette di creare i rispettivi ordini fornitore. Inoltre, è possibile visualizzare gli ordini di consegna diretta aperti e gli ordini confermati nelle schede Conferma e Consegna.   
14. Fare clic su Crea consegna diretta.
15. Fare clic sulla scheda Conferma.
    * Dopo aver creato un ordine di consegna diretta, questo viene spostato automaticamente nella scheda Conferma. È possibile scegliere di confermare l'ordine direttamente in questa pagina. Quando l'acquisto viene confermato, viene automaticamente spostato nella scheda Consegna da cui è possibile registrarne la ricezione.  



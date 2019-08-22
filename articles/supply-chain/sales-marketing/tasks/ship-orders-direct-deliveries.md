---
title: Spedire ordini come consegne dirette
description: Questa argomento dimostra come si crea una consegna diretta per un ordine cliente.
author: omulvad
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, PurchCreateFromSalesOrder, VendAccountItemLookup, SalesTableReferences, PurchTable, PurchEditLines, PurchTableReferences, MCRDropShipWorkbench
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1bce2674b321475bc516724f74bac2d3a648e257
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843363"
---
# <a name="ship-orders-as-direct-deliveries"></a>Spedire ordini come consegne dirette

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa argomento dimostra come si crea una consegna diretta per un ordine cliente. Si utilizza la consegna diretta se si desidera spedire merci al cliente direttamente dal fornitore, anziché spedirle prima al proprio magazzino. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati. Per eseguire correttamente la seconda attività secondaria "Creare consegne dirette dal workbench", assicurarsi che l'articolo che si sceglie nell'ordine cliente abbia un fornitore predefinito specificato nella scheda dettaglio Acquisto della rappresentazione generale del prodotto rilasciato.

## <a name="set-an-individual-order-for-direct-delivery"></a>Impostare un singolo ordine per la consegna diretta
1. Passare al **pannello di navigazione >Moduli > Contabilità clienti > Ordini > Tutti gli ordini cliente**.
2. Selezionare **Nuovo**.
3. Nel campo **Conto cliente**, immettere o selezionare un valore, quindi selezionare **OK**
4. Immettere o selezionare valori nei campi **Sito** e **Numero articolo**, quindi selezionare **Salva**.
5. Nel riquadro azioni selezionare **Ordine cliente**, quindi **Consegna diretta**. Nella pagina Crea consegna è visualizzato l'elenco di tutte le righe ordine cliente aperte come copiate dall'ordine cliente. È possibile esaminare i dettagli dell'ordine e se necessario, è possibile modificare i dettagli quali la quantità di acquisto e i termini per la determinazione del prezzo prima di creare la consegna diretta.  
6. Selezionare **Sì** nel campo **Includi tutto**.
    - Se si desidera generare una consegna diretta solo per un sottoinsieme delle righe di ordine cliente, selezionarle singolarmente.  
    - Il campo **Conto fornitore** potrebbe essere già popolato con un numero fornitore. Se il fornitore predefinito è impostato per il prodotto (nella copertura articoli associata), questo fornitore verrà copiato nella riga. In caso contrario, è necessario immettere manualmente un fornitore. In questo esempio, verrà selezionato un nuovo fornitore al prossimo passaggio, anche se il campo è già popolato.   
7. Nel campo **Conto fornitore**, immettere o selezionare un valore, quindi selezionare **OK**. Il messaggio informa che l'ordine fornitore è stato creato.   
8. Espandere la sezione **Dettagli riga**.
9. Fare clic sulla scheda **Consegna** e verificare che il campo **Consegna diretta** sia impostato **Sì**.
10. Nel riquadro azioni fare clic su **Generale**.
11. Selezionare **Ordini correlati**.
12. Selezionare il collegamento nel campo **Ordine fornitore**.
13. Espandere la sezione **Dettagli riga** e selezionare  la scheda **Indirizzo**.
    - L'indirizzo di consegna per la riga ordine fornitore è l'indirizzo di consegna del cliente e non l'indirizzo della società.  
    - Se si modifica l'indirizzo di consegna nella riga dell'ordine acquisto o nella riga dell'ordine cliente originale, l'indirizzo nella riga dell'ordine corrispondente verrà aggiornato automaticamente.  
14. Selezionare la scheda **Consegna**.
    - Analogamente alla riga ordine cliente, il tipo di riga ordine fornitore associato verrà impostato su Consegna diretta.  
    - La data di consegna e la data di consegna confermata della riga ordine fornitore sono impostate sulla data di ricevimento richiesta e sulla data di ricevimento confermata della riga ordine cliente di origine rispettivamente.   
    - Se si aggiorna una di queste date nella riga di acquisto o nella riga di vendita, le date nell'ordine corrispondente verranno automaticamente aggiornate.     
    - L'ordine fornitore impostato per consegnare le merci direttamente al cliente è collegato all'ordine cliente di origine per mezzo di un'associazione speciale. Questa associazione impone la regola secondo cui l'aggiornamento del documento di trasporto dell'ordine cliente non può essere eseguito dall'ordine cliente stesso e deve essere effettuato utilizzando l'ordine fornitore. Tuttavia, la fatturazione cliente deve essere eseguita dall'ordine cliente.  
15. Nel riquadro azioni fare clic su **Acquisto**.
16. Selezionare **Conferma**.
17. Selezionare **OK**.
18. Nel riquadro azioni fare clic su **Ricevimento**.
19. Selezionare **Entrata prodotti**.
20. Nel campo **Entrata prodotti**, digitare un valore.
21. Selezionare **OK**.
22. Nel riquadro azioni fare clic su **Generale**.
23. Selezionare **Ordini correlati** ed evidenziare il record desiderato.
    - Dopo che l'ordine fornitore è stato aggiornato come ricevuto, ovvero dopo che il fornitore ha consegnato le merci all'indirizzo del cliente, lo stato dell'ordine cliente di origine viene aggiornato automaticamente su Consegnato.  
    - L'ordine cliente può ora essere fatturato.    
24. Selezionare **OK**.
25. Chiudere la pagina.
26. Selezionare **OK**. Chiudere le pagine e tornare alla home page.

## <a name="create-direct-deliveries-from-the-workbench"></a>Creare consegne dirette dal workbench
1. Passare al **pannello di navigazione >Moduli > Contabilità clienti > Ordini > Tutti gli ordini cliente**.
2. Selezionare **Nuovo**.
3. Nel campo **Conto cliente**, immettere o selezionare un valore, quindi selezionare **OK**
4. Nei campi **Numero articolo** e **Sito** immettere o selezionare un valore.
5. Espandere la sezione **Dettagli riga**, quindi selezionare la scheda **Consegna**. Anziché creare una consegna diretta come parte dell'elaborazione dell'ordine cliente come nella procedura precedente, è possibile scegliere di passare questa attività a un professionista degli acquisti. Per includere la riga ordine cliente nel processo di gestione consegna diretta, è necessario contrassegnare la riga per la consegna diretta.  
6. Selezionare **Sì** nel campo **Consegna diretta**.
    - Se l'articolo è già stato impostato per la consegna diretta per impostazione predefinita, il campo verrà impostato automaticamente su Sì alla voce della riga ordine. È possibile impostare un articolo per la consegna diretta nella rappresentazione generale prodotto impostando l'opzione Consegna diretta su Sì e selezionando un magazzino consegna diretta.  
    - Poiché l'ordine fornitore non è ancora stato creato, lo stato della consegna diretta è impostato su "Per consegna diretta".   
7. Selezionare **Salva**.
8. Chiudere le pagine fino a tornare alla home page.
9. Inserire `Direct delivery` nella barra di ricerca.
    - La pagina Consegna diretta agisce da workbench che fornisce all'addetto acquisti una panoramica di tutte le righe ordine cliente che devono essere consegnate direttamente e permette di creare i rispettivi ordini fornitore. Inoltre, è possibile visualizzare gli ordini di consegna diretta aperti e gli ordini confermati nelle schede Conferma e Consegna.  
    - Dopo aver creato un ordine di consegna diretta, questo viene spostato automaticamente nella scheda Conferma. È possibile scegliere di confermare l'ordine direttamente in questa pagina. Quando l'acquisto viene confermato, viene automaticamente spostato nella scheda Consegna da cui è possibile registrarne la ricezione.  


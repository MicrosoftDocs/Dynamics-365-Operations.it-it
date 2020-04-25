---
title: Creare un ordine fornitore da un ordine cliente
description: Questa procedura indica come creare un ordine fornitore in base a un ordine cliente.
author: omulvad
manager: tfehr
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, PurchCreateFromSalesOrder, VendAccountItemLookup, SalesTableReferences, PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3379f5899fedbe8944585388bdb98c4d810c2e26
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204358"
---
# <a name="create-a-purchase-order-from-a-sales-order"></a>Creare un ordine fornitore da un ordine cliente

[!include [banner](../../includes/banner.md)]

Questa procedura indica come creare un ordine fornitore in base a un ordine cliente. Le quantità del prodotto nell'ordine fornitore sono definite per soddisfare la richiesta dell'ordine cliente di origine. La richiesta di vendita soddisfatta in questo modo è un'alternativa all'approccio più completo e ottimizzato della pianificazione dei fabbisogni di distribuzione. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.


## <a name="create-a-purchase-order-from-a-sales-order"></a>Creare un ordine fornitore da un ordine cliente
1. Andare a **Pannello di navigazione > Moduli > Vendite e marketing > Ordini cliente > Tutti gli ordini cliente**.
2. Fare clic su **Nuovo**.
3. Nel campo **Conto cliente** fare clic sul pulsante a discesa per aprire la ricerca.
4. Trovare e selezionare il record desiderato nell'elenco.
5. Fare clic su **OK**.
6. Nel campo **Numero articolo** fare clic sul pulsante a discesa per aprire la ricerca.
7. Nell'elenco trovare e selezionare il record desiderato. Se si utilizza USMF, è possibile selezionare D0001.  
8. Nel campo **Quantità** immettere un numero.
9. Fare clic su **Aggiungi riga**.
10. Nel campo **Numero articolo** fare clic sul pulsante a discesa per aprire la ricerca.
11. Nell'elenco trovare e selezionare il record desiderato. Se si utilizza USMF, è possibile selezionare T0020.  
12. Nell'elenco fare clic sul collegamento nella riga selezionata.
13. Nel campo **Quantità** immettere un numero.
14. Fare clic su **Salva**.
15. Nel **riquadro azioni**, fare clic su **Ordine cliente**.
16. Fare clic su **Ordine acquisto**. Nella pagina **Crea ordine acquisto** è visualizzato l'elenco di tutte le righe ordine cliente aperte che sono state copiate dall'ordine cliente. È possibile esaminare i dettagli dell'ordine e se necessario, è possibile modificare i dettagli selezionati quali la quantità di acquisto e i termini per la determinazione del prezzo prima di creare gli acquisti. 
17. Selezionare l'opzione **Includi tutto**.
    - Se si desidera generare ordini acquisto solo per un sottoinsieme delle righe di ordine cliente, selezionarle singolarmente.  
    - Il campo **Conto fornitore** potrebbe essere già popolato con un numero fornitore. Se il fornitore predefinito è impostato per il prodotto (nella copertura articoli associata), questo fornitore verrà copiato nella riga. In caso contrario, è necessario immettere manualmente un fornitore.  Nella guida, indipendentemente dal campo **Conto fornitore** se già contiene un valore o meno, i seguenti passaggi indicano di selezionare un nuovo fornitore diverso per ciascuna riga.  
18. Nel campo **Conto fornitore** fare clic sul pulsante a discesa per aprire la ricerca.
19. Trovare e selezionare il record desiderato nell'elenco.
20. Nell'elenco fare clic sul collegamento nella riga selezionata.
21. Selezionare la seconda riga dell'ordine.
22. Nel campo **Conto fornitore** fare clic sul pulsante a discesa per aprire la ricerca.
23. Trovare e selezionare il record desiderato nell'elenco.
24. Nell'elenco fare clic sul collegamento nella riga selezionata.
25. Fare clic su **Convalida**.
26. Fare clic su **OK**. Il messaggio informa che uno o più ordini acquisto non sono stati creati. Il sistema genera un ordine acquisto separato per ciascun fornitore specificato per le righe dell'ordine cliente. Pertanto se più righe di ordine cliente devono essere fornite dallo stesso fornitore, verrà generato un singolo ordine fornitore con più righe.  

## <a name="review-purchase-orders-created-from-sales-orders"></a>Esaminare gli ordini acquisto creati da ordini cliente
1. Nel **riquadro azioni** fare clic su **Generale**.
2. Fare clic su **Ordini correlati**. Nella pagina **Ordini correlati** sono elencati tutti gli ordini creati dall'ordine cliente. In questo esempio, sono disponibili due ordini fornitore generati per due fornitori diversi rispettivamente. 
3. Fare clic per seguire il collegamento nel campo **Ordine acquisto**. Ciascuna riga ordine fornitore è associata alla riga ordine cliente da cui ha avuto origine l'acquisto. La relazione con l'ordine cliente viene visualizzata nella **scheda Prodotto** della Scheda dettaglio **Dettagli riga**, nei campi **Tipo di riferimento**, **Numero di riferimento** e **Lotto di riferimento**.  
4. Espandere o comprimere la sezione **Dettagli riga**.
5. Fare clic sulla scheda **Prodotto**.
    - Il **lotto di riferimento** garantisce che i costi dell'acquisto corrente vengano addebitati all'ordine cliente collegato.  
    - È possibile passare all'ordine cliente di origine aprendo il collegamento nel campo **Numero di riferimento**.  


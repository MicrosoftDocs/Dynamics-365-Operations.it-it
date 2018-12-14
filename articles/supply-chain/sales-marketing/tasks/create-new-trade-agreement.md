--- 
title: Creare un nuovo accordo commerciale
description: Questa procedura illustra come creare un accordo commerciale in cui si registra un nuovo prezzo di vendita del prodotto accordato con un cliente specifico.
author: omulvad
manager: AnnBe
ms.date: 11/16/2018
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
ms.sourcegitcommit: f7df0a91948a494465fbd55af99757e3890357ce
ms.openlocfilehash: e132cd20437b7929e81fcaa123d70bb57fb320c8
ms.contentlocale: it-it
ms.lasthandoff: 12/04/2018

---
# <a name="create-a-new-trade-agreement"></a>Creare un nuovo accordo commerciale

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura illustra come creare un accordo commerciale in cui si registra un nuovo prezzo di vendita del prodotto accordato con un cliente specifico. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati. Se si utilizzano i propri dati, prima di iniziare questa guida è necessario assicurarsi che sia presente un nome di giornale di registrazione per accordi commerciali in cui la relazione predefinita sia impostata su "Prezzo (vend.)".


## <a name="create-and-post-a-new-trade-agreement-journal"></a>Creare e registrare un nuovo giornale di registrazione degli accordi commerciali
1. Andare a Vendite e marketing > Prezzi e sconti > Giornale di registrazione accordi commerciali.
2. Fare clic su Nuovo.
3. Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.
4. Trovare e selezionare il record desiderato nell'elenco.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Fare clic su Righe.
7. Nel campo Conto selezionare "Tabella".
    * In questo esempio viene aggiornato il prezzo per un cliente specifico ed è pertanto necessario scegliere Tabella. Se si aggiorna il prezzo di listino del prodotto, è necessario selezionare Tutti, in modo che il nuovo prezzo sia valido per tutti i clienti. Se si differenziano i prezzi per segmenti di clienti diversi, è necessario selezionare Gruppo. Per selezionare Gruppo, è necessario impostare i gruppi di prezzi del cliente.  
8. Nel campo Selezione del conto fare clic sul pulsante a discesa per aprire la ricerca.
9. Nell'elenco trovare e selezionare il record desiderato.
10. Nel campo Codice articolo selezionare "Tabella".
    * Quando si immette un accordo commerciale di tipo "Prezzo (vend.)", è necessario selezionare "Tabella" nel campo Codice articolo. Ciò è dovuto al fatto che un prezzo è un valore assoluto e non può essere lo stesso per tutti i prodotti o per un gruppo di prodotti.  
11. Nel campo Relazione articolo fare clic sul pulsante a discesa per aprire la ricerca.
12. Nell'elenco selezionare il prodotto da includere nell'accordo.
    * Prendere nota del prodotto selezionato.  
13. Nell'elenco fare clic sul collegamento nella riga selezionata.
14. Nel campo Da immettere una quantità minima.
    * Se il cliente deve ordinare una quantità minima prima di ottenere il nuovo prezzo, è necessario specificare la quantità in questo campo.  
    * Immettere un valore nel campo A per specificare la quantità massima sopra cui il prezzo del contratto non sarà valido. Se si offrono prezzi e sconti in base a più intervalli di quantità, specificare ogni intervallo come una coppia di quantità minima e massima nel campo "Da" e "A" rispettivamente.  
15. Nel campo Importo in valuta immettere un prezzo.
16. Nel campo Dal immettere una data di inizio validità dell'accordo.
17. Fare clic su Salva.
18. Fare clic su Convalida.
19. Fare clic su Convalida le righe selezionate.
20. Fare clic su OK.
21. Fare clic su Registra.
22. Fare clic su OK.

## <a name="view-trade-agreements-for-a-product"></a>Visualizzare accordi commerciali per un prodotto
1. Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.
2. Nell'elenco individuare e selezionare il prodotto il cui prezzo è stato aggiornato.
3. Nel riquadro azioni fare clic su Vendi.
4. Fare clic su Visualizza accordi commerciali.
    * Esaminare i dettagli dell'accordo commerciale sui prezzi creato.    
5. Chiudere la pagina.

## <a name="additional-resources"></a>Risorse aggiuntive
### <a name="community-blogs"></a>Blog della Community
- [Prezzi di vendita in Dynamics 365 for Finance and Operations](https://financefunction.tech/2018/11/14/sales-prices-in-dynamics-365-for-finance-and-operations/#sales_price_in_trade_agreements)


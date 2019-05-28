---
title: Creare un ordine di sostituzione articolo
description: Gli ordini di sostituzione articolo vengono in genere creati dopo la restituzione e l'ispezione di un prodotto.
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReturnTableListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 784a2522c27e8131f211ffc52319552b3b928cc3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556831"
---
# <a name="create-an-item-replacement-order"></a>Creare un ordine di sostituzione articolo 

[!include [banner](../includes/banner.md)]


Gli ordini di sostituzione articolo vengono in genere creati dopo la restituzione e l'ispezione di un prodotto. Tuttavia, quando un articolo deve essere sostituito prima della restituzione, oppure quando un articolo non viene restituito, è possibile creare un ordine di sostituzione articolo immediatamente dopo la creazione di un ordine di reso.

## <a name="create-a-replacement-order-after-you-receive-an-item-that-is-returned"></a>Creare un ordine sostitutivo dopo che viene visualizzato un articolo che viene restituito

1.  Fare clic su **Vendite e marketing** \> **Comune** \> **Ordini di reso** \> **Tutti gli ordini di reso**.

2.  Creare un nuovo ordine di reso o selezionare un ordine di reso dall'elenco per aprire il modulo **Ordine di reso - Codice NAR: %1, %2**.

3.  Fare clic su **Riga reso**quindi selezionare **Articolo sostitutivo**.

4.  Selezionare l'articolo da sostituire con il reso. Immettere le specifiche dell'articolo e quindi fare clic su **Applica**.

5.  Fare clic su **Documento di trasporto** per generare il documento di trasporto per l'ordine di reso. Un ordine cliente viene generato per un articolo sostitutivo selezionato.
    
    Dopo che l'ordine cliente viene creato dell'articolo sostitutivo, i contratti di vendita vengono cercati automaticamente e se è presente un contratto di vendita applicabile, viene applicato all'ordine cliente.

## <a name="create-a-replacement-order-before-you-receive-an-item-that-will-be-returned"></a>Creare un ordine sostitutivo prima di ricevere un articolo che verrà restituito

1.  Fare clic su **Vendite e marketing** \> **Comune** \> **Ordini di reso** \> **Tutti gli ordini di reso**.

2.  Creare un nuovo ordine di reso o selezionare un ordine di reso dall'elenco per aprire il modulo **Ordine di reso - Codice NAR: %1, %2**.

3.  Fare clic su **Trova ordine cliente** se si desidera identificare l'ordine cliente per il reso. Completare il modulo **Trova ordine cliente** quindi fare clic su **OK** per chiudere il modulo e tornare al modulo **Ordine di reso - Codice NAR: %1, %2**. La riga di ordine cliente per il reso viene copiata nell'ordine di reso.

4.  Fare clic su **Ordine sostitutivo** per aprire il modulo **Crea ordine cliente**.

5.  Selezionare la casella di controllo **Copia righe ordine di reso** per trasferire i dettagli dall'ordine di reso selezionato nel modulo **Ordine di reso - Codice NAR: %1, %2** all'ordine cliente corrente.

6.  Immettere o modificare i dettagli, come richiesto.
    
    Se è stato identificato l'ordine cliente al passaggio 3 e se la riga ordine cliente per il reso è collegata a un contratto di vendita, l'identificatore del contratto di vendita applicabile per l'ordine di sostituzione articolo verrà automaticamente visualizzato nel campo **ID contratto di vendita**.

7.  Fare clic su **OK** per chiudere il modulo **Crea ordine cliente** e aprire il modulo **Ordine cliente**, in cui è possibile continuare a immettere le informazioni per il nuovo ordine cliente. Tutte le righe degli ordini di reso applicabili verranno copiate nel nuovo ordine cliente. 
    
    Se l'identificatore del contratto di vendita viene visualizzato automaticamente nel campo **ID contratto di vendita**, il contratto di vendita è stato collegato all'intestazione ordine cliente dell'ordine di sostituzione articolo. Se è presente un impegno applicabile nel contratto di vendita che non è stato ancora compiuto e l'ordine cliente viene creato prima della scadenza del contratto di vendita, viene stabilito un collegamento tra la riga contratto di vendita e la riga ordine cliente. Di conseguenza, le informazioni del contratto di vendita, ad esempio il prezzo dell'articolo, vengono copiate nella nuova riga ordine cliente. 
  



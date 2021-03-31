---
title: Eseguire il prezzo di costo e restituire l'ID lotto
description: Si può decidere che il costo dei prodotti resi deve essere uguale al costo dei prodotti nel momento in cui sono stati venduti al cliente. È possibile effettuare questa operazione utilizzando **Operazione ID lotto**.
author: ShylaThompson
manager: tfehr
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReturnTableListPage, ReturnInventTransIdLookup, ReturnItemNumLookup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b420c0716823f587ea3f349a5d654ace23d84f41
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5219271"
---
# <a name="return-cost-price-and-return-lot-id"></a>Eseguire il prezzo di costo e restituire l'ID lotto        

[!include [banner](../includes/banner.md)]



Il costo dei prodotti resi al magazzino viene calcolato utilizzando il costo corrente dei prodotti. Si può tuttavia decidere che il costo dei prodotti resi deve essere uguale al costo dei prodotti nel momento in cui sono stati venduti al cliente. A tale scopo, utilizzare il campo **ID lotto resi** della Scheda dettaglio **Dettagli riga** nel modulo **Ordine cliente**.

Ad esempio, considerare il seguente scenario. Si invia la fattura a un cliente. Quindi, il cliente restituisce i prodotti consegnati. I prodotti vengono restituiti al magazzino. In questo caso, quando si emette una nota di accredito al cliente per i prodotti resi, il costo dei prodotti viene calcolato utilizzando il costo corrente dei prodotti. Se invece si utilizza il campo **ID lotto resi**, il costo dei prodotti resi viene calcolato utilizzando il costo riportato nella fattura di vendita originale al cliente.

Per utilizzare un costo diverso da quello corrente per i resi da un cliente, utilizzare uno dei seguenti metodi.

## <a name="method-1-manually-enter-the-return-cost-price"></a>Metodo 1: immettere manualmente il prezzo di costo di reso

Per impostazione predefinita, quando si aggiungono articoli a un ordine di reso, gli articoli vengono restituiti al magazzino al prezzo di costo corrente. Per specificare un prezzo di costo di reso diverso, effettuare le operazioni seguenti.

1.  Fare clic su **Vendite e marketing** \> **Comune** \> **Ordini di reso** \> **Tutti gli ordini di reso**.

2.  Nel **riquadro azioni** fare clic su **Ordine di reso** nel gruppo **Nuovo**.

3.  Nel modulo **Crea ordine di reso**, selezionare un conto cliente e fare clic su **OK**.

4.  Nel modulo **Ordine di reso - Codice NAR: %1, %2**, selezionare un articolo e immettere una quantità negativa nel campo **Quantità**.

5.  Fare clic sulla Scheda dettaglio **Dettagli riga**.

6.  Nella scheda **Generale** immettere un valore nel campo **Prezzo di costo reso**. Questo valore viene utilizzato quando le merci vengono restituite al magazzino. Se non si immette alcun valore, il prezzo di costo corrente viene utilizzato quando le merci vengono restituite al magazzino.

## <a name="method-2-automatically-generate-the-cost-price-based-on-the-customer-invoice-line"></a>Metodo 2: generare automaticamente il prezzo di costo in base alla riga fattura cliente

Questo è il metodo preferito da utilizzare per creare le righe di reso. Per utilizzare il costo dei prodotti nel momento in cui sono stati venduti al cliente, creare un ordine di reso e specificare una riga di vendita da restituire.

1.  Fare clic su **Vendite e marketing** \> **Comune** \> **Ordini di reso** \> **Tutti gli ordini di reso**.

2.  Nel **riquadro azioni** fare clic su **Ordine di reso** nel gruppo **Nuovo**.

3.  Nel modulo **Crea ordine di reso**, selezionare un conto cliente e fare clic su **OK**.

4.  Nel modulo **Ordine di reso - Codice NAR: %1, %2** nel **riquadro azioni**, fare clic su **Trova ordine cliente**.

5.  Nel modulo **Trova ordine cliente** selezionare la riga fattura per il reso, quindi fare clic su **OK**.
    
    Nella Scheda dettaglio **Dettagli riga**, nella scheda **Generale**, il campo **ID lotto resi** visualizza il valore della riga di vendita originale. Inoltre, il campo **Prezzo di costo reso** visualizza il valore di costo dalla riga di vendita originale.

## <a name="cost-calculation-example"></a>Esempio di calcolo dei costi

Quando si utilizza il campo **ID lotto resi** in una riga ordine di reso per specificare il prezzo di costo di reso, viene utilizzato il costo nella riga ordine di reso. Se si esegue la funzionalità di chiusura o il ricalcolo di inventario, il costo viene rettificato nella riga di vendita originale. Il costo nella riga ordine di reso viene rettificato automaticamente per riflettere lo stesso costo per pezzo.

1.  Creare e rilasciare un prodotto denominato Test. Nel modulo **Dettagli prodotto rilasciato**, specificare le informazioni seguenti:
    
    1.  Nella Scheda dettaglio **Gestisci costi** selezionare il gruppo **Parti** nel campo **Gruppo di articoli**.
    
    2.  Nel campo **Gruppo di modelli di articoli** della Scheda dettaglio **Generale**, selezionare **DEF**.
    
    3.  Nel campo **Prezzo** della Scheda dettaglio **Acquisti**, digitare 10,00 come prezzo di costo dell'articolo.
    
    4.  Nel **riquadro azioni**, fare clic su **Gruppi di dimensioni**. Nel campo **Gruppo di dimensioni di immagazzinamento**, selezionare **Solo sito e magazzino**. Nel campo **Gruppo di dimensioni di tracciabilità** selezionare **Nessuna dimensione di tracciabilità attiva**.

2.  Creare un ordine fornitore per 10 pezzi dell'articolo Test a 6,00 per pezzo, quindi registrare una fattura per l'ordine fornitore.
    
    Creare un secondo ordine fornitore per 10 pezzi dell'articolo Test a 8,00 per pezzo, quindi registrare una fattura per l'ordine fornitore.

3.  Registrare una fattura per un ordine cliente per la vendita di cinque pezzi dell'articolo Test.
    
    In questo caso, la riga ordine cliente è preventivata a 35,00 (5 pezzi \* costo medio di 7,00 per pezzo).

4.  Creare un ordine di reso per il cliente. Nel modulo **Trova ordine cliente** selezionare la riga fattura, quindi fare clic su **OK**.

5.  Nel modulo **Ordine di reso - Codice NAR: %1, %2** verificare che un ordine di reso venga generato per il reso dell'articolo Test. La quantità dell'ordine di reso è impostata su -5,00.
    
    Il campo **ID lotto resi** visualizza un ID lotto. Questo ID lotto viene ricavato dall'ordine cliente originale dell'articolo che è stato venduto al cliente. Il campo **Prezzo di costo reso** visualizza il prezzo di costo dalla riga di vendita originale.

6.  Registrare il ricevimento degli articoli resi.

7.  Registrare un documento di trasporto per gli articoli resi.

8.  Registrare una fattura per l'ordine di reso. Nella pagina elenco **Tutti gli ordini cliente** selezionare un ordine cliente per cui **Ordine di reso** è il tipo di ordine.

9.  Aprire il modulo **Operazioni di magazzino**. Verificare che il reso sia preventivato a 7,00 per pezzo utilizzando il valore nel campo **Prezzo di costo reso**, per un totale di 35,00 nel campo **Importo costi**. È possibile aprire il modulo **Operazioni di magazzino** dal modulo **Ordine di reso - Codice NAR: %1, %2**. Nella griglia **Righe** fare clic su **Magazzino** \> **Transazioni**.

10. In Gestione articoli e magazzino, utilizzare il modulo **Chiusura e rettifica** per eseguire la procedura **3. Chiudere**.
    
    Questa azione consente di rettificare il costo nella riga di vendita originale, che era preventivata a -35,00 (5 pezzi \* 7,00), a -30,00 (5 pezzi \* 6,00). Ciò accade perché il gruppo di modelli inventariali utilizza il metodo FIFO (First In, First Out) e 6,00 per pezzo è il costo FIFO dal primo ordine fornitore. Inoltre, l'azione consente di rettificare il costo della riga di vendita di reso in modo che corrisponda al costo per pezzo nella riga di vendita originale. Pertanto, il costo della riga di reso viene rettificato da 35,00 a 30,00.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
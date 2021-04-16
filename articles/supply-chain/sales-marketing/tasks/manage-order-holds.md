---
title: Gestire sospensioni ordine
description: In questa procedura viene illustrato come mettere in sospeso ordini cliente, come utilizzare i check-out della sospensioni ordine e come rimuovere le sospensioni ordine.
author: omulvad
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MCRHoldCodeTable, SalesTableListPage, SalesCreateOrder, SalesTable, MCRHoldCodeTrans, MCRHoldCheckOutOverride, MCRHoldCodeTable, MCRItemListCopying, MCRItemListTable, MCROMHoldList
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a0a6acbc55a69f854463e72391fb0fff4dfb459c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817727"
---
# <a name="manage-order-holds"></a>Gestire sospensioni ordine

[!include [banner](../../includes/banner.md)]

In questa procedura viene illustrato come mettere in sospeso ordini cliente, come utilizzare i check-out della sospensioni ordine e come rimuovere le sospensioni ordine. Un ordine può essere sospeso per diversi motivi. Ad esempio, è possibile sospendere un ordine fino a che non può essere verificato un indirizzo cliente o un metodo di pagamento o fino a che un responsabile può verificare il limite di credito del cliente. Quando l'ordine è in sospeso, non potrà essere elaborato dal magazzino per la spedizione. 

È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.


## <a name="set-up-order-holds"></a>Impostare sospensioni ordine
1. Andare a **Pannello di navigazione > Moduli > Vendite e marketing > Impostazioni > Ordini cliente > Codici sospensione ordine**.
2. Fare clic su **Nuovo**.
3. Digitare un valore nel campo **Codice sospensione**. Ad esempio, digitare "Richiamata".  
4. Digitare un valore nel campo **Descrizione**
    - Ad esempio, ordine in sospeso in attesa il contenuto del cliente.  
    - Facoltativamente, selezionare la casella di controllo **Rimuovi prenotazioni** per rimuovere tutte le prenotazioni fisiche dall'ordine quando il codice di sospensione viene aggiunto.  
5. Fare clic su **Salva**.

## <a name="place-order-on-hold"></a>Mettere un ordine in attesa
1. Andare a **Pannello di navigazione > Moduli > Vendite e marketing > Ordini cliente > Tutti gli ordini cliente**.
2. Fare clic su **Nuovo**.
3. Nel campo **Conto cliente**, immettere o selezionare un valore.
4. Fare clic su **OK**.
5. Nel campo **Numero articolo** immettere o selezionare un valore.
6. Nel campo **Quantità** immettere un numero.
7. Nel **riquadro azioni**, fare clic su **Ordine cliente**.
8. Fare clic su **Sospensioni ordine**.
9. Fare clic su **Nuovo**.
10. Nel campo **Codice sospensione**, selezionare il codice creato nella sottoattività precedente.
11. Fare clic su **Salva**.
12. Chiudere la pagina.
13. Passare a **Vendite e marketing > Ordini cliente > Tutti gli ordini cliente**.
14. Nell'elenco contrassegnare la riga selezionata. Gli ordini attualmente in attesa hanno i campi "Non elaborare"e "Pausa" contrassegnati.
15. Nel riquadro azioni fare clic su **Preleva e imballa**.

## <a name="manage-order-holds"></a>Gestire sospensioni ordine
1. Passare a **Vendite e marketing > Ordini cliente > Ordini aperti > Sospensioni ordine**. La pagina delle **sospensioni ordini** funziona come workbench in cui è possibile visualizzare una panoramica di tutte le sospensioni correnti ed elaborate e gestire le sospensioni e gli ordini cliente associati.     
2. Nell'elenco contrassegnare la riga selezionata.
3. Nel **riquadro azioni**, fare clic su **Sospendi estrazione**.
4. Fare clic su **Estrai**.
5. Nell'elenco deselezionare la riga selezionata. Il campo **Estrai in** ora mostra l'ID utente.   
6. Fare clic su **Cancella estrazione**.
7. Nel **riquadro azioni**, fare clic su **Cancella sospensione**.
    - Quando si è pronti a rimuovere la sospensione e a consentire all'ordine di procedere al passaggio successivo dell'evasione, è necessario cancellare la sospensione. Se per l'ordine non sono necessarie modifiche, è possibile eseguire l'azione Cancella sospensioni. Tuttavia, è possibile utilizzare l'azione Cancella e modifica, se al momento della cancellazione di una sospensione, l'ordine deve essere aggiornato.      
    - L'azione **Cancella e invia** è applicabile solo quando si utilizza la funzionalità Servizio clienti.  
8. Fare clic su **Cancella sospensioni**. La sospensione è stata cancellata dall'ordine e rimossa dall'elenco delle sospensioni attive. Per visualizzare tutte le sospensioni o i relativi sottoinsiemi in base a uno stato specifico, modificare il valore nel campo Mostra.     



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
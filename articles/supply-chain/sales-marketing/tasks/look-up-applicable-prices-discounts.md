---
title: Cercare i prezzi e gli sconti applicabili
description: Questa procedura illustra come trovare il prezzo e/o lo sconto per un prodotto che è attualmente valido per un cliente specifico, senza creare un ordine cliente.
author: omulvad
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 50d7cf7b765c27db5aa9ea50c8593132c68c850a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824848"
---
# <a name="look-up-applicable-prices-and-discounts"></a>Cercare i prezzi e gli sconti applicabili

[!include [banner](../../includes/banner.md)]

Questa procedura illustra come trovare il prezzo e/o lo sconto per un prodotto che è attualmente valido per un cliente specifico, senza creare un ordine cliente. La procedura viene eseguita tramite un esempio specifico che è necessario seguire utilizzando la società dimostrativa USMF per selezionare i valori necessari.


## <a name="find-the-applicable-price"></a>Individuare il prezzo applicabile
1. Andare a Vendite e marketing > Prezzi e sconti > Trova prezzi.
2. Nel campo Conto cliente fare clic sul pulsante a discesa per aprire la ricerca.
3. Trovare e selezionare il record cliente US-001.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Nel campo Numero articolo digitare "T0004".
    * Per impostazione predefinita, il campo Quantità è impostato su 1. Tuttavia, se si conosce la dimensione dell'ordine che il cliente intende effettuare per il prodotto, immettere tale valore. Queste informazioni sono rilevanti se per gli accordi commerciali con il cliente sono presenti intervalli di quantità, ovvero se il prezzo del prodotto dipende dalla quantità minima acquistata.  
6. Nel campo Data immettere una data in cui si prevede che il cliente effettui un ordine. 
    * La data può essere quella odierna o una qualsiasi data nel futuro.  
    * Il sistema ora restituisce il prezzo valido per il prodotto selezionato una volta acquistato dal cliente selezionato nella data indicata con una quantità specificata. In questo esempio, se il cliente US-001 acquista oggi un'unità di prodotto T0004, vengono addebitati 350 EUR per unità. Il prezzo viene ricavato da un accordo commerciale con il cliente esistente e attivo.      Altri campi nella pagina forniscono ulteriori dettagli sul prezzo e sul costo del prodotto (se impostati nella rappresentazione generale prodotto) e sulla redditività calcolata.  
    * Se l'opzione Mostra varianti prodotti correlate è selezionata, significa che sono presenti accordi commerciali aggiuntivi per le varianti prodotto.  
7. Selezionare la casella di controllo Mostra varianti prodotti correlate.
    * Un elenco di varianti prodotto viene visualizzato, con informazioni sulle dimensioni.  
8. Nell'elenco, contrassegnare la riga che rappresenta il colore bianco.
    * Si noti che il prezzo del prodotto ora è diverso da quello visualizzato in precedenza quando non era specificato per dimensione.  
9. Fare clic su Visualizza prezzi di vendita.
    * Nella pagina Prezzo (vend.) vengono visualizzati tutti gli accordi commerciali applicabili al prodotto, incluse le varianti.  
10. Chiudere la pagina.

## <a name="find-the-applicable-discount"></a>Individuare lo sconto applicabile
Verificare che il campo del conto cliente contenga il numero cliente US-001    
1. Nel campo Numero articolo digitare "T0012".
    * Assicurarsi che il campo Quantità sia impostato su 1.  
    * I seguenti dettagli di prezzo visualizzati per il prodotto T0012 derivano da uno o più accordi commerciali. Il prezzo unitario è di 1.000 EUR e la percentuale di sconto è 5.  
2. Impostare la quantità su "20".
    * Le quantità ordine aumentata determina la modifica dello sconto riga che verrà offerto da 5 a 7.  
    * L'importo netto viene calcolato in base al prezzo unitario, allo sconto e alla quantità totale.  
3. Fare clic su Visualizza sconto riga.
    * Sono disponibili due accordi sugli sconti riga per il prodotto T0012, che specificano uno sconto del 5% per una quantità della riga ordine da 1 a 10 e del 7% per le quantità ordine superiori a 10. Si noti che gli sconti vengono applicati a un gruppo di prodotti, in questo esempio al gruppo con codice 01, a cui il prodotto T0012 appartiene.  
4. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
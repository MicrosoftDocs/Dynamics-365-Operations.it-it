---
title: Crea ordine cliente
description: Questa procedura indica come creare un ordine cliente.
author: omulvad
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, InventDimParmFixed, InventProductDimensionLookup, SalesTotals
audience: Application User, SalesTableDelete, SalesTableListPagePreviewPage, SalesUpdateRemain
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3bf52a90a709aa74c579aa0047a38c1f3c7a845711f61f07a491705c798f1c62
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744084"
---
# <a name="create-sales-orders"></a>Crea ordine cliente

[!include [banner](../../includes/banner.md)]

Questa procedura indica come creare un ordine cliente. È possibile utilizzare questa procedura nella società di dati dimostrativi USMF. Gli ordini cliente vengono in genere creati da un sistema di elaborazione degli ordini cliente. 

## <a name="enter-sales-order-header-details"></a>Immettere i dettagli dell'intestazione ordine cliente
1. Andare a **Pannello di navigazione > Moduli > Vendite e marketing > Ordini cliente > Tutti gli ordini cliente**.
2. Selezionare **Nuovo**.
3. Nel campo **Conto cliente** selezionare il pulsante a discesa per aprire la ricerca.
4. Trovare e selezionare il record cliente nell'elenco.
    - Per questo esempio, selezionare il numero cliente US-004.  
5. Selezionare **OK**.

## <a name="enter-sales-order-line-details"></a>Immettere i dettagli della riga ordine cliente
    
I prodotti venduti dall'organizzazione possono presentare varianti differenziate per le dimensioni, ad esempio la configurazione, il colore, le dimensioni e lo stile. Inoltre, i prodotti possono essere impostati per utilizzare le dimensioni di immagazzinamento, ad esempio sito, magazzino e pallet e dimensioni di scaffali, ad esempio i numeri batch e di serie. Quando vengono assegnate queste dimensioni, è necessario selezionare i valori di tali dimensioni nella riga ordine. Per aumentare l'efficienza della registrazione ordine, potrebbe essere necessario aggiungere i campi delle rispettive dimensioni alla griglia dell'ordine.
    
1. Sotto la sezione **Righe ordine cliente** selezionare **Riga ordine cliente**.
2. Selezionare **Dimensioni**.
    
    Per questo esempio, selezionare Colore, Sito e Dimensioni magazzino. Le dimensioni selezionate qui verranno visualizzate nella griglia dell'ordine cliente. Se si desidera che le selezioni vengano salvate in modo permanente, impostare l'opzione **Salva impostazione** su Sì.
    
3. Selezionare **OK**.
4. Nel campo **Numero articolo** fare clic sul pulsante a discesa per aprire la ricerca.
5. Per questo esempio, selezionare il numero articolo T0004.
    - Se l'articolo fa parte di una categoria di vendita, il nome verrà visualizzato automaticamente nel campo Categoria di vendita.  
    - Se i campi Dimensione prodotto non contengono un valore, è dovuto al fatto che il valore è stato copiato dal record del prodotto in cui viene definito come dimensione prodotto predefinita. È possibile modificare il valore predefinito in qualsiasi momento.   
6. Nel campo **Colore** fare clic sul pulsante a discesa per aprire la ricerca.
7. Nell'elenco trovare e selezionare il record desiderato.
8. Nel campo **Quantità** immettere un numero.
    - Se l'articolo viene venduto in unità diverse rispetto a quando è stato acquistato, prodotto e archiviato e nel record del prodotto viene impostata un'unità di misura di vendita, questo valore verrà visualizzato nel campo **Unità**. È possibile modificare il valore in qualsiasi momento.   
    - Se il campo **Sito** contiene già un valore, il valore è stato copiato dall'intestazione ordine o dalle impostazioni dell'ordine associate al prodotto. È possibile modificare il valore in qualsiasi momento. Se il campo è vuoto, selezionare un valore.   
    - Se il campo **Prezzo unitario** contiene già un valore, il valore è stato copiato da un accordo commerciale valido o dal record del prodotto. (Il prezzo unitario può anche avere origine da un contratto di vendita, ma il processo per creare ordini cliente dai contratti di vendita è diverso da quello visualizzato in questo campo). Se il campo è vuoto, immettere un valore.   
    - Il campo **Sconto** contiene un importo di sconto unitario del prodotto. Per calcolare l'importo totale dello sconto riga, il valore dello sconto viene moltiplicato per la quantità della riga. Se il campo **Sconto** contiene già un valore, il valore è stato copiato da un accordo commerciale valido. Se il campo è vuoto e si desidera fornire al cliente uno sconto riga, immettere un valore.  
    - Il campo **Percentuale di sconto** contiene un valore percentuale in base al quale l'importo lordo totale della riga deve essere ridotto.  Se il campo **Percentuale sconto** contiene già un valore, il valore è stato copiato da un accordo commerciale valido. Se il campo è vuoto e si desidera fornire al cliente uno sconto riga, immettere un valore. 
    - Il campo **Importo netto** contiene un valore calcolato in base alla quantità e al prezzo unitario della riga rettificato in base agli sconti.  È possibile sostituire il valore calcolato con uno diverso.  

## <a name="review-the-order-totals"></a>Rivedere i totali ordini
1. Nel **Riquadro azioni**, selezionare **Ordine cliente**.
2. Selezionare **Totali**.
    
    Nella pagina **Totali** vengono visualizzati i dettagli dell'intero ordine. Sono inclusi l'importo subtotale, ovvero una somma di tutti gli importi netti della riga rettificati per gli sconti riga finali, l'importo totale della fattura, ovvero un importo subtotale rettificato per lo sconto a livello di ordine finale, le spese e l'IVA, la situazione limite di credito del cliente e altro. Importo della fattura è l'importo che verrà visualizzato nel documento fattura del cliente.  
    
3. Selezionare **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
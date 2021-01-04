---
title: Creare un ordine fornitore
description: In questo argomento viene descritto come creare un ordine fornitore manualmente.
author: mkirknel
manager: tfehr
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, InventDimParmFixed, InventItemIdLookupPurchase, InventProductDimensionLookup, PurchTotals
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ec91174f291bcfa7027a93ca344823561cc29e3f
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4431542"
---
# <a name="create-a-purchase-order"></a>Creare un ordine fornitore

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come creare un ordine fornitore manualmente. È più normale che gli ordini fornitori vengano creati automaticamente come risultato di una pianificazione generale, della consegna diretta e di altri processi. Gli ordini acquisti sono in genere creati da un addetto agli acquisti. L'esempio riportato in questo campo può essere utilizzato nella società di dati dimostrativi USMF usando i valori che verranno suggeriti nelle note per i vari passaggi.


## <a name="create-the-purchase-order-header"></a>Creare l'intestazione ordine fornitore
1. Passare a **pannello di navigazione > Moduli > Approvvigionamento > Ordini fornitore > Tutti gli ordini fornitore**.
2. Selezionare **Nuovo**.
3. Selezionare il conto fornitore **US-101**. Quando si seleziona un fornitore, i dettagli del record fornitore, ad esempio indirizzo, conto fatture, termini di consegna e modalità di consegna verranno copiati come valori predefiniti nell'intestazione ordine. È possibile modificare questi valori in qualsiasi momento.  
4. Espandere la sezione **Generale**.

    - Il campo **Sito** insieme al campo **Magazzino** specifica il luogo in cui le merci o i servizi ottenuti devono essere consegnati. L'indirizzo di consegna predefinito è il sito. Entrambi i campi possono essere popolati con l'impostazione dei valori per il fornitore selezionato oppure è possibile specificarli manualmente.  
    - Il campo **Data di consegna** viene utilizzato per specificare quando devono essere consegnati i beni e i servizi ottenuti. È possibile specificare una singola data di consegna per l'ordine o nelle singole righe ordine è possibile immettere date di consegna univoche. Se la data di consegna indicata in questo campo non può essere soddisfatta per i prodotti o i servizi specifici poiché questi hanno lead time maggiori, le righe verranno create con una data di consegna successiva.  

5. Espandere la sezione **Amministrazione**. Il campo **Autore ordine** può essere utilizzato per specificare chi sta eseguendo l'ordine. È opportuno condividerlo con il fornitore nel caso debba contattare la persona. Al campo può essere assegnato un valore automaticamente se l'account utente corrente è associato a un nome nella pagina **Utenti**.  
6. Selezionare **OK**. L'intestazione ordine ora è stata creata. Quando si utilizzano le righe ordine fornitore, solo un riepilogo delle informazioni dell'intestazione viene visualizzato. Se è necessario visualizzare il resto delle informazioni, selezionare **Intestazione**.  

## <a name="add-a-purchase-order-line"></a>Aggiungere una riga ordine fornitore
1. Selezionare **Riga ordine fornitore**.
2. Selezionare **Dimensioni**. I prodotti possono essere in varianti differenziate in base alle dimensioni, ad esempio, colore, dimensione o stile. I prodotti possono essere impostati per utilizzare le dimensioni di immagazzinamento, ad esempio sito e magazzino. Esistono inoltre dimensioni di tracciabilità facoltative, ad esempio batch e numeri di serie. Per migliorare l'efficienza della registrazione ordine, è possibile aggiungere i campi dimensione utilizzati in genere direttamente nella griglia di ordine.  
3. Selezionare la casella di controllo **Colore**. Facoltativo: se si seleziona il campo **Salva impostazione**, le dimensioni specificate verranno anche visualizzate nella griglia della riga ordine alla successiva apertura della pagina ordine fornitore.  
4. Selezionare **OK**.
5. Nel campo **Numero articolo** selezionare **T0004**.

    - Le righe ordine vengono create per i prodotti e i servizi specificando un numero di articolo o come spese specificando una categoria di approvvigionamento. 
    - Il campo **Categoria di approvvigionamento** viene utilizzato per l'aggiunta delle righe in cui gli articoli ottenuti sono inseriti direttamente nelle spese, anziché nell'inventario. Pertanto, se è necessario inserire tra le spese un acquisto è possibile effettuare questa operazione creando una riga ordine fornitore che specifichi una categoria di approvvigionamento, anziché creare una riga con un numero articolo. Gli articoli possono essere associati a una categoria di approvvigionamento e in questo caso la categoria di approvvigionamento viene visualizzata solo come informativa.  

6. Nel campo **Colore** immettere o selezionare un valore. I campi **Sito** e **Magazzino** sono in genere popolati con i valori dall'intestazione ordine, ma è possibile ignorare i campi se alcune righe devono essere consegnate a ubicazioni diverse.  
7. Nel campo **Quantità** immettere un numero.

    - Selezionare la quantità che si desidera acquistare. Il campo **Quantità** viene automaticamente compilato con la quantità di ordine minima per il prodotto se questo è impostato oppure con il valore 1.  
    - Il campo **Unità** indica l'unità di misura per la quantità ordinata. In genere, l'unità viene automaticamente fornita dall'unità di acquisto dei dati della rappresentazione generale prodotto, ma si può modificare.  
    - Il campo **Prezzo unitario** in genere contiene un valore di un contratto di acquisto o di un accordo commerciale. È possibile modificare il prezzo unitario nelle singole righe ordine, ad esempio se un prezzo univoco viene negoziato con il fornitore.  
    - Il campo **Sconto** rappresenta un importo di sconto unitario. Questo sconto riduce il prezzo unitario in base allo sconto. Questo sconto viene in genere fornito automaticamente dai contratti di acquisto o dagli accordi commerciali, ma è possibile ignorarlo su singole righe se gli sconti univoci sono stati negoziazioni con il fornitore.  
    - Di conseguenza, può essere immessa una percentuale di sconto che riduce l'importo netto della riga. La percentuale di sconto viene spesso fornita automaticamente dai contratti di acquisto o dagli accordi commerciali, ma è possibile ignorarla su singole righe se con il fornitore è stata negoziaziota una percentuale di sconto univoco.  
    - Il valore del campo **Importo netto** viene calcolato da altri campi nella riga che include la quantità, il prezzo unitario, lo sconto e la percentuale di sconto. È possibile modificare l'importo netto, ma dopo i campi **Prezzo unitario**, **Sconto** e **Percentuale sconto** risulteranno vuoti e quando si registra verso la riga, l'importo registrato sarà proporzionale all'importo netto. In genere il campo **Importo netto** viene utilizzato solo per visualizzare l'importo netto della riga.  

8. Espandere la sezione **Dettagli riga**.
9. Selezionare la scheda **Consegna**. Una data di consegna univoca può essere assegnata a ciascuna riga ordine. La data viene ereditata dal campo dell'intestazione dell'ordine fornitore, ma si può modificare.  

## <a name="review-order-totals"></a>Rivedere i totali ordini
1. Selezionare **Totali**.

    - Se non noti l'azione **Totali**, seleziona la scheda **Ordine fornitore** nel riquadro azioni.  
    - Questa finestra di dialogo mostra i totali dell'intero ordine.  
    - Il campo **Selezione** consente di modificare la base di come vengono calcolati i totali. Ad esempio, è possibile scegliere **Quantità entrata prodotti** per visualizzare i totali correlati all'importo dei prodotti ricevuti o **Quantità ordinata** per visualizzare l'importo del prodotto ordinato.  

2. Selezionare **OK**.


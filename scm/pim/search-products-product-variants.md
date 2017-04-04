---
title: Ricerca di prodotti e varianti prodotto durante la registrazione ordine
description: "Utilizzare il campo <strong>Numero articolo </strong>per cercare i prodotti e le varianti prodotto quando si crea manualmente una riga ordine cliente o una riga ordine fornitore.  In questo modo è possibile trovare rapidamente le varianti prodotto quando si dispone solo della stringa di configurazione o una delle dimensioni prodotto."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: MCRFullTextIndexField, MCRFullTextParameters, PurchTable, SalesTable
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 248534
ms.assetid: 99dd5ce1-0029-4f06-90e7-865e6d46d86e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 5b0f3c1a853f8f5e61dedaf588b6f9d2da3a53b5
ms.lasthandoff: 03/31/2017


---

# <a name="search-for-products-and-product-variants-during-order-entry"></a>Ricerca di prodotti e varianti prodotto durante la registrazione ordine

Utilizzare il campo <strong>Numero articolo </strong>per cercare i prodotti e le varianti prodotto quando si crea manualmente una riga ordine cliente o una riga ordine fornitore.  In questo modo è possibile trovare rapidamente le varianti prodotto quando si dispone solo della stringa di configurazione o una delle dimensioni prodotto.

Talvolta, troppo disporre di un evento non è una migliore caso siano in e questo viene soddisfatta la condizione in particolare se si vende una serie di prodotti simili e si tenta di dover immettere i numeri di articolo o di prodotto per trovare il prodotto a destra per mettere in un ordine cliente. È possibile utilizzare ** numero di articolo ** liquidate in una riga di ordine cliente o una riga ordine fornitore nel campo di ricerca. È possibile immettere qualsiasi parte di un nome prodotto, un numero, o di una dimensione e ottenere una ricerca che mostra tutti gli articoli che corrispondono al termine di ricerca.

## <a name="how-search-works"></a>Come funziona la ricerca
Durante la ricerca dei prodotti o varianti prodotto, è importante comprendere come la funzionalità di ricerca trova i prodotti che corrispondono al testo immesso. Le regole chiave di ricerca nella fornitura dei risultati della ricerca sono:

-   I risultati della ricerca restituiranno qualsiasi record corrispondente, indipendentemente dal campo in cui il testo di ricerca viene immesso.
-   Il testo di ricerca deve essere presente nel record corrispondente nella sua interezza.
-   Una corrispondenza si verifica anche se il testo di ricerca viene trovato all'interno di una stringa di testo nel record corrispondente. Non deve apparire all'inizio di una stringa di testo.
-   Il testo di ricerca viene considerato come singola stringa di testo anche se contiene spazi vuoti.

### <a name="examples"></a>Esempi

Negli esempi seguenti vengono utilizzati prodotti e varianti prodotto per illustrare come la ricerca viene gestita in vari scenari. ** Prerequisito: ** In ** vendita e parametri &gt; di ricerca &gt; Impostazioni di marketing ** &gt; ** tipo di ricerca **, selezionare ** corrispondenza completa ** l'opzione.

| Tipo di prodotto     | Nome prodotto    | Numero prodotto visualizzato | Numero articolo | Configurazione |
|------------------|-----------------|------------------------|-------------|---------------|
| Prodotto specifico | SpeakerMidRange | D0001                  | D0001       | N/D            |
| Variante prodotto  | Active speaker  | D0010:::Nero:         | D0010       | 000005        |
| Variante prodotto  | Active speaker  | D0010:::Bianco:         | D0010       | Bianco         |

Se si digita 'speak' nel campo **Numero articolo**, si ottengono tutti i prodotti precedenti come risultato della ricerca. Se si immette 'nero' nel campo **Numero articolo**, si ottiene il secondo prodotto come risultato, perché contiene il testo 'nero' nel numero prodotto visualizzato. Questi due esempi mostrano che la ricerca viene effettuata non solo all'inizio del campo, una corrispondenza si verifica anche se il testo di ricerca viene trovato nel mezzo di una stringa di testo nel record corrispondente.  

Se si immette '05' si otterrà solo la seconda variante prodotto come risultato, poiché contiene '05' nella configurazione. Ciò dimostra che la ricerca avviene in tutti i campi abilitati nella pagina **Criteri di ricerca**.  

Se si digita 'speak 05' non si ottiene alcun risultato. Questo accase perché la ricerca cerca il testo completo immesso. La ricerca non proverà a trovare 'speak' per poi limitare i risultati a quelli contenenti '05'.  

Per limitare il numero dei risultati della ricerca utilizzando ** numero dei risultati ** liquidate ** vendita e parametri &gt; di ricerca &gt; Impostazioni di marketing ** nella pagina. Se si imposta il campo su 0, tutti i risultati della ricerca verranno restituiti. Se lo si imposta su 10, ad esempio, verranno riportati al massimo 10 risultati della ricerca.

## <a name="configure-the-product-search"></a>Configurare la ricerca di prodotti
Prima di utilizzare la funzionalità di ricerca di prodotti e varianti prodotto, attenersi alla procedura seguente per configurare la ricerca di prodotti. [![3 Passaggi per configurare la ricerca di prodotti\_AXAppFall (]. /media/3-steps-to-configure-product-search_axappfall.png)](. /media/3-steps-to-configure-product-search_axappfall.png)

### <a name="step-1-include-all-the-relevant-product-and-product-variant-identifiers-and-dimensions-in-the-search-criteria"></a>Passaggio 1: Includere tutti gli identificatori e dimensioni prodotto e variante prodotto pertinenti nei criteri di ricerca

Esempi di identificatori e dimensioni di prodotti e varianti prodotto in base a cui è possibile cercare sono **Nome prodotto, Numero articolo**, **Numero prodotto visualizzato, Configurazione, Colore, Dimensione, Stile, Nome ricerca e così via**.  

Va ** vendita e criteri &gt; di ricerca &gt; per l'impostazione di marketing ** la pagina. La pagina **Criteri di ricerca** consente di definire i criteri per il cliente, il prospect e la ricerca di prodotti. Assicurarsi di filtrare la pagina utilizzando i criteri di ricerca del prodotto. Questa operazione può essere eseguita passando a **Prodotto** nel menu della pagina.  

Per aggiungere il numero prodotto di visualizzazione dei criteri di ricerca, fare clic su ** nuovo ** il menu della pagina. Questo consentirà di aggiungere un nuovo record ** criteri di ricerca ** nella griglia. Aprire la colonna di ricerca **Nome campo** e scegliere **DisplayProductNumber**. Per aggiungere Configurazione prodotto i criteri di ricerca, creare un nuovo record ** criteri di ricerca ** nella griglia e scegliere configId ** ** ** nome del campo ** nella colonna. Nello stesso modo, creare un record con **Nome campo** **InventColorId** per la dimensione colore, **InventSizeId** per la dimensione di tipo dimensione e **InventStyleId** per la dimensione stile.

### <a name="step-2-populate-the-database-table-that-is-used-for-product-search"></a>Passaggio 2: Popolare la tabella di database utilizzata per la ricerca di prodotti

Nella pagina **Criteri di ricerca**, fare clic sul pulsante **Aggiorna dati ricerca**. Nella finestra di dialogo **Aggiorna dati ricerca** assicurarsi che **Origine** sia impostato su **Prodotto**e fare clic su **OK**. Il sistema aggregherà in una tabella tutti i criteri di ricerca selezionati specificato nel passaggio 1. Se si dispone di molti prodotti e varianti prodotto, questa operazione può essere sufficienti lunga ed è possibile ricevere un avviso. Si consiglia di programmare la popolazione della tabella di ricerca nel server batch in un momento in cui il server non è troppo occupato.  

Finché la tabella non viene popolata, la ricerca di prodotti non fornirà i risultati corretti. Se non viene visualizzato alcun risultato di ricerca, verificare che la tabella sia popolata.  

La tabella deve essere popolata solo quando i criteri di ricerca viene modificato. I prodotti e le varianti appena rilasciati vengono aggiunti automaticamente alla tabella. I prodotti e le varianti eliminati vengono rimossi automaticamente dalla tabella.

### <a name="step-3-enable-the-lookup-for-product-search-on-sales-and-purchase-order-lines"></a>Passaggio 3: abilitare la ricerca di prodotti nelle righe ordine cliente e ordine fornitore

È possibile attivare questa funzionalità verranno ** vendita e parametri &gt; di ricerca &gt; Impostazioni di marketing ** e da impostazione ** attivare la ricerca per la ricerca ** ** Sì ** ** dettagli relativi all'identificazione ** nella scheda.  

Per l'immissione riga ordine cliente, il comportamento predefinito è di aprire la pagina **Ricerca prodotto** quando si inizia a digitare nel campo **Numero articolo** e quindi premere il tasto **TAB**. La pagina **Ricerca prodotto** cambia il contesto durante la creazione della riga ordine e può essere considerata inutilmente intrusiva. Se si preferisce visualizzare i risultati della ricerca in una ricerca e non perdere il contesto durante l'immissione riga ordine, è possibile utilizzare invece la ricerca esterna. Se si cerca un prodotto o una variante prodotto, ma non viene selezionata alcuna informazione nella ricerca e si preme il tasto **TAB**, viene visualizzata la pagina **Ricerca prodotto**.



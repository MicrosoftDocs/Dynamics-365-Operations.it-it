---
title: Cercare prodotti e clienti in POS
description: "Questo argomento fornisce una panoramica dei miglioramenti apportati alla funzionalità di ricerca prodotti e clienti in Dynamics 365 for Retail."
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 08/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 141393
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: Retail April 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 5f6f9a02b20549a75941d367c1b46e3439360078
ms.contentlocale: it-it
ms.lasthandoff: 01/19/2018

---

# <a name="overview-of-product-and-customer-search-in-point-of-sale"></a>Panoramica sulla funzionalità di ricerca prodotti e clienti in POS

Modern POS (MPOS) e POS cloud (CPOS) forniscono una funzionalità di ricerca di facile utilizzo che consente ai dipendenti dei punti vendita di cercare rapidamente prodotti e clienti. La barra di ricerca è sempre presente nella parte superiore di MPOS e CPOS, di modo che i dipendenti possano trovare rapidamente prodotti e clienti.

I dipendenti possono cercare i prodotti negli assortimenti e nei cataloghi associati al punto vendita corrente e negli assortimenti e nei cataloghi associati a qualsiasi altro punto vendita della società. Di conseguenza, i cassieri possono vendere e restituire prodotti al di fuori dell'assortimento del punto vendita. Analogamente, i dipendenti possono cercare i clienti associati al punto vendita corrente o a qualsiasi altro punto vendita della società. Inoltre, i dipendenti possono cercare i clienti associati a un'altra società nell'organizzazione padre.

## <a name="product-search"></a>Ricerca prodotto 

Per impostazione predefinita, una ricerca prodotto viene effettuata nell'assortimento del punto vendita. Questo tipo di ricerca è denominata *ricerca prodotto locale*. Tuttavia, i dipendenti possono passare facilmente a qualsiasi catalogo associato al punto vendita corrente, oppure possono effettuare una ricerca in un altro punto vendita. Questo tipo di ricerca è denominata *ricerca prodotto remota*. Per cambiare il catalogo, selezionare il pulsante **Categorie** nella parte sinistra della pagina. Nella parte superiore del riquadro visualizzato, selezionare il pulsante **Cambia catalogo** e selezionare il catalogo in cui effettuare la ricerca. Il sistema cercherà i prodotti nel catalogo selezionato.

Nella pagina **Cambia catalogo**, i dipendenti possono selezionare facilmente qualsiasi punto vendita, oppure possono cercare prodotti in tutti i punti vendita.

![Cambiare il catalogo](./media/Changecatalog.png "Cambiare il catalogo")
 
Una ricerca prodotto locale esegue la ricerca nelle seguenti proprietà di prodotto:

- Numero prodotto
- Nome prodotto
- descrizione
- Dimensioni
- Codice a barre
- Nome di ricerca

### <a name="enhancements-to-local-product-searches"></a>Miglioramenti alle ricerche prodotto locali

Le ricerche prodotto locali sono ora più facili e intuitive. Sono state apportati i seguenti miglioramenti:

- Menu a discesa per clienti e prodotti sono stati stati aggiunti alla barra di ricerca, di modo che i dipendenti possano selezionare **Prodotto** o **Cliente** prima di eseguire la ricerca. **Prodotto** è l'impostazione predefinita, come illustrato di seguito.
- Per le ricerche con più parole chiave (ovvero le ricerche che utilizzano termini di ricerca), i rivenditori possono stabilire se i risultati della ricerca includono i risultati corrispondenti a qualsiasi termine di ricerca o solo i risultati che corrispondono a tutti i termini di ricerca. Questa impostazione è disponibile nel profilo della funzionalità POS, in un nuovo gruppo denominato **Ricerca prodotto**. L'impostazione predefinita è **Abbina alcuni termini di ricerca**. Questa impostazione è quella consigliata. Se si utilizza l'impostazione **Abbina alcuni termini di ricerca**, la ricerca restituisce tutti i prodotti che corrispondono completamente o parzialmente a uno o più termini di ricerca e i risultati vengono automaticamente elencati in ordine crescente a partire dai prodotti che hanno il maggior numero di corrispondenze (totali o parziali) con le parole chiave.

    L'impostazione **Abbina tutti i termini di ricerca** restituisce solo i prodotti che corrispondono (completamente o parzialmente) a tutti i termini di ricerca. Questa impostazione è utile quando i nomi dei prodotti sono lunghi e i dipendenti desiderano visualizzare solo una parte dei nomi nei risultati della ricerca. Questo tipo di ricerca presenta tuttavia due limiti:

    - La ricerca viene effettuata in singole proprietà di prodotto. Ad esempio, vengono restituiti solo i prodotti che hanno tutte le parole chiave cercate in almeno una proprietà di prodotto.
    - La ricerca non viene eseguita nelle dimensioni.

- I rivenditori possono ora configurare la ricerca prodotto in modo da visualizzare suggerimenti di ricerca mentre gli utenti digitano nomi di prodotti. Una nuova impostazione per questa funzionalità è disponibile nel profilo della funzionalità POS, in un nuovo gruppo denominato **Ricerca prodotto**. L'impostazione è denominata **Mostra suggerimenti di ricerca durante la digitazione**. Questa funzionalità può consentire ai dipendenti di trovare rapidamente il prodotto che stanno cercando, in quanto non devono digitarne il nome completo.
- L'algoritmo di ricerca prodotto ora cerca i termini anche nella proprietà **Nome di ricerca** del prodotto.

![Suggerimenti su prodotti](./media/Productsuggestions.png "Suggerimenti su prodotti")

## <a name="customer-search"></a>Ricerca cliente

La ricerca cliente viene utilizzata per trovare clienti per vari scopi. Ad esempio, i cassieri potrebbero aver bisogno di visualizzare l'elenco preferenze o lo storico degli acquisti di un cliente o aggiungere il cliente a una transazione. In caso di ricerche con molteplici parola chiave, l'algoritmo di ricerca cliente restituisce tutti i clienti corrispondenti a una qualsiasi delle parole chiave cercate. Tuttavia, i clienti con il maggior numero di corrispondenze sono visualizzati nella parte superiore dei risultati. Questo comportamento è analogo a quello di altri motori di ricerca, i quali mostrano dapprima i risultati corrispondenti alla maggior parte dei termini cercati e quindi quelli con corrispondenze parziali alle parole chiave di ricerca. Questo comportamento è utile per i cassieri nei casi in cui utilizzano più parole chiave per la ricerca, ma una delle parole chiave presenta un errore ortografico.

Per impostazione predefinita, una ricerca cliente viene eseguita nelle rubriche clienti associate al punto vendita. Questo tipo di ricerca è denominata *ricerca cliente locale*. Tuttavia, i dipendenti possono anche cercare i clienti globalmente. In altre parole, possono effettuare la ricerca nei punti vendita della società e in tutte le altre persone giuridiche. Questo tipo di ricerca è denominata *ricerca cliente remota*.

Per effettuare una ricerca globale, i dipendenti possono selezionare il pulsante **Risultati filtro** nella parte inferiore della pagina e quindi selezionare l'opzione **Cerca in tutti i punti vendita**, come illustrato nella figura di seguito. In questo caso, non vengono restituiti solo i clienti, ma anche tutti i tipi di parti incluse in qualsiasi rubrica nella sede centrale. Queste parti includono lavoratori, fornitori, contatti e concorrenti.

> [!NOTE]
> È necessario immettere almeno quattro caratteri perché una ricerca cliente remota restituisca dei risultati.

In una ricerca cliente remota, l'ID cliente non è visualizzato per i clienti di altre persone giuridiche, poiché nessun ID cliente è stata creato per quelle parti nella società corrente. Tuttavia, se un dipendente apre la pagina dei dettagli del cliente, il sistema genera automaticamente un ID cliente per la parte e inoltre associa la rubrica clienti del punto vendita al cliente. Di conseguenza, il cliente sarà visibile nelle ricerche dei punti vendita locali eseguite successivamente.

![Ricerca cliente globale](./media/Globalcustomersearch.png "Ricerca cliente globale")

### <a name="enhancements-to-local-customer-searches"></a>Miglioramenti alle ricerche cliente locali

Le ricerche cliente locali consentono ai dipendenti di trovare rapidamente i clienti per numero di telefono. I dipendenti non devono digitare eventuali caratteri speciali aggiunti al numero di telefono del cliente, ad esempio spazi, trattini o parentesi. Sebbene i cassieri siano in grado di archiviare numeri di telefono in qualsiasi formato (ad esempio, con parentesi, trattini, simboli e così via), possono cercare i clienti digitando un numero di telefono parziale. Se un cassiere ha incluso dei caratteri speciali in un numero di telefono, gli altri cassieri possono trovare il cliente digitando le cifre visualizzate dopo i caratteri speciali. Ad esempio, se il numero di telefono di un cliente è stato immesso come **123-456-7890**, un cassiere può cercare il cliente digitando **123**, **456**, **7890** o **1234567890** oppure immettendo le prime cifre del numero telefonico.


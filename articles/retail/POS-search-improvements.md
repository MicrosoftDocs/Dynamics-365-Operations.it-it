---
title: Ricerca di prodotti e di clienti nel POS
description: Questo argomento fornisce una panoramica dei miglioramenti apportati alla funzionalità di ricerca prodotti e clienti in Microsoft Dynamics 365 for Retail.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 03/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: Retail April 2017 update
ms.openlocfilehash: a1593445af41cba30bdc35933302d0873e313585
ms.sourcegitcommit: 0bd0215d0735ed47b1b8af93a80bcdbf7ca2cc49
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2019
ms.locfileid: "789871"
---
# <a name="product-search-and-customer-search-in-the-point-of-sale-pos"></a>Ricerca di prodotti e di clienti nel POS

[!include [banner](includes/banner.md)]

Modern POS (MPOS) e POS cloud (CPOS) forniscono una funzionalità di ricerca di facile utilizzo che consente di cercare prodotti e clienti. Dal momento che la barra di ricerca è sempre presente nella parte superiore delle finestre MPOS e CPOS, i dipendenti possono trovare rapidamente prodotti e clienti.

I dipendenti possono cercare i prodotti negli assortimenti e nei cataloghi associati al punto vendita corrente. Possono inoltre cercare negli assortimenti e nei cataloghi associati a qualsiasi altro punto vendita della società. Di conseguenza, i cassieri possono vendere e restituire prodotti al di fuori dell'assortimento del punto vendita. Analogamente, i dipendenti possono cercare i clienti che sono associati al punto vendita corrente o a qualsiasi altro punto vendita della società. Inoltre, i dipendenti possono cercare i clienti che sono associati a un'altra società nell'organizzazione padre.

## <a name="product-search"></a>Ricerca prodotto

Per impostazione predefinita, le ricerche dei prodotti vengono effettuate nell'assortimento del punto vendita. Questo tipo di ricerca è denominata *ricerca prodotto locale*. Tuttavia, i dipendenti possono passare facilmente a qualsiasi catalogo associato al punto vendita corrente, oppure possono effettuare una ricerca in un altro punto vendita. Questo tipo di ricerca è denominata *ricerca prodotto remota*. Per cambiare il catalogo, selezionare il pulsante **Categorie** nella parte sinistra della pagina. Nella parte superiore del riquadro visualizzato, selezionare il pulsante **Cambia catalogo** e selezionare il catalogo in cui effettuare la ricerca. Il sistema cercherà i prodotti nel catalogo selezionato.

Nella pagina **Cambia catalogo**, i dipendenti possono selezionare facilmente qualsiasi punto vendita, oppure possono cercare prodotti in tutti i punti vendita.

![Cambiare il catalogo](./media/Changecatalog.png "Cambiare il catalogo")
 
Una ricerca di prodotto locale esegue la ricerca nelle seguenti proprietà di prodotto:

- Numero prodotto
- Nome prodotto
- descrizione
- Dimensioni
- Codice a barre
- Nome di ricerca

### <a name="enhancements-to-local-product-searches"></a>Miglioramenti alle ricerche prodotto locali

Le ricerche di prodotto locali sono ora più facili e intuitive. Sono state apportati i seguenti miglioramenti:

- Menu a discesa per clienti e prodotti sono stati stati aggiunti alla barra di ricerca, di modo che i dipendenti possano selezionare **Prodotto** o **Cliente** prima di eseguire la ricerca. **Prodotto** è l'impostazione predefinita, come illustrato di seguito.
- Per le ricerche con più parole chiave (ovvero le ricerche che utilizzano termini di ricerca), i rivenditori possono stabilire se i risultati della ricerca includono i risultati corrispondenti a *qualsiasi* termine di ricerca o solo i risultati che corrispondono a *tutti* i termini di ricerca. Questa impostazione è disponibile nel profilo della funzionalità POS, in un nuovo gruppo denominato **Ricerca prodotto**. L'impostazione predefinita è **Abbina alcuni termini di ricerca**. Questa impostazione è quella consigliata. Quando si utilizza l'impostazione **Abbina alcuni termini di ricerca**, nei risultati vengono restituiti tutti i prodotti che corrispondono completamente o parzialmente a uno o più termini di ricerca. Tali risultati vengono ordinati automaticamente in ordine crescente in base ai prodotti che hanno il maggior numero di corrispondenze (complete o parziali) con le parole chiave.

    L'impostazione **Abbina tutti i termini di ricerca** restituisce solo i prodotti che corrispondono (completamente o parzialmente) a tutti i termini di ricerca. Questa impostazione è utile quando i nomi dei prodotti sono lunghi e i dipendenti desiderano visualizzare solo una parte dei nomi nei risultati della ricerca. Questo tipo di ricerca presenta tuttavia due limiti:

    - La ricerca viene effettuata in singole proprietà di prodotto. Ad esempio, vengono restituiti solo i prodotti che hanno tutte le parole chiave cercate in almeno una proprietà di prodotto.
    - La ricerca non viene eseguita nelle dimensioni.

- I rivenditori possono ora configurare la ricerca prodotto in modo da visualizzare suggerimenti di ricerca mentre gli utenti digitano nomi di prodotti. Una nuova impostazione per questa funzionalità è disponibile nel profilo della funzionalità POS, in un gruppo denominato **Ricerca prodotto**. L'impostazione è denominata **Mostra suggerimenti di ricerca durante la digitazione**. Questa funzionalità può consentire ai dipendenti di trovare rapidamente il prodotto che stanno cercando, in quanto non devono digitarne il nome completo.
- L'algoritmo di ricerca prodotto ora cerca i termini anche nella proprietà **Nome di ricerca** del prodotto.

    ![Suggerimenti su prodotti](./media/Productsuggestions.png "Suggerimenti su prodotti")

## <a name="customer-search"></a>Ricerca cliente

La ricerca cliente viene utilizzata per trovare clienti per vari scopi. Ad esempio, i cassieri potrebbero aver bisogno di visualizzare l'elenco preferenze o lo storico degli acquisti di un cliente o aggiungere il cliente a una transazione. L'algoritmo di ricerca abbina i termini di ricerca ai valori presenti nelle seguenti proprietà cliente: nome, posta elettronica, telefono, numero di carta fedeltà, indirizzo e numero di conto. Tra queste, la proprietà Nome fornisce la maggiore flessibilità in caso di ricerche con molteplici parole chiave in quanto l'algoritmo restituisce tutti i clienti che corrispondono a una qualsiasi delle parole chiave di ricerca e quelli che presentano il maggior numero di corrispondenze con le parole chiave sono visualizzati nella parte superiore dei risultati. Questo comportamento è utile ai cassieri nelle situazioni in cui effettuano ricerche digitando il nome completo e il cognome e il nome sono stati scambiati durante l'immissione iniziale dei dati. Tuttavia, per motivi di prestazioni, tutte le altre proprietà preservano l'ordine delle parole chiave di ricerca, quindi se queste non corrispondono all'ordine in cui i dati sono archiviati, non verrà restituito alcun risultato.

Per impostazione predefinita, una ricerca cliente viene eseguita nelle rubriche clienti associate al punto vendita. Questo tipo di ricerca è denominata *ricerca cliente locale*. Tuttavia, i dipendenti possono anche cercare i clienti globalmente. In altre parole, possono effettuare la ricerca nei punti vendita della società e in tutte le altre persone giuridiche. Questo tipo di ricerca è denominata *ricerca cliente remota*.

Per effettuare una ricerca globale, i dipendenti possono selezionare il pulsante **Risultati filtro** nella parte inferiore della pagina e quindi selezionare l'opzione **Cerca in tutti i punti vendita**, come illustrato nella figura di seguito. In questo caso, non vengono restituiti solo i clienti, ma anche tutti i tipi di parti incluse in qualsiasi rubrica nella sede centrale. Queste parti includono lavoratori, fornitori, contatti e concorrenti.

> [!NOTE]
> È necessario immettere almeno quattro caratteri perché una ricerca cliente remota restituisca dei risultati.

In una ricerca cliente remota, l'ID cliente non è visualizzato per i clienti di altre persone giuridiche, poiché nessun ID cliente è stata creato per quelle parti nella società corrente. Tuttavia, se un dipendente apre la pagina dei dettagli del cliente, il sistema genera automaticamente un ID cliente per la parte e inoltre associa la rubrica clienti del punto vendita al cliente. Di conseguenza, il cliente sarà visibile nelle ricerche dei punti vendita locali eseguite successivamente.

![Ricerca cliente globale](./media/Globalcustomersearch.png "Ricerca cliente globale")

### <a name="enhancements-to-local-customer-search"></a>Miglioramenti alla ricerca cliente locale

Sono state semplificate le ricerche che si basano sul numero di telefono. Queste ricerche ignorano ora i caratteri speciali, ad esempio spazi, trattini e parentesi, che potrebbero essere stati aggiunti al momento della creazione del cliente. Di conseguenza, i cassieri non devono preoccuparsi del formato del numero di telefono durante la ricerca. Possono inoltre cercare i clienti digitando parte del numero di telefono. Se un numero di telefono include caratteri speciali, può essere trovato anche cercando nei numeri che vengono visualizzati dopo i caratteri speciali. Ad esempio, se il numero di telefono di un cliente è stato immesso come **123-456-7890**, un cassiere può cercare il cliente digitando **123**, **456**, **7890** o **1234567890** oppure digitando le prime cifre del numero di telefono.

La ricerca tradizionale dei clienti può richiedere molto tempo, poiché esegue la ricerca in più campi. I cassieri possono ora effettuare una ricerca in una singola proprietà personalizzata, ad esempio il nome, l'indirizzo di posta elettronica o il numero di telefono. Le proprietà dell'algoritmo di ricerca del cliente sono collettivamente note come *criteri di ricerca del cliente*. L'amministratore di sistema può facilmente configurare uno o più criteri come collegamenti da visualizzare nel POS. Poiché la ricerca è limitata a un unico criterio, vengono visualizzati solo i risultati della ricerca pertinenti, pertanto le prestazioni sono molto superiori rispetto a quelle di una ricerca standard del cliente. La figura riportata di seguito mostra i collegamenti di ricerca del cliente nel POS.

![Collegamenti di ricerca del cliente](./media/SearchShortcutsPOS.png "Collegamenti di ricerca del cliente")

Per impostare i criteri di ricerca come collegamenti, l'amministratore deve aprire la pagina **Parametri di vendita** al dettaglio in Microsoft Dynamics 365 for Finance and Operations, quindi, nella scheda **Criteri di ricerca POS**, selezionare tutti i criteri che devono essere mostrati come collegamenti.

![Configurare i collegamenti di ricerca](./media/ConfigureShortcutsAX.png "Configurare i collegamenti di ricerca")

> [!NOTE]
> Se si aggiungono troppi collegamenti, il menu a discesa nella barra della ricerca nel POS non riesce a visualizzarli correttamente a scapito della ricerca da parte del dipendente. Si consiglia di aggiungere solo i collegamenti necessari.

Il campo **Ordine di visualizzazione** determina l'ordine in cui i collegamenti vengono visualizzati nel POS. I criteri che vengono visualizzati sono le proprietà predefinite utilizzate dall'algoritmo di ricerca del cliente per cercare i clienti. Tuttavia, i partner possono aggiungere proprietà personalizzate come collegamenti di ricerca. Per aggiungere proprietà personalizzate come collegamenti di ricerca, l'amministratore di sistema deve estendere l'enumerazione (enum) estendibile utilizzata per i criteri di ricerca del cliente e quindi contrassegnare le proprietà personalizzate del partner come collegamenti. I partner sono responsabili della scrittura del codice per trovare i risultati derivanti dall'utilizzo dei collegamenti personalizzati.

> [!NOTE]
> Una proprietà personalizzata che viene aggiunta all'enumerazione non influisce sull'algoritmo predefinito di ricerca del cliente. In altre parole, l'algoritmo di ricerca del cliente non cerca nella proprietà personalizzata. Gli utenti possono utilizzare una proprietà personalizzata per le ricerche solo se la proprietà personalizzata viene aggiunta come collegamento o se l'algoritmo di ricerca predefinito viene sovrascritto.

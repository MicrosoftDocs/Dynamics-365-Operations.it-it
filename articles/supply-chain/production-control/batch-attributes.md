---
title: Attributi batch
description: Questo argomento fornisce informazioni sugli attributi batch. Gli attributi batch sono caratteristiche delle materie prime e dei prodotti finiti che costituiscono i lotti di magazzino. L'argomento illustra inoltre come assegnare gli attributi batch e come cercarli quando si prenotano i batch.
author: ShylaThompson
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PdsBatchAttrib, PdsBatchAttribAssociate, PdsBatchAttribByAttribGroup, PdsBatchAttribByItem, PdsBatchAttribByitemCustomer, PdsBatchAttribGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19271
ms.assetid: 41de0250-4a96-412e-a412-aa06615b6b1d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 325e647185e3eb4c0eacdfd00c320804e31ddb48
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555887"
---
# <a name="batch-attributes"></a>Attributi batch

[!include [banner](../includes/banner.md)]

Questo argomento fornisce informazioni sugli attributi batch. Gli attributi batch sono caratteristiche delle materie prime e dei prodotti finiti che costituiscono i lotti di magazzino. L'argomento illustra inoltre come assegnare gli attributi batch e come cercarli quando si prenotano i batch.

Gli attributi batch sono caratteristiche delle materie prime e dei prodotti finiti che costituiscono i lotti di magazzino. Gli attributi lotto possono variare in base a diversi fattori, ad esempio le condizioni ambientali o la qualità delle materie prime utilizzate per produrre il lotto. Il numero e i tipi degli attributi batch utilizzati possono variare notevolmente da un settore a un altro. Di seguito vengono riportati due esempi di utilizzo degli attributi batch:

-   Nel settore caseario il latte, ovvero una delle materie prime utilizzate per la produzione del formaggio, potrebbe essere associato ad attributi quali contenuto di grasso e peso percentuale. Il formaggio prodotto dal latte può essere associato ad altri attributi, ad esempio umidità ed età.
-   Nel settore dell'acciaieria il ferro prodotto potrebbe essere associato ad attributi quali le percentuali di contenuto di magnesio, di argento e di zinco.

Per gestire meglio il numero e i tipi di attributi, è possibile utilizzare i gruppi di attributi batch. In questo modo, non è necessario aggiungere ogni attributo singolarmente.

## <a name="assign-batch-attributes"></a>Assegnare attributi batch
È possibile assegnare attributi batch a singoli articoli contenuti in lotti di magazzino oppure è possibile assegnarli agli articoli associati a clienti specifici. Prima di poter assegnare un attributo batch al livello del cliente, è necessario assegnarlo al livello dell'articolo. Per l'articolo la dimensione del batch deve essere impostata su **attiva** nel gruppo di dimensioni di tracciabilità. Per assegnare un attributo batch a un singolo articolo, utilizzare il modulo Specifico del prodotto. Se l'attributo è specifico di un articolo per un cliente, utilizzare il modulo Specifico del cliente. Quando si aggiunge un attributo a un articolo, si definiscono anche altri parametri. Di seguito sono riportati alcuni esempi.

-   Intervalli minimo e massimo per un attributo di tipo **Intero** o **Frazione**.
-   Azioni tolleranza per un attributo di tipo **Intero** o **Frazione**. L'azione può essere un messaggio di avviso o un messaggio di errore se il valore dell'attributo non rientra nell'intervallo minimo e massimo.
-   Valore di destinazione per l'attributo. Si tratta del valore ottimale dell'attributo ed è applicabile a tutti i tipi di attributo.

È possibile accedere a queste pagine per i prodotti selezionati nella pagina elenco **Prodotti rilasciati** in Gestione informazioni sul prodotto. Dopo avere assegnato attributi batch a un prodotto, è possibile aggiungere valori specifici agli attributi nella pagina **Attributi lotto di magazzino**.

## <a name="reserve-batches"></a>Prenotazione di batch
È possibile eseguire ricerche negli attributi batch quando si eseguono prenotazioni batch per un ordine cliente allo scopo di evadere l'ordine di un cliente, o quando si prelevano e si prenotano batch per un ordine di produzione. La ricerca consente di trovare il lotto di magazzino che contiene il prodotto con gli attributi batch desiderati. Dopo aver trovato il batch, è possibile prenotare l'articolo sulla riga di transazione di magazzino di origine.




---
title: Gestione dell'assortimento
description: In questo argomento vengono descritti i concetti di base della gestione dell'assortimento in Dynamics 365 Commerce e vengono fornite considerazioni relative all'implementazione per il progetto.
author: jblucher
manager: AnnBe
ms.date: 03/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Retail, Operations
ms.search.region: Global
ms.author: jeffbl
ms.search.validFrom: 2017-11-21
ms.dyn365.ops.version: Application update 5
ms.openlocfilehash: e1b177989065740eef0bd917a7ce1e0a2c79088b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413382"
---
# <a name="assortment-management"></a>Gestione dell'assortimento

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Panoramica

In Dynamics 365 Commerce sono disponibili *assortimenti* che consentono di gestire la disponibilità di prodotto tramite i canali. Gli assortimenti determinano quali prodotti sono disponibili in specifici punti vendita e durante un periodo specifico.

In Commerce, un assortimento è un mapping di uno o più canali (o gruppi di canali, se le gerarchie organizzative vengono utilizzate) a uno o più prodotti (o gruppi di prodotti, se le gerarchie di categorie vengono utilizzate).

La combinazione generale dei prodotti di un canale è determinata dagli assortimenti pubblicati assegnati al canale. Di conseguenza, è possibile configurare più assortimenti attivi per canale.

### <a name="basic-assortment-setup"></a>Impostazione degli assortimenti di base

Nel seguente esempio, un assortimento univoco è configurato per ogni punto vendita. In questo caso, solo il prodotto 1 è disponibile presso il punto vendita 1 e solo il prodotto 2 è disponibile presso il punto vendita 2.

![Ciascun prodotto è disponibile in un punto vendita](./media/Managing-assortments-figure1.png)

Per rendere disponibile il prodotto 2 presso il punto vendita 1, è possibile aggiungere il prodotto all'assortimento 1.

![Prodotto 2 aggiunto all'assortimento 1](./media/Managing-assortments-figure2.png)

In alternativa, è possibile aggiungere il punto vendita 1 all'assortimento 2.

![Punto vendita 1 aggiunto all'assortimento 2](./media/Managing-assortments-figure3.png)

### <a name="organization-hierarchies"></a>Gerarchie organizzative

Nelle situazioni in cui più canali condividono gli stessi assortimenti di prodotto, è possibile configurare gli assortimenti utilizzando la gerarchia organizzativa dell'assortimento di articoli di Commerce. Quando i nodi di questa gerarchia vengono aggiunti, tutti i canali nel nodo e i relativi nodi figlio verranno inclusi.

![Gerarchia organizzativa](./media/Managing-assortments-figure4.png)

### <a name="product-categories"></a>Categorie prodotti

Analogamente, dal lato del prodotto, è possibile includere i gruppi di prodotti utilizzando le gerarchie di categorie di prodotti. È possibile configurare gli assortimenti includendo uno o più nodi di gerarchia di categorie. In questo caso, l'assortimento includerà tutti i prodotti nel nodo di categoria e nei relativi nodi figlio.

![Categorie prodotti](./media/Managing-assortments-figure5.png)

### <a name="excluded-products-or-categories"></a>Categorie o prodotti esclusi

Oltre a includere prodotti e categorie negli assortimenti, è possibile utilizzare l'opzione di esclusione per definire categorie o prodotti specifici da escludere dagli assortimenti. Nel seguente esempio, si desidera includere tutti i prodotti in una categoria specifica, ad eccezione del prodotto 2. In questo caso, non è necessario definire il prodotto in assortimento per prodotto o creare nodi di categoria aggiuntivi. È possibile invece solo includere la categoria, ma escludere il prodotto.

> [!NOTE]
> Se un prodotto viene incluso ed escluso in uno o più assortimenti per definizione, il prodotto verrà considerato sempre escluso.

![Prodotti esclusi](./media/Managing-assortments-figure6.png)

### <a name="global-and-released-products"></a>Prodotti rilasciati e globali

Gli assortimenti vengono definiti a livello globale e possono contenere canali da più persone giuridiche. Anche i prodotti e le categorie inclusi in assortimenti vengono condivisi tra persone giuridiche. Tuttavia, un prodotto deve essere rilasciato per poter essere effettivamente venduto, ordinato, conteggiato o ricevuto nel canale (ad esempio, nel POS \[POS\]). Di conseguenza, anche se due punti vendita in persone giuridiche diverse possono suddividere un assortimento contenente gli stessi prodotti, i prodotti sono disponibili solo se sono stati rilasciati a tali persone giuridiche.

### <a name="dynamic-and-static-assortments"></a>Assortimenti dinamici e statici

Gli assortimenti possono essere definiti con prodotti e canali specifici o includendo le categorie e le unità organizzative. Gli assortimenti che includono riferimenti a questi gruppi vengono considerati assortimenti dinamici. Se la definizione o il contenuto di questi gruppi cambia mentre l'assortimento è attivo, verrà modificata anche la definizione dell'assortimento.

Ad esempio, un assortimento è originariamente definito e pubblicato in modo che faccia riferimento a una categoria di prodotti. Se ulteriori prodotti vengono aggiunti successivamente alla categoria, tali prodotti vengono inclusi automaticamente nella definizione dell'assortimento esistente. Non è necessario aggiungere manualmente i prodotti all'assortimento. Analogamente, se un'unità organizzativa viene aggiunta a un nodo diverso, l'assortimento dell'unità organizzativa viene rettificato automaticamente in base a tale definizione.

### <a name="stopped-products"></a>Prodotti interrotti

È possibile "interrompere" i prodotti rilasciati per il processo di vendita accendendo un'impostazione nelle impostazioni **Ordine predefinito**. Questa impostazione è utilizzata soprattutto quando un prodotto è alla fine del ciclo di vita e non deve essere venduto ad alcun canale. Gli assortimenti rispettano questa impostazione e i prodotti interrotti non vengono inclusi negli assortimenti, indipendentemente dalla configurazione dell'assortimento.

### <a name="blocked-products"></a>Prodotti bloccati

Oltre a interrompere le vendite di un prodotto, è possibile bloccare temporaneamente le vendite di un prodotto. È possibile configurare questa impostazione della scheda **Commerce** di un prodotto rilasciato. I prodotti bloccati vengono comunque inclusi negli assortimenti, ma verrà visualizzato un messaggio nel POS in cui viene indicato che il prodotto non può essere venduto.

### <a name="date-effectivity"></a>Validità della data

Gli assortimenti hanno una data di validità. Di conseguenza, i rivenditori possono configurare quando i prodotti devono o non devono essere disponibili per canale. È possibile definire e pubblicare gli assortimenti prima del tempo e specificare le date di inizio e di fine. I prodotti diventeranno automaticamente disponibili o non disponibili nelle date specificate.

### <a name="process-assortments-batch-job"></a>Elaborazione del processo batch degli assortimenti

Per renderli effettivi, gli assortimenti definiti in Commerce devono essere elaborati. Questa elaborazione viene effettuata per i seguenti motivi:

- Le definizioni degli assortimenti devono essere de-normalizzate in modo che i canali possano utilizzarle più facilmente. Una combinazione di prodotti per un canale può essere definita tramite più assortimenti che coprono diversi intervalli di date. Se alcune di queste informazioni vengono calcolate prima del tempo sul server, le prestazioni sul canale vengono migliorate.
- I prodotti e i canali nell'assortimento possono cambiare al di fuori dell'assortimento stesso. Gli assortimenti dinamici contenenti riferimenti a categorie o a unità organizzative devono essere elaborati periodicamente affinché includano o escludano record, in base alla loro assegnazione corrente.

## <a name="implementation-considerations"></a>Considerazioni sull'implementazione

Considerare i seguenti requisiti di implementazione quando si pianificano e si gestiscono gli assortimenti per l'implementazione di Commerce:

- **Replica dati e dimensioni di database** - Gli assortimenti contribuiscono a rispondere alle esigenze aziendali per gestire la disponibilità di prodotto, ma costituiscono anche uno strumento importante per la gestione delle dimensioni dei database offline e del canale. Gli assortimenti ben gestiti consentono di ridurre la quantità di dati da elaborare e replicare sui database offline e del canale. Consentono inoltre di limitare il numero dei record da rendere persistenti. Un numero inferiore di record in questi database aumenta le prestazioni quando si aggiungono articoli a una transazione o quando si cercano prodotti.
- **Assortimenti in scadenza/con data di validità** - Uno degli strumenti più validi per la gestione del numero di prodotti nei database offline e del canale è la validità della data degli assortimenti. Se si lasciano assortimenti aperti (senza scadenza) per prodotti stagionali o prodotti che sono alla fine del ciclo di vita, questi database si svilupperanno in modo illimitato. È possibile utilizzare diversi metodi per la gestione di questa situazione. Ad esempio, è possibile gestire assortimenti distinti per prodotti stagionali e prodotti che sono sempre disponibili.
- **Vendite e resi esterni agli assortimenti** - Questa funzionalità aiuta i rivenditori a gestire con efficacia gli assortimenti consentendo loro di limitare i prodotti disponibili a quelli appartenenti alla combinazione di prodotti di base per il punto vendita. Questa funzione consente inoltre ai rivenditori di gestire situazioni in cui un prodotto è stato omesso erroneamente da un assortimento o in cui un prodotto viene restituito al di fuori delle date di validità per l'assortimento.

Se i dati del prodotto non sono presenti nel database del canale, il POS effettua le chiamate in tempo reale alla sede centrale per recuperare le informazioni necessarie, in modo che il prodotto possa essere venduto, restituito o aggiunto a un ordine cliente. Le informazioni sul prodotto recuperate in questo modo sono disponibili solo nell'ambito della transazione. Il prodotto non viene aggiunto alla definizione dell'assortimento. Di conseguenza, le chiamate in tempo reale successive verranno eseguite in base alle esigenze.

---
title: Creare un catalogo del servizio clienti
description: Questo articolo fornisce una panoramica del processo per creare un catalogo per un call center.
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 16212
ms.assetid: c9d1b9df-82e8-4b3a-a13c-166df8b9718e
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 857d280ab6d846c19102dd053a2c5f27fe14654c
ms.lasthandoff: 03/31/2017


---

# <a name="create-a-call-center-catalog"></a>Creare un catalogo del servizio clienti

[!include[banner](includes/banner.md)]


Questo articolo fornisce una panoramica del processo per creare un catalogo per un call center. 

In un servizio clienti è possibile utilizzare i cataloghi dei prodotti per identificare quelli che si desidera offrire ai clienti. In genere nei servizi clienti vengono utilizzati i cataloghi stampati. La progettazione e la produzione di un catalogo stampato viene gestita al di fuori di Microsoft Dynamics 365 for Operations. Tuttavia, è possibile creare e archiviare un formato digitale di un catalogo in Vendita al dettaglio e commercio in Dynamics 365 for Operations utilizzando gli stessi moduli che si utilizzano per impostare i cataloghi al dettaglio online. Prima di poter creare un catalogo, è necessario impostare gli assortimenti dei prodotti e assegnare gli assortimenti a un servizio clienti. Successivamente, è possibile aggiungere i prodotti al catalogo selezionandoli da questi assortimenti. Al termine dell'aggiunta dei prodotti al catalogo e del completamento del catalogo, è necessario convalidare quest'ultimo per verificare i dati. Successivamente, è necessario inviare il catalogo per la revisione e l'approvazione. Dopo l'approvazione, il catalogo può essere pubblicato. Quando viene creato un catalogo del servizio clienti, è possibile acquisire uno snapshot dei dati del catalogo al momento della pubblicazione. Questa funzionalità dello snapshot consente di accedere a una determinata versione del catalogo anche se quest'ultimo viene modificato e aggiornato in un secondo momento. I cataloghi dei servizi clienti possono inoltre essere configurati per includere le funzionalità facoltative riportate di seguito.

-   **Codici di origine**: codici utilizzati per tenere traccia della risposta del cliente a una determinata posta del catalogo.
-   **Prodotti gratuiti**: prodotti inclusi nell'ordine di un cliente senza costi aggiuntivi. Questi prodotti vengono aggiunti automaticamente all'ordine quando il codice sorgente del catalogo viene immesso nell'ordine.
-   **Script**: testi letti da un lavoratore del servizio clienti a un cliente quando viene creato un ordine cliente. Gli script possono includere auguri o suggerimenti di acquisti.
-   **Upsell o articoli di vendita interaziendale**: articoli visualizzati come suggerimento quando un prodotto specifico viene aggiunto all'ordine.

Queste opzioni devono essere impostate prima che il catalogo venga approvato e pubblicato.

## <a name="prerequisites"></a>Prerequisiti
Completare le seguenti attività prima di iniziare:

-   Impostare i prodotti e gli assortimenti di prodotti.
-   Impostare i prodotti di vendita al dettaglio.
-   Impostare un assortimento.
-   Creare un servizio clienti.
-   Impostare un servizio clienti.
-   Aggiungere il servizio clienti a una gerarchia organizzativa.
-   Creare o modificare una gerarchia organizzativa.

## <a name="create-a-catalog"></a>Creazione di un catalogo
È necessario innanzitutto creare un catalogo, aggiungervi dei prodotti, quindi rivedere e aggiornare gli attributi dei prodotti.

## <a name="validate-the-catalog"></a>Convalida del catalogo
Dopo aver completato l'impostazione del catalogo, è necessario convalidarlo. Il processo di convalida verifica che i dati richiesti per gli attributi del canale e gli attributi del prodotto siano completi e validi e che il catalogo possa essere pubblicato.

## <a name="submit-the-catalog-for-review-and-approval"></a>Invio del catalogo per la revisione e l'approvazione
Dopo aver convalidato un catalogo, è possibile effettuarne l'invio per la revisione e l'approvazione. Un catalogo deve essere approvato prima di poter essere pubblicato. È possibile configurare un flusso di lavoro in modo che i cataloghi siano approvati automaticamente o richiedano l'approvazione manuale.

## <a name="optional-add-source-codes-free-products-and-scripts"></a>Facoltativo: aggiungere i codici sorgente, i prodotti gratuiti e gli script
È inoltre possibile aggiungere gli articoli riportati di seguito a un catalogo del servizio clienti. Questi articoli sono facoltativi.

-   I **codici di origine** possono essere utilizzati dalle società che forniscono i cataloghi stampati per tenere traccia della risposta del cliente a determinati cataloghi. I codici sorgente spesso vengono stampati sul retro di un catalogo e vengono immessi nell'ordine cliente quando un cliente effettua un acquisto. Per aggiungere un codice sorgente al catalogo, è innanzitutto necessario creare un mercato di destinazione. Il mercato di destinazione è in genere associato a una mailing list di proprietà o affittata.
-   **Prodotti gratuiti** sono gli articoli promozionali inclusi gratuitamente nell'ordine cliente quando viene fatto riferimento al catalogo.
-   Gli **script** possono essere utilizzati per facilitare le interazioni del lavoratore con i clienti nel contesto di un catalogo o di un prodotto all'interno di un catalogo.

## <a name="publish-the-catalog"></a>Pubblicazione del catalogo
Con la pubblicazione di un catalogo per un servizio clienti vengono finalizzate le informazioni sui prodotti nel catalogo. La pubblicazione indica inoltre che il catalogo è pronto per qualsiasi azione aggiuntiva che si desidera eseguire, ad esempio la creazione di un catalogo stampato. È possibile pubblicare i cataloghi manualmente oppure utilizzare un processo batch da pubblicare in base a una programmazione. Prima di poter pubblicare un catalogo, il catalogo deve essere convalidato e approvato. Per cambiare il catalogo dopo la sua pubblicazione, è possibile ritirare il catalogo e ripubblicarlo.





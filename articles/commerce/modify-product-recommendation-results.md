---
title: Regolare i risultati dei suggerimenti sul prodotto basati su AI-ML
description: In questo argomento viene descritto come gestire i risultati dei suggerimenti sul prodotto basati su AI-ML (intelligenza artificiale-machine learning) all'azienda.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: bc6a793061a3e644599f0882ff163f5f57b2162d
ms.sourcegitcommit: 8905d7a7a010e451c5435086480f66650ec54926
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "3664956"
---
# <a name="adjust-ai-ml-based-product-recommendation-results"></a>Regolare i risultati dei suggerimenti sul prodotto basati su AI-ML


[!include [banner](includes/banner.md)]

In questo argomento viene descritto come regolare i risultati dei suggerimenti sul prodotto basati su AI-ML (intelligenza artificiale-machine learning) all'azienda. 

Dopo l'abilitazione delle raccomandazioni sul prodotto, le impostazioni predefinite diventano effettive. Questi parametri possono rivelarsi utili per numerose esigenze. Si consiglia di spendere un po' di tempo per determinare se i risultati corrispondono all'andamento di vendita dei prodotti. Suggeriamo di valutare i risultati per alcuni giorni prima di modificare i parametri come necessario e di eseguire di nuovo dei test. 

## <a name="understanding-recommendation-list-parameters"></a>Informazioni sui parametri degli elenchi di suggerimenti

Prima di modificare i parametri, è necessario comprendere come questi influiscono sui risultati.

### <a name="trending-product-list"></a>Elenco di prodotti "Di tendenza"

L'elenco di prodotti "Di tendenza" include due parametri che possono essere modificati:

![Esempio di parametri predefiniti dell'elenco Di tendenza](./media/exampletrendingparameters.png)

1. **Includi nuovi prodotti degli ultimi X giorni** - I prodotti che sono stati aggiunti entro il numero di giorni specificato prima della data corrente possono essere utilizzati per selezionare candidati prodotto. Il valore predefinito nell'immagine suggerisce che i prodotti aggiunti fino a 180 giorni prima della data corrente possono essere utilizzati nell'elenco di prodotti Di tendenza.
1. **Includi vendite degli ultimi X giorni** - Le transazioni di vendita verificatesi entro il numero di giorni specificato prima della data corrente possono essere utilizzati per ordinare i prodotti. Il valore predefinito di cui sopra suggerisce che tutti gli acquisti di un prodotto effettuati negli ultimi 30 giorni sono utilizzati per determinare la posizione del prodotto nell'elenco di prodotti Di tendenza. 

### <a name="best-selling-product-list"></a>Elenco di prodotti "Più venduti"

A seconda dell'attività commerciale, l'elenco "Più venduti" può avere risultati differenti rispetto all'elenco Di tendenza, anche se entrambi utilizzano dati transazione per ordinare prodotti. Poiché l'elenco Più venduti non ha alcun limite basato sulla data di assortimento, questo elenco può ancora evidenziare prodotti più vecchi molto popolari che potrebbero essere stati rimossi dall'elenco Di tendenza. 

L'elenco di prodotti "Più venduti" include un parametro che può essere modificato:

![Esempio di parametro predefinito dell'elenco Più venduti](./media/examplebestsellingparameters.PNG)

1. **Includi vendite degli ultimi X giorni** - Le transazioni di vendita verificatesi entro il numero di giorni specificato prima della data corrente possono essere utilizzati per ordinare i prodotti. Il valore predefinito di cui sopra suggerisce che tutti gli acquisti di un prodotto effettuati negli ultimi 30 giorni sono utilizzati per determinare il posizionamento del prodotto nell'elenco di prodotti Più venduti. 

## <a name="manually-add-or-remove-products-from-recommendation-lists"></a>Aggiungere o rimuovere manualmente prodotti negli elenchi di suggerimenti

### <a name="for-new-trending-or-best-selling-lists"></a>Per gli elenchi "Novità", "Di tendenza" o "Più venduti"

1.  Andare a **Retail e Commerce** > **Suggerimenti sul prodotto** > **Parametri suggerimenti**.
1.  Nell'elenco dei parametri condivisi, selezionare **Elenchi suggerimenti**.
1.  Selezionare l'elenco per il quale si intende aggiungere o rimuovere prodotti.
1.  Per aggiungere prodotti alla tabella, selezionare **Aggiungi riga**. 
1.  Sotto la colonna Prodotto, cerca un prodotto per **Nome**o **Numero prodotto**.

    ![Esempio di ricerca di un prodotto nell'elenco Nuovo prodotto](./media/examplenewlistconfiguration1.png)

1.  Sotto la colonna Tipo di riga, selezionare una delle due seguenti opzioni:
    -   **Includi** - Aggiunge un prodotto all'elenco
    -   **Escludi** - Rimuove un prodotto dall'elenco
    
    ![Esempio di inclusione o esclusione di un prodotto dall'elenco Nuovo prodotto](./media/examplenewlistconfiguration2.png)

1.  La modifica di **Ordine di visualizzazione** cambierà l'ordine di visualizzazione dei prodotti contrassegnati con **includi** nell'elenco.
    - Se due prodotti hanno lo stesso valore di **ordine di visualizzazione**, l'ordine finale di quei due risultati può differire dal back office.
1.  Per rimuovere prodotti dalla tabella: selezionare la riga da rimuovere e selezionare **Rimuovi**.


### <a name="for-people-also-like-or-frequently-bought-together-lists"></a>Per gli elenchi "Alle persone piace anche" o "Spesso acquistati insieme"

Nel contesto degli elenchi "Alle persone piace anche" o "Spesso acquistati insieme", il machine learning è utilizzato per analizzare criteri di acquisto dei consumatori allo scopo di consigliare prodotti correlati acquistati spesso insieme a un prodotto iniziale univoco. 
 
Un *prodotto iniziale* è il prodotto per il quale si desidera generare i risultati. Nel contesto della modifica manuale degli elenchi di suggerimenti, si aggiungono o rimuovono risultati per questo prodotto. 

Seguire questi passaggi per aggiungere o rimuovere manualmente risultati per un prodotto iniziale:
1.  Selezionare il **Prodotto iniziale**. 
1.  Sotto la colonna **Prodotto**, cercare un prodotto per **Nome** o **Numero prodotto**
![Esempio di ricerca di un prodotto nell'elenco Spesso acquistati insieme](./media/exampleFBTlistconfiguration1.png)
1. Sotto la colonna **Tipo di riga**, selezionare una delle due seguenti opzioni:
    - **Includi** - Aggiunge un prodotto all'elenco
    - **Escludi** - Rimuove un prodotto dall'elenco     
![Esempio di inclusione o esclusione di un prodotto nell'elenco Spesso acquistati insieme](./media/exampleFBTlistconfiguration2.png)
1.  Per rimuovere prodotti dalla tabella: selezionare la riga da rimuovere e selezionare Rimuovi.


## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica suggerimenti sul prodotto](product-recommendations.md)

[Abilitare Azure Data Lake Storage in un ambiente Dynamics 365 Commerce](enable-adls-environment.md)

[Abilita suggerimenti sul prodotto](enable-product-recommendations.md)

[Abilitare i suggerimenti personalizzati](personalized-recommendations.md)

[Rifiuto esplicito dei suggerimenti personalizzati](personalization-gdpr.md)

[Abilitare gli elementi consigliati "acquista prodotti simili"](shop-similar-looks.md)

[Aggiungere suggerimenti sul prodotto nel POS](product.md)

[Aggiungere suggerimenti alla schermata della transazione](add-recommendations-control-pos-screen.md)

[Creare manualmente suggerimenti mirati](create-editorial-recommendation-lists.md)

[Crea suggerimenti con dati dimostrativi](product-recommendations-demo-data.md)

[Domande frequenti su suggerimenti prodotto](faq-recommendations.md)

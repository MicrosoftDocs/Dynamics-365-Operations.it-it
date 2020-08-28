---
title: Domande frequenti sui suggerimenti sul prodotto
description: In questo argomento vengono fornite informazioni sui processi e sugli strumenti che è possibile utilizzare per risolvere i problemi che riguardano i suggerimenti sul prodotto o i relativi risultati.
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
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, Core, Operations
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cf3df2267671b50c20b28dbdb1c6a21696bf2515
ms.sourcegitcommit: 8905d7a7a010e451c5435086480f66650ec54926
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "3664980"
---
# <a name="product-recommendations-faq"></a>Domande frequenti sui suggerimenti sul prodotto


[!include [banner](includes/banner.md)]

In questo argomento vengono fornite informazioni sui processi e sugli strumenti che è possibile utilizzare per risolvere i problemi che riguardano i [suggerimenti sul prodotto](product-recommendations.md) o i relativi risultati.

## <a name="best-practices"></a>Procedure consigliate
È molto importante utilizzare il concetto delle rappresentazioni generali prodotto e delle varianti. Il raggruppamento di varianti per una rappresentazione generale prodotto padre consente agli algoritmi degli elenchi e al servizio di creare modelli migliori. Inoltre, il servizio può servire una sola istanza di un prodotto anziché inserire tutte le varianti strettamente correlate in un elenco. Quando tutte le varianti strettamente correlate sono inserite in un elenco, è possibile avere risultati duplicati o errati.

## <a name="why-are-products-missing-from-my-recommendation-lists"></a>Perché i prodotti non sono presenti negli elenchi di suggerimenti?

In genere, se un articolo non è presente in un elenco di suggerimenti sul prodotto, è possibile che vi sia un problema di configurazione del prodotto. Ad esempio, è possibile che la data di inizio o di fine di un prodotto sia errata, che una dimensione non sia configurata correttamente, che il prodotto non si trovi nell'assortimento di canale appropriato e così via.

Se un articolo non è presente in un elenco di suggerimenti basato sull'intelligenza artificiale e sul machine learning, l'articolo potrebbe non soddisfare i criteri dell'elenco di suggerimenti o potrebbe non avere transazioni di acquisto sufficienti per essere visualizzato nell'elenco di suggerimenti.

È consigliabile verificare quanto segue:
1. **Verificare che i suggerimenti sul prodotto siano stati attivati in HQ.** Per ulteriori informazioni su come abilitare questo servizio, vedere [Abilitare suggerimenti sul prodotto](enable-product-recommendations.md).
1. **Verificare che le proprietà chiave del prodotto siano state impostate.** Ad esempio, gli assortimenti di prodotti devono essere impostati su **Includi**.
1. **Per i prodotti assortiti di recente, esiste la possibilità che il prodotto sia visualizzato nel nuovo elenco solo dopo 3 ore.**
1. **Se un prodotto non è ancora visualizzato in Di tendenza, Più venduti, Alle persone piace anche o Spesso acquistati insieme, è possibile che il prodotto non abbia transazioni sufficienti.** In questo caso, è possibile attendere che si verifichino altre transazioni, aggiornare i parametri degli elenchi di suggerimenti predefiniti o modificare manualmente i risultati degli elenchi di suggerimenti. Per ulteriori informazioni sui parametri relativi ai suggerimenti, vedere [Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML](modify-product-recommendation-results.md).
1. **Verificare che il prodotto soddisfi i criteri dei suggerimenti per l'elenco.** Per ulteriori informazioni sui parametri relativi ai suggerimenti sul prodotto, vedere [Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML](modify-product-recommendation-results.md).

## <a name="how-can-i-prevent-poor-recommendation-results-from-being-returned"></a>Come è possibile evitare di avere risultati dei suggerimenti insoddisfacenti?

Gli elenchi di suggerimenti richiedono un ampio volume di transazioni per generare risultati. Di conseguenza, è importante che gli utenti forniscano dati sulle transazioni completi.

Inoltre, i prodotti che non hanno transazioni o un numero elevato di transazioni generalmente non hanno risultati in **Alle persone piace anche** o **Spesso acquistati insieme** e non sono visualizzati negli elenchi di suggerimenti **Più venduti** o **Di tendenza**. Questa situazione può verificarsi spesso per prodotti nuovissimi o prodotti vecchi con un numero ridotto di acquisti. Per i nuovi articoli popolari, questo problema verrà risolto facilmente.

È consigliabile procedere come segue:
1. **Verificare che il prodotto soddisfi i criteri dei suggerimenti per quell'elenco.** Per ulteriori informazioni sui parametri relativi ai suggerimenti sul prodotto, vedere Modificare i risultati dei suggerimenti sul prodotto basati su AI-ML.
1. **Se il prodotto è nuovo, valutare l'opportunità di modificare un elenco di suggerimenti fino a che il prodotto ha più transazioni.** Per ulteriori informazioni su come modificare i risultati degli elenchi di suggerimenti, vedere [Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML](modify-product-recommendation-results.md).


- **Verificare che il prodotto soddisfi i criteri dei suggerimenti per quell'elenco.** Per ulteriori informazioni sui parametri relativi ai suggerimenti sul prodotto, vedere [Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML](modify-product-recommendation-results.md).
- **Se il prodotto è nuovo, valutare l'opportunità di modificare un elenco di suggerimenti fino a che il prodotto ha più transazioni.** Per ulteriori informazioni su come modificare i risultati degli elenchi di suggerimenti, vedere [Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML](modify-product-recommendation-results.md).

## <a name="can-i-remove-a-product-but-still-see-it-in-the-store"></a>È possibile continuare a visualizzare un prodotto nel punto vendita anche dopo averlo eliminato?

Se necessario, è possibile rettificare gli elenchi generati mediante algoritmi. Tuttavia, se un prodotto viene rimosso da un elenco di suggerimenti, il prodotto rimarrà individuabile nel punto vendita. Per ulteriori informazioni su come modificare i risultati dei suggerimenti sul prodotto, vedere [Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML](modify-product-recommendation-results.md).

Se un articolo non deve essere individuato nel punto vendita, è necessario impostare **Assortimenti articolo** su **Escludi**.

## <a name="how-do-i-add-a-list-to-an-e-commerce-page"></a>Come si aggiunge un elenco a una pagina di e-Commerce?

Per informazioni su come aggiungere le pagine di suggerimenti sul prodotto al sito Web di e-Commerce, vedere [Aggiungere elenchi di suggerimenti sul prodotto alle pagine](add-reco-list-to-page.md).

## <a name="how-do-i-enable-recommendations-on-pos"></a>Come si abilitano i suggerimenti nel POS?

Dopo avere abilitato i suggerimenti sul prodotto, sarà necessario aggiungere il pannello dei suggerimenti alla schermata POS di controllo. Per ulteriori informazioni, vedere [Aggiungere un controllo di suggerimenti alla schermata della transazione su dispositivi POS](add-recommendations-control-pos-screen.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica suggerimenti sul prodotto](product-recommendations.md)

[Abilitare Azure Data Lake Storage in un ambiente Dynamics 365 Commerce](enable-adls-environment.md)

[Abilita suggerimenti sul prodotto](enable-product-recommendations.md)

[Abilitare i suggerimenti personalizzati](personalized-recommendations.md)

[Rifiuto esplicito dei suggerimenti personalizzati](personalization-gdpr.md)

[Abilitare gli elementi consigliati "acquista prodotti simili"](shop-similar-looks.md)

[Aggiungere suggerimenti sul prodotto nel POS](product.md)

[Aggiungere suggerimenti alla schermata della transazione](add-recommendations-control-pos-screen.md)

[Regolare i risultati dei suggerimenti AI-ML](modify-product-recommendation-results.md)

[Creare manualmente suggerimenti mirati](create-editorial-recommendation-lists.md)

[Crea suggerimenti con dati dimostrativi](product-recommendations-demo-data.md)

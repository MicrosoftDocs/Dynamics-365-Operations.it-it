---
title: Creare manualmente suggerimenti mirati
description: In questo articolo viene illustrato come i merchandiser possono creare e gestire manualmente elenchi di prodotti per i clienti di Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e1a1b402165c5cb35696cf1cf6630770ad07508a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892680"
---
# <a name="manually-create-curated-recommendations"></a>Creare manualmente suggerimenti mirati

[!include [banner](includes/banner.md)]

In questo articolo viene illustrato come i merchandiser possono creare e gestire manualmente elenchi di suggerimenti sui prodotti per i clienti di Microsoft Dynamics 365 Commerce.

Gli elenchi curati sono raccolte di singoli contenuti creati e gestiti da persone.  

## <a name="create-a-new-list"></a>Crea un nuovo elenco

Per creare un elenco curato di suggerimenti sul prodotto, effettuare le operazioni seguenti.

1. Andare a **Retail e Commerce &gt; Suggerimenti sul prodotto &gt; Elenchi di suggerimenti**.
1. Selezionare **Nuovo**.
1. Nel campo **ID elenco** immettere un valore.
1. Nel campo **Nome elenco** immettere un valore.
    - Il campo **Nome elenco** indica il titolo dell'elenco che verrà visualizzato nella sezione degli elenchi curati del modulo **Raccolta prodotto**.
1. Per aggiungere prodotti all'elenco, selezionare **Aggiungi prodotti**.
1. Per modificare l'ordine dei prodotti nell'elenco, immettere un valore nella colonna **Ordine di visualizzazione**.
    - Se due prodotti hanno lo stesso valore di ordine di visualizzazione, l'ordine finale di quei due risultati può differire dal back office.
1. Selezionare **Salva** per salvare l'elenco.

## <a name="example-list"></a>Esempio di elenco

![Esempio di elenco curato nel back office.](./media/examplecuratedrecolist.png)

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

[Crea suggerimenti con dati dimostrativi](product-recommendations-demo-data.md)

[Domande frequenti su suggerimenti prodotto](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
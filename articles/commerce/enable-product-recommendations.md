---
title: Abilita suggerimenti sul prodotto
description: In questo articolo viene descritto come abilitare i suggerimenti sul prodotto basati su intelligenza artificiale-machine learning (AI-ML) disponibili per i clienti di Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 08/31/2021
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
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3dceec9e8e994a81b43cd5d1bd13970f2d246f40
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892073"
---
# <a name="enable-product-recommendations"></a>Abilita suggerimenti sul prodotto

[!include [banner](includes/banner.md)]

In questo articolo viene descritto come abilitare i suggerimenti sul prodotto basati su intelligenza artificiale-machine learning (AI-ML) disponibili per i clienti di Microsoft Dynamics 365 Commerce. Per ulteriori informazioni sugli elenchi di suggerimenti sul prodotto, vedere [Panoramica dei suggerimenti sul prodotto](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Verifica preliminare dei suggerimenti

1. Assicurarsi di avere una licenza per gli elementi consigliati di Dynamics 365 Commerce.
1. Assicurarsi che l'archivio entità sia connesso a un account Azure Data Lake Storage Gen2 di proprietà del cliente. Per ulteriori informazioni, vedere [Assicurarsi che Azure Data Lake Storage sia stato acquistato e verificato correttamente nell'ambiente](enable-ADLS-environment.md).
1. Verificare che la configurazione dell'identità di Azure AD contiene una voce per i Consigli. Ulteriori informazioni su come eseguire questa azione sono di seguito.
1. Assicurarsi che l'aggiornamento giornaliero dell'archivio entità ad Azure Data Lake Storage Gen2 sia stato programmato. Per ulteriori informazioni, vedere [Assicurarsi che l'aggiornamento dell'archivio entità sia stato automatizzato](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).
1. Abilitare le misure RetailSale per l'archivio entità. Per ulteriori informazioni sulla configurazione di questa procedura, vedere [Lavorare con le misure](/dynamics365/ai/customer-insights/pm-measures).

Dopo aver completato i passaggi precedenti, sarà possibile abilitare gli elementi consigliati.

## <a name="azure-ad-identity-configuration"></a>Configurazione dell'identità di Azure AD

Questo passaggio è necessario solo per i clienti che eseguono una configurazione di infrastruttura distribuita come servizio (IaaS). La configurazione dell'identità di Azure AD è automatica per i clienti in esecuzione su Azure Service Fabric, ma si consiglia di verificare che l'impostazione sia configurata come previsto.

### <a name="setup"></a>Attrezzaggio

1. In Commerce Headquarters, cercare la pagina **Applicazioni Azure Active Directory**.
1. Verificare che esista una voce per **RaccomandationSystemApplication-1**. Se una voce non esiste, crearne una utilizzando le seguenti informazioni:

    - **ID client**: d37b07e8-dd1c-4514-835d-8b918e6f9727
    - **Nome**: RecommendationSystemApplication-1
    - **ID utente**: RetailServiceAccount

1. Salvare e chiudere la pagina. 

## <a name="turn-on-recommendations"></a>Attivare i suggerimenti

Per attivare i suggerimenti sul prodotto, effettuare le seguenti operazioni.

1. In Commerce headquarters cercare **Gestione funzionalità**.
1. Selezionare **Tutto** per visualizzare un elenco delle funzionalità disponibili. 
1. Nella casella di ricerca, immettere **Elementi consigliati**.
1. Selezionare la funzionalità **Suggerimenti sul prodotto**.
1. Nel riquadro delle proprietà **Suggerimenti sul prodotto**, selezionare **Abilita ora**.

![Attivazione dei suggerimenti.](./media/FeatureManagement_Recommendations.PNG)

> [!NOTE]
> - La procedura indicata in precedenza avvia il processo di generazione di elenchi di elementi consigliati relativi al prodotto. Potrebbero essere necessarie diverse ore prima che gli elenchi siano disponibili e possano essere visualizzati nel punto vendita (POS) o in Dynamics 365 Commerce.
> - Questa configurazione non abilita tutte le funzionalità degli elementi consigliati. Le funzionalità avanzate quali elementi consigliati personalizzati, "acquista prodotti simili" e "acquista prodotti con descrizioni simili" sono controllate da voci di gestione delle funzionalità dedicate. Per informazioni sull'abilitazione di queste funzionalità in Commerce Headquarters, vedere [Abilitare gli elementi consigliati personalizzati](personalized-recommendations.md), [Abilitare gli elementi consigliati "acquista prodotti simili"](shop-similar-looks.md) e [Abilitare gli elementi consigliati "acquista prodotti con descrizioni simili"](shop-similar-description.md).

## <a name="configure-recommendation-list-parameters"></a>Configurare i parametri degli elenchi di suggerimenti

Per impostazione predefinita, l'elenco di suggerimenti sul prodotto basati su AI ML fornisce valori suggeriti. È possibile modificare i valori suggeriti predefiniti in base al flusso aziendale. Per ulteriori informazioni su come modificare i parametri predefiniti, accedere a [Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML](modify-product-recommendation-results.md).

## <a name="include-recommendations-in-e-commerce-experiences"></a>Includere elementi consigliati nelle esperienze e-commerce

Dopo aver abilitato gli elementi consigliati in Commerce Headquarters, i moduli Commerce utilizzati per visualizzare i risultati degli elementi consigliati per le esperienze e-commerce sono pronti per essere configurati. Per ulteriori informazioni, vedere [Moduli raccolta prodotti](product-collection-module-overview.md).

## <a name="show-recommendations-on-pos-devices"></a>Visualizzare suggerimenti sui dispositivi POS

Dopo avere abilitato gli elementi consigliati in Commerce Headquarters, è necessario aggiungere il pannello degli elementi consigliati alla schermata del POS di controllo mediante lo strumento di layout. Per ulteriori informazioni su questo processo, vedere [Aggiungere un controllo di suggerimenti alla schermata della transazione su dispositivi POS](add-recommendations-control-pos-screen.md). 

## <a name="enable-personalized-recommendations"></a>Abilitare i suggerimenti personalizzati

In Dynamics 365 Commerce, i rivenditori possono rendere disponibili suggerimenti personalizzati sui prodotti (noti anche come personalizzazione). In questo modo, i suggerimenti personalizzati possono essere incorporati nell'esperienza del cliente online e nel punto vendita. Quando la funzionalità di personalizzazione è attivata, il sistema può associare l'acquisto di un utente e le informazioni sul prodotto per generare suggerimenti personalizzati sul prodotto.

Per ulteriori informazioni su suggerimenti personalizzati, vedere [Abilitare suggerimenti personalizzati](personalized-recommendations.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica suggerimenti sul prodotto](product-recommendations.md)

[Abilitare Azure Data Lake Storage in un ambiente Dynamics 365 Commerce](enable-adls-environment.md)

[Abilitare i suggerimenti personalizzati](personalized-recommendations.md)

[Abilitare gli elementi consigliati "acquista prodotti simili"](shop-similar-looks.md)

[Rifiuto esplicito dei suggerimenti personalizzati](personalization-gdpr.md)

[Aggiungere suggerimenti sul prodotto su POS](product.md)

[Aggiungere suggerimenti alla schermata della transazione](add-recommendations-control-pos-screen.md)

[Regolare i risultati dei suggerimenti AI-ML](modify-product-recommendation-results.md)

[Creare manualmente suggerimenti mirati](create-editorial-recommendation-lists.md)

[Crea suggerimenti con dati dimostrativi](product-recommendations-demo-data.md)

[Domande frequenti su suggerimenti prodotto](faq-recommendations.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]

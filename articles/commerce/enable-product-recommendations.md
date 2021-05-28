---
title: Abilitare suggerimenti sul prodotto
description: In questo argomento viene descritto come abilitare i suggerimenti sul prodotto basati su intelligenza artificiale-machine learning (AI-ML) disponibili per i clienti di Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 08/18/2020
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
ms.openlocfilehash: 873266405638cd277eb748ad7e966ba8a4976b13
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019861"
---
# <a name="enable-product-recommendations"></a>Abilita suggerimenti sul prodotto

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come abilitare i suggerimenti sul prodotto basati su intelligenza artificiale-machine learning (AI-ML) disponibili per i clienti di Microsoft Dynamics 365 Commerce. Per ulteriori informazioni sugli elenchi di suggerimenti sul prodotto, vedere [Panoramica dei suggerimenti sul prodotto](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Verifica preliminare dei suggerimenti

Prima di abilitare, tenere presente che i consigli sui prodotti sono supportati solo per i clienti Commerce i quali hanno migrato il loro archivio utilizzando Azure Data Lake Storage. 

Le seguenti configurazioni devono essere abilitate nel back office prima di abilitare i consigli:

1. Assicurarsi che Azure Data Lake Storage sia stato acquistato e verificato correttamente nell'ambiente. Per ulteriori informazioni, vedere [Assicurarsi che Azure Data Lake Storage sia stato acquistato e verificato correttamente nell'ambiente](enable-ADLS-environment.md).
2. Assicurarsi che l'aggiornamento dell'archivio entità sia stato automatizzato. Per ulteriori informazioni, vedere [Assicurarsi che l'aggiornamento dell'archivio entità sia stato automatizzato](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).
3. Verificare che la configurazione dell'identità di Azure AD contiene una voce per i Consigli. Ulteriori informazioni su come eseguire questa azione sono di seguito.

Assicurarsi inoltre che le misurazioni RetailSale siano state abilitate. Per ulteriori informazioni su questa procedura di configurazione, vedere [Lavorare con le misure](/dynamics365/ai/customer-insights/pm-measures).

## <a name="azure-ad-identity-configuration"></a>Configurazione dell'identità di Azure AD

Questo passaggio è necessario per tutti i clienti che eseguono una configurazione di infrastruttura distribuita come servizio (IaaS). Per i clienti che eseguono Service Fabric (SF) questo passaggio dovrebbe essere automatico e consigliamo di verificare che l'impostazione sia configurata come previsto.

### <a name="setup"></a>Attrezzaggio

1. Dal back office, cercare la pagina **Applicazioni Azure Active Directory**.
2. Verificare se esiste una voce per "RaccomandationSystemApplication-1".

Se la voce non esiste, aggiungere una nuova voce con le seguenti informazioni:

- **ID client** - d37b07e8-dd1c-4514-835d-8b918e6f9727
- **Nome** - RecommendationSystemApplication-1
- **ID utente** - RetailServiceAccount

Salvare e chiudere la pagina. 

## <a name="turn-on-recommendations"></a>Attivare i suggerimenti

Per attivare i suggerimenti sul prodotto, effettuare le seguenti operazioni.

1. In Commerce headquarters cercare **Gestione funzionalità**.
1. Selezionare **Tutto** per visualizzare un elenco delle funzionalità disponibili. 
1. Nella casella di ricerca, immettere **Elementi consigliati**.
1. Selezionare la funzionalità **Suggerimenti sul prodotto**.
1. Nel riquadro delle proprietà **Suggerimenti sul prodotto**, selezionare **Abilita ora**.

![Attivazione dei suggerimenti](./media/FeatureManagement_Recommendations.PNG)

> [!NOTE]
> Questa procedura avvia il processo di generazione di elenchi di suggerimenti sul prodotto. Potrebbero essere necessarie diverse ore prima che gli elenchi siano disponibili e possano essere visualizzati nel punto vendita (POS) o in Dynamics 365 Commerce.

## <a name="configure-recommendation-list-parameters"></a>Configurare i parametri degli elenchi di suggerimenti

Per impostazione predefinita, l'elenco di suggerimenti sul prodotto basati su AI ML fornisce valori suggeriti. È possibile modificare i valori suggeriti predefiniti in base al flusso aziendale. Per ulteriori informazioni su come modificare i parametri predefiniti, accedere a [Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML](modify-product-recommendation-results.md).

## <a name="show-recommendations-on-pos-devices"></a>Visualizzare suggerimenti sui dispositivi POS

Dopo avere abilitato i suggerimenti nel back office di Commerce, è necessario aggiungere il pannello dei suggerimenti alla schermata del POS di controllo mediante lo strumento di layout. Per ulteriori informazioni su questo processo, vedere [Aggiungere un controllo di suggerimenti alla schermata della transazione su dispositivi POS](add-recommendations-control-pos-screen.md). 

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
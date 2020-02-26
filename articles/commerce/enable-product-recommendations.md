---
title: Abilitare suggerimenti sul prodotto
description: In questo argomento viene descritto come abilitare i suggerimenti sul prodotto basati su intelligenza artificiale-machine learning (AI-ML) disponibili per i clienti di Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 10/1/2019
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
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2d3f1bc2526eeacb4bd6338a0679eadd95a75989
ms.sourcegitcommit: b5ecde955a69f577de46e7db10e89caaedeb2b49
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024958"
---
# <a name="enable-product-recommendations"></a>Abilitare suggerimenti sul prodotto

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come abilitare i suggerimenti sul prodotto basati su intelligenza artificiale-machine learning (AI-ML) disponibili per i clienti di Microsoft Dynamics 365 Commerce. Per ulteriori informazioni sugli elenchi di suggerimenti sul prodotto, vedere [Panoramica dei suggerimenti sul prodotto](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Verifica preliminare dei suggerimenti

Prima di abilitare i suggerimenti sul prodotto, è necessario notare che questi sono supportati solo per i clienti Commerce che hanno eseguito la migrazione del proprio spazio di archiviazione utilizzando Azure Data Lake Storage (ADLS). 

Per i passaggi sull'abilitazione di ADLS, vedere [Come abilitare ADLS in un ambiente Dynamics 365](enable-ADLS-environment.md).

Assicurarsi inoltre che le misurazioni RetailSale siano state abilitate. Per ulteriori informazioni su questo processo di impostazione, vedere [qui.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)


## <a name="turn-on-recommendations"></a>Attivare i suggerimenti

Per attivare i suggerimenti sul prodotto, effettuare le seguenti operazioni.

1. Andare a **Retail e Commerce &gt; Suggerimenti sul prodotto &gt; Parametri suggerimenti**.
1. Nell'elenco dei parametri condivisi, selezionare **Elenchi suggerimenti**.
1. Impostare l'opzione **Abilita suggerimenti** su **Sì**.

![Abilitare i suggerimenti sul prodotto](./media/enableproductrecommendations.png)

> [!NOTE]
> Questa procedura avvia il processo di generazione di elenchi di suggerimenti sul prodotto. Questo processo può durare varie ore ed è visibile sul POS o in Dynamics 365 Commerce.

## <a name="configure-recommendation-list-parameters"></a>Configurare i parametri degli elenchi di suggerimenti

Per impostazione predefinita, l'elenco di suggerimenti sul prodotto basati su AI ML fornisce valori suggeriti. È possibile modificare i valori suggeriti predefiniti in base al flusso aziendale. Per ulteriori informazioni su come modificare i parametri predefiniti, accedere a [Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML](modify-product-recommendation-results.md).

## <a name="show-recommendations-on-pos-devices"></a>Visualizzare suggerimenti sui dispositivi POS

Dopo avere abilitato i suggerimenti nel back office di Commerce, è necessario aggiungere il pannello dei suggerimenti alla schermata del POS di controllo mediante lo strumento di layout. Per ulteriori informazioni su questo processo, vedere [Aggiungere un controllo di suggerimenti alla schermata della transazione su dispositivi POS](add-recommendations-control-pos-screen.md). 

## <a name="enable-personalized-recommendations"></a>Abilitare suggerimenti personalizzati

Per ulteriori informazioni su come ricevere suggerimenti personalizzati, vedere [Abilitare suggerimenti personalizzati](personalized-recommendations.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica suggerimenti sul prodotto](product-recommendations.md)

[Abilitare suggerimenti personalizzati](personalized-recommendations.md)

[Aggiungere elenchi di suggerimenti sul prodotto alle pagine](add-reco-list-to-page.md)

[Aggiungere il pannello dei suggerimenti a dispositivi POS](add-recommendations-control-pos-screen.md)

[Panoramica del modulo di raccolta prodotti](product-collection-module-overview.md)

[Abilitare ADLS nell'ambiente Dynamics 365](enable-ADLS-environment.md)


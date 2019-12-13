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
ms.openlocfilehash: ecda571a356c6968196d09cc19923105cf4544ab
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770141"
---
# <a name="enable-product-recommendations"></a>Abilitare suggerimenti sul prodotto

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento viene descritto come abilitare i suggerimenti sul prodotto basati su intelligenza artificiale-machine learning (AI-ML) disponibili per i clienti di Microsoft Dynamics 365 Commerce. Per ulteriori informazioni sugli elenchi di suggerimenti sul prodotto, vedere [Panoramica dei suggerimenti sul prodotto](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Verifica preliminare dei suggerimenti
Prima di abilitare i suggerimenti sul prodotto, è necessario notare che questi sono supportati solo per i clienti F&O che supportano la build 10.0.6 e che hanno eseguito la migrazione del proprio spazio di archiviazione utilizzando BDL. 

Assicurarsi inoltre che le misurazioni RetailSale siano state abilitate. Per ulteriori informazioni su questo processo di impostazione, vedere [qui.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)


## <a name="turn-on-recommendations"></a>Attivare i suggerimenti

Per attivare i suggerimenti sul prodotto, effettuare le seguenti operazioni.

1. Andare a **Vendita al dettaglio** &gt; **Suggerimenti sul prodotto** &gt; **Parametri suggerimenti**.
1. Nell'elenco dei parametri di vendita al dettaglio condivisi, selezionare **Elenchi suggerimenti**.
1. Impostare l'opzione **Abilita suggerimenti** su **Sì**.

![Abilitare i suggerimenti sul prodotto](./media/enableproductrecommendations.png)

> [!NOTE]
> Questa procedura avvia il processo di generazione di elenchi di suggerimenti sul prodotto. Questo processo può durare varie ore ed è visibile sul POS o in Dynamics 365 for Commerce.

## <a name="configure-recommendation-list-parameters"></a>Configurare i parametri degli elenchi di suggerimenti
Per impostazione predefinita, l'elenco di suggerimenti sul prodotto basati su AI ML fornisce valori suggeriti. È possibile modificare i valori suggeriti predefiniti in base al flusso aziendale. Per ulteriori informazioni su come modificare i parametri predefiniti, accedere a [Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML](modify-product-recommendation-results.md).

## <a name="show-recommendations-on-pos-devices"></a>Visualizzare suggerimenti sui dispositivi POS
Dopo avere abilitato i suggerimenti nel back office, è necessario aggiungere il pannello dei suggerimenti alla schermata del POS di controllo mediante lo strumento di layout. Per ulteriori informazioni su questo processo, vedere [qui.](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)


## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica suggerimenti sul prodotto](product-recommendations.md)

[Aggiungere elenchi di suggerimenti sul prodotto alle pagine](add-reco-list-to-page.md)

[Aggiungere il pannello dei suggerimenti a dispositivi POS](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)



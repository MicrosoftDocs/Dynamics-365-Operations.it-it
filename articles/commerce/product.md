---
title: Aggiungere suggerimenti sul prodotto su POS
description: In questo argomento viene descritto l'utilizzo dei suggerimenti sul prodotto in un dispositivo POS .
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 08784385dd1fead13f538b4e856b4bac6651a560
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969928"
---
# <a name="add-product-recommendations-on-pos"></a>Aggiungere suggerimenti sul prodotto su POS

[!include [banner](includes/banner.md)]

Fondamentalmente, i suggerimenti sul prodotto sono un'applicazione aziendale trasformativa che si estende su tutte le aree commerciali per creare esperienze di scoperta di prodotti ricchi, coinvolgenti e personalizzati. Per implementare questa funzionalità sul POS, seguire i passaggi in [come aggiungere i suggerimenti si dispositivi POS.](add-recommendations-control-pos-screen.md) 

Per ulteriori informazioni sulle funzionalità di suggerimenti sul prodotto, vedere [Panoramica dei suggerimenti sul prodotto.](../commerce/product-recommendations.md) 

## <a name="scenarios"></a>Scenari

I suggerimenti sul prodotto sono abilitati per i seguenti scenari di POS. Sono disponibili in Cloud POS o Modern POS (MPOS).

1. Nella pagina **Dettagli prodotto**:

    - Se un associato del punto vendita visita una pagina **Dettagli prodotto** quando visualizza le transazioni precedenti su più canali diversi, il servizio dei suggerimenti suggerisce articoli aggiuntivi che è probabile vengano acquistati insieme.

    [![Suggerimenti sulla pagina Dettagli prodotto](./media/proddetails.png)](./media/proddetails.png)

2. Nella pagina **Transazione**:

    - Il motore dei suggerimenti suggerisce gli articoli in base all'intero elenco di articoli nel carrello che vengono acquistati insieme di frequente.

    > [!NOTE]
    > Per visualizzare i suggerimenti nella pagina **Transazione**, il rivenditore deve aggiornare il layout dello schermo in Dynamics 365 Commerce. Il controllo **Suggerimenti** deve essere rilasciato nella pagina **Transazione**.

    [![Suggerimenti nella pagina Transazione](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

## <a name="configure-commerce-to-enable-pos-recommendations"></a>Configurare Commerce per abilitare i suggerimenti POS

Per impostare i suggerimenti sul prodotto, effettuare le seguenti operazioni:

1. Verificare che il servizio sia stato aggiornato alla **build 10.0.6.**
2. Seguire le istruzioni su come [abilitare i suggerimenti sul prodotto](../commerce/enable-product-recommendations.md) per l'azienda.
3. Facoltativo: per visualizzare i suggerimenti sulla schermata della transazione, passare a **Layout schermo**, scegliere il layout dello schermo, avviare **Progettazione layout schermo**, quindi rilasciare il controllo **suggerimenti** dove necessario.
4. Passare a **Parametri di commercio**, selezionare **Machine learning**, quindi scegliere **Sì** in **Abilita suggerimenti POS**.
5. Per visualizzare i suggerimenti sul POS, eseguire il processo di configurazione globale **1110**. Per riflettere le modifiche apportate a Progettazione layout schermo POS, eseguire il processo di configurazione dei canali **1070**.

## <a name="troubleshoot-issues-where-you-have-product-recommendations-already-enabled"></a>Risolvere i problemi in caso di suggerimenti sul prodotto già abilitati

- Passare a **Parametri di commercio** \> **Elenchi di suggerimenti** \> **Disabilita suggerimenti sul prodotto** ed eseguire il **Processo di configurazione globale \[9999\]**. 
- Se si è aggiunto il **Controllo per suggerimenti** alla schermata di transazione mediante la **Progettazione layout schermo**, rimuovere anche tale elemento.
- Per eventuali domande aggiuntive, leggere le [domande frequenti su suggerimenti prodotto](../commerce/faq-recommendations.md) per ulteriori informazioni.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica suggerimenti sul prodotto](product-recommendations.md)

[Abilitare Azure Data Lake Storage in un ambiente Dynamics 365 Commerce](enable-adls-environment.md)

[Abilita suggerimenti sul prodotto](enable-product-recommendations.md)

[Abilitare i suggerimenti personalizzati](personalized-recommendations.md)

[Rifiuto esplicito dei suggerimenti personalizzati](personalization-gdpr.md)

[Abilitare gli elementi consigliati "acquista prodotti simili"](shop-similar-looks.md)

[Aggiungere suggerimenti alla schermata della transazione](add-recommendations-control-pos-screen.md)

[Regolare i risultati dei suggerimenti AI-ML](modify-product-recommendation-results.md)

[Creare manualmente suggerimenti mirati](create-editorial-recommendation-lists.md)

[Crea suggerimenti con dati dimostrativi](product-recommendations-demo-data.md)

[Domande frequenti su suggerimenti prodotto](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
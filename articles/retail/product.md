---
title: Suggerimenti sul prodotto nel dispositivo POS
description: In questo argomento viene descritto l'utilizzo dei suggerimenti sul prodotto in un dispositivo POS .
author: bebeale
manager: AnnBe
ms.date: 10/01/19
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 98c84e987c40adf136d0240117f7b0f119bf2f59
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811119"
---
# <a name="product-recommendations-on-pos"></a>Suggerimenti sul prodotto nel dispositivo POS

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
    > Per visualizzare i suggerimenti nella pagina **Transazione**, il rivenditore deve aggiornare il layout dello schermo in Dynamics 365 for Retail. Il controllo **Suggerimenti** deve essere rilasciato nella pagina **Transazione**.

    [![Suggerimenti nella pagina Transazione](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

## <a name="configure-dynamics-365-retail-to-enable-pos-recommendations"></a>Configurare Dynamics 365 Retail per abilitare i suggerimenti POS

Per impostare i suggerimenti sul prodotto, effettuare le seguenti operazioni:

1. Verificare che il servizio sia stato aggiornato alla **build 10.0.6.**
2. Seguire le istruzioni su come [abilitare i suggerimenti sul prodotto](../commerce/enable-product-recommendations.md) per l'azienda.
3. Facoltativo: per visualizzare i suggerimenti sulla schermata della transazione, passare a **Layout schermo**, scegliere il layout dello schermo, avviare **Progettazione layout schermo**, quindi rilasciare il controllo **suggerimenti** dove necessario.
4. Passare a **Parametri di vendita al dettaglio**, selezionare **Machine learning**, quindi scegliere **Sì** in **Abilita suggerimenti POS**.
5. Per visualizzare i suggerimenti sul POS, eseguire il processo di configurazione globale **1110**. Per riflettere le modifiche apportate a Progettazione layout schermo POS, eseguire il processo di configurazione dei canali **1070**.



## <a name="troubleshoot-issues-where-you-have-product-recommendations-already-enabled"></a>Risolvere i problemi in caso di suggerimenti sul prodotto già abilitati

- Passare a **Parametri di vendita al dettaglio** \> **Elenchi di suggerimenti** \> **Disabilita suggerimenti sul prodotto** ed eseguire il **Processo di configurazione globale \[9999\]**. 
- Se si è aggiunto il **Controllo per suggerimenti** alla schermata di transazione mediante la **Progettazione layout schermo**, rimuovere anche tale elemento.
- Per eventuali domande aggiuntive, leggere le [domande frequenti su suggerimenti prodotto](../commerce/faq-recommendations.md) per ulteriori informazioni.

## <a name="additional-resources"></a>Risorse aggiuntive

[Aggiungere un controllo di suggerimenti alla schermata della transazione su dispositivi POS](add-recommendations-control-pos-screen.md)

[Panoramica suggerimenti sul prodotto](../commerce/product-recommendations.md)

[Abilitare suggerimenti sul prodotto](../commerce/enable-product-recommendations.md) 

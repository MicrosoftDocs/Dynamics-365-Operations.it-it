---
title: Abilitare gli elementi consigliati "acquista prodotti simili"
description: Questo argomento descrive come abilitare i consigli sui prodotti "acquista prodotti simili" in Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: e70365be8484d71ef9e0e9823b0a4406b0fd2761439780cafc30e1284bda1f20
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722002"
---
# <a name="enable-shop-similar-looks-recommendations"></a>Abilitare gli elementi consigliati "acquista prodotti simili"

[!include [banner](includes/banner.md)]

Questo argomento descrive come abilitare i consigli sui prodotti "acquista prodotti simili" in Microsoft Dynamics 365 Commerce.

La funzionalità relativa ai consigli "acquista prodotti simili" in Dynamics 365 Commerce utilizza la potenza dell'intelligenza artificiale e dell'apprendimento automatico (IA-ML) per fornire ai clienti consigli per prodotti visivamente simili. Rendendo disponibili i consigli "acquista prodotti simili" per tutti i canali di vendita al dettaglio in Commerce, i rivenditori possono aumentare la soddisfazione dei clienti aiutandoli a trovare facilmente ciò che desiderano.

La funzionalità per i consigli "acquista prodotti simili" utilizza immagini di prodotti di varianti del prodotto iniziale per trovare e consigliare prodotti visivamente simili nel catalogo prodotti di un rivenditore. 

I consigli "acquista prodotti simili" sono disponibili sia nelle esperienze POS che e-commerce.

### <a name="example-scenarios"></a>Scenari di esempio

- Un cliente visualizza un maglione a righe nere e riceve un consiglio per un maglione rosso simile. Il cliente seleziona il prodotto consigliato invece del prodotto visualizzato originariamente e quindi riceve consigli per prodotti simili in rosso. 
- Un cliente utilizza i consigli "acquista prodotti simili" per scoprire orecchini corrispondenti a un anello che il cliente è interessato ad acquistare.

## <a name="enable-shop-similar-looks-recommendations-in-commerce-headquarters"></a>Abilitare i consigli "acquista look simili" in Commerce headquarters

I consigli relativi ai prodotti sono supportati solo per gli utenti Commerce che hanno eseguito la migrazione del loro archivio ad Azure Data Lake Gen2.

### <a name="prerequisites"></a>Prerequisiti

Prima che i rivenditori possano iniziare a mostrare ai clienti consigli di "acquista prodotti simili", esistono due passaggi prerequisiti:

- [Abilitare suggerimenti sul prodotto](enable-product-recommendations.md) in Commerce headquarters.
- Verificare che il server multimediale supporti le chiamate HTTPS.

Affinché il motore dei consigli possa accedere alle immagini dei prodotti, i rivenditori devono generare gli URL dei prodotti. Per generare gli URL dei prodotti in Commerce Headquarters, attenersi alla seguente procedura.

1. Andare a **Immagini del prodotto**.
1. Nel riquadro azioni selezionare **Definisci modello media**.
1. Nel riquadro delle proprietà **Definisci modello media**, in **URL multimediali**, selezionare **Genera URL**.

> [!NOTE]
> Quando si abilita la funzionalità di consiglio "acquista prodotti simili", inizia il processo di generazione degli elenchi di consigli sui prodotti. Potrebbe essere necessario fino a un giorno prima che questi elenchi siano disponibili e visibili online e nei terminali POS.

Per abilitare la funzione di consigli "acquista prodotti simili" in Commerce headquarters, seguire questi passaggi.

1. Andare a **Gestione funzionalità**.
1. Nell'elenco delle funzioni disponibili, cercare e selezionare **Acquista prodotti simili**.
1. Nel riquadro di destra, selezionare **Abilita** per attivare il servizio.

La figura seguente mostra la funzione **Acquista prodotti simili** nella pagina **Gestione funzionalità** in Commerce headquarters.

![La funzione Acquista prodotti simili nella pagina Gestione funzionalità in Commerce headquarters.](./media/enableshopsimilarlooks.png)

Dopo che le attività precedenti sono state completate, i terminali POS vengono automaticamente migliorati con un pannello **Acquista prodotti simili** contestuale. Selezionando **Ulteriori informazioni**, gli utenti dei terminali POS possono essere indirizzati a una pagina dedicata "acquista prodotti simili" che può essere filtrata ulteriormente.

> [!NOTE]
> Se si disabilita la funzione "acquista prodotti simili", nessun altro tipo di consiglio sui prodotti sarà interessato. Per ulteriori informazioni relative ai suggerimenti sui prodotti, vedere [Panoramica suggerimenti sul prodotto](product-recommendations.md).

## <a name="add-a-shop-similar-looks-button-to-product-details-pages-by-using-commerce-site-builder"></a>Aggiungi un pulsante Acquista prodotti simili alle pagine dei dettagli dei prodotti utilizzando la creazione di siti Commerce

Dopo aver abilitato la funzione di consigli "acquista prodotti simili" in Commerce headquarters, un'opzione nel generatore di siti Commerce consente ai rivenditori di aggiungere un pulsante **Acquista prodotti simili** alla casella di acquisto in qualsiasi pagina dei dettagli del prodotto (PDP). Un cliente che seleziona questo pulsante viene indirizzato a una pagina dedicata "acquista prodotti simili" che restituisce prodotti visivamente simili. Lì, il cliente può utilizzare i selettori per filtrare ulteriormente i prodotti.

Per aggiungere un pulsante **Acquista prodotti simili** alle pagine dei dettagli dei prodotti utilizzando la creazione di siti Commerce, seguire questi passaggi.

1. Aprire una pagina di creazione di siti Web che contiene un modulo Casella acquisti.
1. Selezionare il modulo Casella acquisti nel pannello di navigazione a sinistra.
1. Nel riquadro di navigazione a destra, selezionare la casella di controllo **Abilita collegamento acquista prodotti simili**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla. Dopo la pubblicazione della pagina, la pagina dei dettagli del prodotto includerà un pulsante **Acquista prodotti simili**.

La figura seguente mostra la casella di controllo **Abilita collegamento acquista prodotti simili** e **Acquista prodotti simili** in una pagina dei dettagli del prodotto di esempio in Creazione di siti.

![Casella di controllo Abilita collegamento acquista prodotti simili e Acquista prodotti simili in una pagina dei dettagli del prodotto in Creazione di siti.](./media/SSLecomtooling.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica suggerimenti sul prodotto](product-recommendations.md)

[Abilitare Azure Data Lake Storage in un ambiente Dynamics 365 Commerce](enable-adls-environment.md)

[Abilita suggerimenti sul prodotto](enable-product-recommendations.md)

[Rifiuto esplicito dei suggerimenti personalizzati](personalization-gdpr.md)

[Aggiungere suggerimenti sul prodotto su POS](product.md)

[Aggiungere suggerimenti alla schermata della transazione](add-recommendations-control-pos-screen.md)

[Regolare i risultati dei suggerimenti AI-ML](modify-product-recommendation-results.md)

[Creare manualmente suggerimenti mirati](create-editorial-recommendation-lists.md)

[Crea suggerimenti con dati dimostrativi](product-recommendations-demo-data.md)

[Domande frequenti su suggerimenti prodotto](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

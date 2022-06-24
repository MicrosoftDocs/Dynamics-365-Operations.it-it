---
title: Abilitare gli elementi consigliati "acquista prodotti simili"
description: Questo articolo descrive come abilitare i consigli sui prodotti "acquista descrizioni simili" in Microsoft Dynamics 365 Commerce.
author: bsokolov
ms.date: 01/13/2021
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
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: b935731b24f96753c814e3b496ffeeb7a92d9cc1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852010"
---
# <a name="enable-shop-similar-description-recommendations"></a>Abilitare gli elementi consigliati "acquista prodotti simili"

[!include [banner](includes/banner.md)]

Questo articolo descrive come abilitare i consigli sui prodotti "acquista descrizioni simili" in Microsoft Dynamics 365 Commerce.

La funzionalità relativa ai consigli "acquista descrizioni simili" in Dynamics 365 Commerce utilizza l'intelligenza artificiale e l'apprendimento automatico (IA-ML) per fornire ai clienti consigli per prodotti le cui descrizioni sono simili a ciò che ha cercato il cliente. Rendendo disponibili i consigli "acquista descrizioni simili" per tutti i canali di vendita al dettaglio in Commerce, i rivenditori possono aiutare i clienti a trovare facilmente ciò che desiderano.

La funzionalità per i consigli "acquista descrizioni simili" utilizza il nome e la descrizione del prodotto di prodotti iniziali per trovare prodotti simili consigliati in un catalogo di prodotti di un rivenditore.

I consigli "acquista descrizioni simili" sono disponibili sia nelle esperienze POS che e-commerce.

## <a name="example-scenarios"></a>Scenari di esempio

I seguenti scenari di esempio mostrano i tipi di consigli che la funzionalità "Descrizione negozio simile" può fornire:

- Un cliente visualizza un paio di occhiali cerchiati di corno in stile retrò e riceve una serie di consigli per altri occhiali con un design simile, nel contesto del settore del rivenditore.
- Un cliente utilizza i consigli "Descrizione negozio simile" per scoprire gusti di caffè simili a un gusto che ha acquistato in precedenza dal rivenditore.

## <a name="set-up-shop-similar-description-recommendations"></a>Configura consigli "acquista descrizioni simili"

I consigli relativi ai prodotti sono supportati solo per gli utenti Commerce che hanno eseguito la migrazione del loro archivio ad Azure Data Lake Storage Gen2.

### <a name="prerequisites"></a>Prerequisiti

Prima di mostrare ai clienti i consigli "acquista descrizioni simili", è necessario completare i seguenti prerequisiti:

- [Abilitare suggerimenti sul prodotto](enable-product-recommendations.md) in Commerce headquarters.
- Verificare che il server multimediale supporti le chiamate HTTPS.

### <a name="turn-on-the-shop-similar-description-recommendations-feature"></a>Abilita la funzionalità dei consigli "acquista descrizioni simili"

Per abilitare la funzione dei consigli "acquista descrizioni simili" in Commerce Headquarters, segui questi passaggi.

1. Nell'area di lavoro **Gestione funzionalità**, nell'elenco delle funzionalità disponibili, cercare e selezionare **Acquista descrizioni simili**.
1. Nel riquadro di destra, seleziona **Abilita**.

> [!NOTE]
> Quando si attiva la funzionalità, il sistema inizia a generare elenchi di suggerimenti sui prodotti. Potrebbe essere necessario fino a un giorno affinché questi elenchi siano disponibili e visibili online e nei terminali POS.
>
> Se disattivi la funzione, altri tipi di consigli sui prodotti non sono interessati. Per ulteriori informazioni relative ai suggerimenti sui prodotti, vedere [Panoramica suggerimenti sul prodotto](product-recommendations.md).

## <a name="add-a-shop-similar-description-button-to-product-details-pages"></a>Aggiungi un pulsante Acquista descrizioni simili alle pagine dei dettagli del prodotto

Dopo aver abilitato la funzione di consigli "acquista descrizioni simili" in Commerce Headquarters, puoi aggiungere un pulsante **Acquista descrizioni simili** per la casella di acquisto nella pagina dei dettagli del prodotto (PDP). Un cliente che seleziona questo pulsante viene indirizzato a una pagina dedicata **Acquista descrizioni simili** che restituisce prodotti visivamente simili. Il cliente può quindi utilizzare i selettori per filtrare ulteriormente i prodotti.

Per aggiungere un pulsante **Descrizione prodotti simili** alle pagine dei dettagli dei prodotti utilizzando la creazione di siti Commerce, segui questi passaggi.

1. Aprire una pagina di creazione di siti Web che contiene un modulo Casella acquisti.
1. Selezionare il modulo Casella acquisti nel pannello di navigazione a sinistra.
1. Nel riquadro di navigazione a destra, seleziona la casella di controllo **Abilita collegamento acquista descrizione simili**.
1. Selezionare **Salva**.
1. Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla. Dopo la pubblicazione della pagina, la pagina dei dettagli del prodotto includerà un pulsante **Acquista descrizione simili**.

La figura seguente mostra la casella di controllo **Abilita collegamento acquista descrizione simili** e il pulsante **Acquista descrizioni simili** in una pagina dei dettagli del prodotto di esempio in Creazione di siti.

![Casella di controllo Abilita collegamento acquista descrizione simili e il pulsante Acquista descrizioni simili in una pagina dei dettagli del prodotto in Creazione di siti.](./media/ter_site_builder_buybox_button.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica suggerimenti sul prodotto](product-recommendations.md)

[Abilitare Azure Data Lake Storage in un ambiente Dynamics 365 Commerce](enable-adls-environment.md)

[Abilita suggerimenti sul prodotto](enable-product-recommendations.md)

[Abilitare gli elementi consigliati "acquista prodotti simili"](shop-similar-looks.md)

[Regolare i risultati dei suggerimenti AI-ML](modify-product-recommendation-results.md)

[Creare manualmente suggerimenti mirati](create-editorial-recommendation-lists.md)

[Domande frequenti su suggerimenti prodotto](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
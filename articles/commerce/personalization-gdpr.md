---
title: Rifiuto esplicito dei suggerimenti personalizzati
description: Questo argomento descrive come è possibile consentire ai clienti di rifiutare esplicitamente i suggerimenti personalizzati in Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e65fc54f87664caec95b2bc2c579d0820ae08c0f
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477686"
---
# <a name="opt-out-of-personalized-recommendations"></a>Rifiuto esplicito dei suggerimenti personalizzati

[!include [banner](includes/banner.md)]

Questo argomento descrive come è possibile consentire ai clienti di rifiutare esplicitamente i suggerimenti personalizzati in Microsoft Dynamics 365 Commerce.

Durante la creazione dell'account, la ricezione di suggerimenti personalizzati è impostata automaticamente per i nuovi clienti. Tuttavia, Dynamics 365 Commerce offre vari modi ai rivenditori per consentire agli utenti di rifiutare questi suggerimenti e limitare il trattamento dei loro dati personali. Per gli utenti autenticati che rinunciano a ricevere suggerimenti personalizzati, la visualizzazione degli elenchi personalizzati viene sospesa immediatamente. Inoltre, tutti i dati personali raccolti per la personalizzazione verranno rimossi dai modelli di suggerimenti personalizzati.

Per ulteriori informazioni sui suggerimenti personalizzati relativi ai prodotti, vedere [Abilitare i suggerimenti personalizzati](personalized-recommendations.md).

## <a name="ways-for-retailers-to-implement-an-opt-out-experience"></a>Metodi di implementazione di un'esperienza di rifiuto esplicito

I rivenditori hanno a disposizione 3 metodi di implementazione di un'esperienza di rifiuto esplicito.

### <a name="opting-out-on-behalf-of-users"></a>Rifiuto per conto degli utenti

Nella gestione degli account nel back office di Commerce, i rivenditori possono attivare il rifiuto per conto degli utenti.

1. Dalla home page del back office, cercare **Tutti i clienti**.
1. Cercare e seleziona un cliente, quindi selezionare la scheda dettaglio **Vendita al dettaglio**.

    ![Scheda dettaglio Vendita al dettaglio](./media/Disablepersonalizationpart1.png)

1. Sotto **Privacy**, impostare l'opzione **Disabilita personalizzazione** su **Sì**.

    ![Impostazioni di privacy](./media/Disablepersonalizationpart2.png)

1. Selezionare **Salva**, quindi chiudere la pagina.

### <a name="module-based-opt-out-experience"></a>Esperienza di rifiuto basata su moduli

I rivenditori possono consentire agli utenti autenticati di rifiutare personalmente i suggerimenti personalizzati. Per fornire questa esperienza di rifiuto, aggiungere il modulo di rifiuto esplicito dell'utente alle pagine del profilo dell'account cliente.

### <a name="custom-extensions"></a>Estensioni personalizzate

I rivenditori possono creare estensioni personalizzate per gestire l'esperienza di rifiuto per gli utenti. Per ulteriori informazioni, vedere [Chiamare API Retail Server](e-commerce-extensibility/call-retail-server-apis.md)e [Estendibilità del canale online](e-commerce-extensibility/overview.md).

## <a name="obtain-a-digital-copy-of-personalized-recommendations-data-on-behalf-of-an-authenticated-user"></a>Ottenere una copia digitale dei dati dei suggerimenti personalizzati per conto di un utente autenticato

È possibile che i clienti vogliano ottenere una copia digitale dei propri dati personali e una vista esportata dei risultati dei loro suggerimenti. Se un cliente richiede queste informazioni, il rivenditore deve creare un'estensione personalizzata che chiama l'API Retail Server e che esegue una query per i risultati completi dall'elenco **Selezioni personalizzate** in base all'ID del cliente. I risultati possono quindi essere esportati in formato CSV e condivisi con il cliente.

L'esempio seguente mostra come un rivenditore può eseguire questa attività.

1. Il rivenditore crea un'estensione personalizzata per estrarre i dati dei suggerimenti personali per conto dell'utente. Per informazioni su come creare moduli, clonare moduli esistenti, chiamare le API Retail Server e chiamare azioni sui dati, vedere [Estendibilità del canale online](e-commerce-extensibility/overview.md).
2. L'estensione personalizzata chiama l'azione **get-recommendations** sui dati core e passa le informazioni richieste alla stessa, in base ai requisiti dell'elenco. Nel caso dell'elenco **Selezioni personalizzate**, l'estensione deve passare il nome di elenco e l'ID cliente corretti all'azione dati.

    Un modo per creare l'estensione personalizzata è clonare il modulo di raccolta prodotti esistente utilizzato per restituire i risultati dei suggerimenti. Clonando questo modulo esistente, un rivenditore può modificare il codice esistente e aggiungere un nuovo pulsante che esporta i risultati dei suggerimenti in un file CSV. Per ulteriori informazioni, vedere [Clonare un modulo libreria di moduli](e-commerce-extensibility/clone-starter-module.md)e [Moduli Raccolta prodotti](product-collection-module-overview.md).

    Per una visualizzazione completa della libreria API Retail Server, vedere [API utente e clienti Retail Server](dev-itpro/retail-server-customer-consumer-api.md).

3. Dopo aver creato l'estensione personalizzata, il rivenditore può esportare un file CSV di tutti i risultati dei suggerimenti, in base all'ID cliente univoco dell'utente autenticato.
4. Il rivenditore può condividere il file CSV esportato che contiene l'elenco personalizzato completo dei prodotti consigliati con l'utente autenticato.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica suggerimenti sul prodotto](product-recommendations.md)

[Abilitare Azure Data Lake Storage in un ambiente Dynamics 365 Commerce](enable-adls-environment.md)

[Abilita suggerimenti sul prodotto](enable-product-recommendations.md)

[Abilitare i suggerimenti personalizzati](personalized-recommendations.md)

[Abilitare gli elementi consigliati "acquista prodotti simili"](shop-similar-looks.md)

[Aggiungere suggerimenti sul prodotto nel POS](product.md)

[Aggiungere suggerimenti alla schermata della transazione](add-recommendations-control-pos-screen.md)

[Regolare i risultati dei suggerimenti AI-ML](modify-product-recommendation-results.md)

[Creare manualmente suggerimenti mirati](create-editorial-recommendation-lists.md)

[Crea suggerimenti con dati dimostrativi](product-recommendations-demo-data.md)

[Domande frequenti su suggerimenti prodotto](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

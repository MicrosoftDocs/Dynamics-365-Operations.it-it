---
title: Abilitare Azure Data Lake Storage in un ambiente Dynamics 365 Commerce
description: Questo argomento fornisce istruzioni su come collegare una soluzione Azure Data Lake Storage Gen 2 a un archivio di entità dell'ambiente Dynamics 365 Commerce. Questo è un passaggio obbligatorio prima di abilitare gli elementi consigliati sui prodotti.
author: bebeale
ms.date: 08/31/2020
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
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c96c29a4d9639b02e6a60ad938b7e06f7d500c68
ms.sourcegitcommit: 98061a5d096ff4b9078d1849e2ce6dd7116408d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466294"
---
# <a name="enable-azure-data-lake-storage-in-a-dynamics-365-commerce-environment"></a>Abilitare Azure Data Lake Storage in un ambiente Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Questo argomento fornisce istruzioni su come collegare una soluzione Azure Data Lake Storage Gen2 a un archivio di entità dell'ambiente Dynamics 365 Commerce. Questo è un passaggio obbligatorio prima di abilitare gli elementi consigliati sui prodotti.

Nella soluzione Dynamics 365 Commerce, i dati necessari per calcolare elementi consigliati, prodotti e transazioni vengono aggregati nell'archivio di entità dell'ambiente. Per rendere questi dati accessibili ad altri servizi di Dynamics 365, come analisi dei dati, business intelligence e suggerimenti personalizzati, è necessario connettere l'ambiente a una soluzione Azure Data Lake Storage Gen2 di proprietà del cliente.

Dopo che i passaggi precedenti sono stati completati, tutti i dati del cliente nell'archivio di entità dell'ambiente vengono rispecchiati automaticamente nella soluzione Azure Data Lake Storage Gen 2 del cliente. Quando le funzionalità degli elementi consigliati sono abilitate tramite l'area di lavoro Gestione funzionalità in Commerce Headquarters, allo stack degli elementi consigliati verrà concesso l'accesso alla stessa soluzione Azure Data Lake Storage Gen2.

Durante l'intero processo i dati dei clienti rimangono protetti e sotto il loro controllo.

## <a name="prerequisites"></a>Prerequisiti

Un archivio di entità dell'ambiente Dynamics 365 Commerce deve essere connesso a un account Azure Data Lake Gen Storage Gen2 e ai servizi associati.

Per ulteriori informazioni su Azure Data Lake Storage Gen 2 e sulla relativa configurazione, vedere la [documentazione ufficiale di Azure Data Lake Storage Gen2](https://azure.microsoft.com/pricing/details/storage/data-lake).
  
## <a name="configuration-steps"></a>Passaggi di configurazione

Questa sezione illustra le fasi di configurazione necessarie per abilitare Azure Data Lake Storage Gen2 in un ambiente in relazione agli elementi consigliati sul prodotto.
Per una panoramica più approfondita dei passaggi necessari per abilitare Azure Data Lake Storage Gen2, vedere [Rendere disponibile l'archivio entità come Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).

### <a name="enable-azure-data-lake-storage-in-the-environment"></a>Abilitare Azure Data Lake Storage nell'ambiente

1. Accedere al portale di back office dell'ambiente.
1. Cercare **Parametri di sistema** e selezionare la scheda **Connessioni dati**. 
1. Impostare **Abilita l'integrazione di Data Lake** su **Sì**.
1. Successivamente, immettere le informazioni necessarie seguenti:
    1. **ID applicazione** // **Segreto applicazione** // **Nome DNS** - Necessario per connettersi a KeyVault in cui è archiviato il segreto Azure Data Lake Storage.
    1. **Nome segreto** - Il nome segreto memorizzato in KeyVault e utilizzato per l'autenticazione con Azure Data Lake Storage.
1. Salvare le modifiche nell'angolo in alto a sinistra della pagina.

L'immagine seguente mostra un esempio di configurazione Azure Data Lake Storage.

![Esempio dI configurazione Azure Data Lake Storage.](./media/exampleADLSConfig1.png)

### <a name="test-the-azure-data-lake-storage-connection"></a>Testare la connessione Azure Data Lake Storage

1. Testare la connessione a KeyVault usando il collegamento **Testa Azure Key Vault**.
1. Testare la connessione a Azure Data Lake Storage usando il collegamento **Testa Archiviazione di Azure**.

> [!NOTE]
> Se entrambi i test precedenti falliscono, ricontrollare che tutte le informazioni KeyVault aggiunte sopra siano corrette, quindi riprovare.

Una volta che i test di connessione hanno esito positivo, è necessario abilitare l'aggiornamento automatico per l'archivio entità.

Per abilitare l'aggiornamento automatico per l'archivio entità, attenersi alla seguente procedura.

1. Cercare **Archivio entità**.
1. Nell'elenco a sinistra, selezionare la voce **RetailSales** e selezionare **Modifica**.
1. Assicurarsi che **Aggiornamento automatico attivato** sia impostato su **Sì**, selezionare **Aggiorna**, quindi selezionare **Salva**.

L'immagine seguente mostra un esempio di archivio entità con aggiornamento automatico abilitato.

![Esempio di archivio entità con aggiornamento automatico abilitato.](./media/exampleADLSConfig2.png)

Azure Data Lake Storage è ora configurato per l'ambiente. 

Se non è già stato fatto, seguire la procedura per [abilitare la personalizzazione e i suggerimenti sui prodotti](enable-product-recommendations.md) per l'ambiente.

## <a name="additional-resources"></a>Risorse aggiuntive

[Rendere disponibile l'archivio entità come Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md)

[Panoramica suggerimenti sul prodotto](product-recommendations.md)

[Abilita suggerimenti sul prodotto](enable-product-recommendations.md)

[Abilitare i suggerimenti personalizzati](personalized-recommendations.md)

[Rifiuto esplicito dei suggerimenti personalizzati](personalization-gdpr.md)

[Abilitare gli elementi consigliati "acquista prodotti simili"](shop-similar-looks.md)

[Aggiungere suggerimenti sul prodotto nel POS](product.md)

[Aggiungere suggerimenti alla schermata della transazione](add-recommendations-control-pos-screen.md)

[Regolare i risultati dei suggerimenti AI-ML](modify-product-recommendation-results.md)

[Creare manualmente suggerimenti mirati](create-editorial-recommendation-lists.md)

[Crea suggerimenti con dati dimostrativi](product-recommendations-demo-data.md)

[Domande frequenti su suggerimenti prodotto](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

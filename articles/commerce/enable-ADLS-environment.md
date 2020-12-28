---
title: Abilitare Azure Data Lake Storage in un ambiente di Dynamics 365 Commerce
description: Questo argomento spiega come abilitare e testare Azure Data Lake Storage per un ambiente di Dynamics 365 Commerce, che è un prerequisito per abilitare i suggerimenti sui prodotti.
author: bebeale
manager: AnnBe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 27e4f1c751ee865b0df536f3c1912cb1d8946032
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413367"
---
# <a name="enable-azure-data-lake-storage-in-a-dynamics-365-commerce-environment"></a>Abilitare Azure Data Lake Storage in un ambiente di Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Questo argomento spiega come abilitare e testare Azure Data Lake Storage per un ambiente di Dynamics 365 Commerce, che è un prerequisito per abilitare i suggerimenti sui prodotti.

## <a name="overview"></a>Panoramica

Nella soluzione Dynamics 365 Commerce, tutte le informazioni su prodotti e transazioni vengono tracciate nell'archivio entità dell'ambiente. Per rendere questi dati accessibili ad altri servizi di Dynamics 365, come analisi dei dati, business intelligence e suggerimenti personalizzati, è necessario connettere l'ambiente a una soluzione Azure Data Lake Storage Gen 2 di proprietà del cliente.

Poiché Azure Data Lake Storage è configurato in un ambiente, tutti i dati necessari vengono sottoposti a mirroring dall'archivio entità pur essendo protetti e sotto il controllo del cliente.

Se nell'ambiente sono abilitati anche suggerimenti sui prodotti o personalizzati, allo stack dei suggerimenti sui prodotti verrà concesso l'accesso alla cartella dedicata in Azure Data Lake Storage per recuperare i dati del cliente e calcolare i suggerimenti basati sugli stessi.

## <a name="prerequisites"></a>Prerequisiti

I clienti devono avere Azure Data Lake Storage configurato in una sottoscrizione di Azure di loro proprietà. Questo argomento non copre l'acquisto di una sottoscrizione di Azure o la configurazione di un account di archiviazione abilitato per Azure Data Lake Storage.

Per ulteriori informazioni su Azure Data Lake Storage, vedere la [documentazione ufficiale di Azure Data Lake Storage Gen2](https://azure.microsoft.com/pricing/details/storage/data-lake).
  
## <a name="configuration-steps"></a>Passaggi di configurazione

Questa sezione illustra le fasi di configurazione necessarie per abilitare Azure Data Lake Storage in un ambiente in relazione ai consigli sul prodotto.
Per una panoramica più approfondita dei passaggi necessari per abilitare Azure Data Lake Storage, vedere [Rendere disponibile l'archivio entità come Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).

### <a name="enable-azure-data-lake-storage-in-the-environment"></a>Abilitare Azure Data Lake Storage nell'ambiente

1. Accedere al portale di back office dell'ambiente.
1. Cercare **Parametri di sistema** e selezionare la scheda **Connessioni dati**. 
1. Impostare **Abilita l'integrazione di Data Lake** su **Sì**.
1. Impostare **Aggiornamento afflusso Data Lake** su **Sì**.
1. Successivamente, immettere le informazioni necessarie seguenti:
    1. **ID applicazione** // **Segreto applicazione** // **Nome DNS** - Necessario per connettersi a KeyVault in cui è archiviato il segreto Azure Data Lake Storage.
    1. **Nome segreto** - Il nome segreto memorizzato in KeyVault e utilizzato per l'autenticazione con Azure Data Lake Storage.
1. Salvare le modifiche nell'angolo in alto a sinistra della pagina.

L'immagine seguente mostra un esempio di configurazione Azure Data Lake Storage.

![Esempio dI configurazione Azure Data Lake Storage](./media/exampleADLSConfig1.png)

### <a name="test-the-azure-data-lake-storage-connection"></a>Testare la connessione Azure Data Lake Storage

1. Testare la connessione a KeyVault usando il collegamento **Testa Azure Key Vault**.
1. Testare la connessione a Azure Data Lake Storage usando il collegamento **Testa Archiviazione di Azure**.

> [!NOTE]
> Se i test falliscono, ricontrollare che tutte le informazioni KeyVault aggiunte sopra siano corrette, quindi riprovare.

Una volta che i test di connessione hanno esito positivo, è necessario abilitare l'aggiornamento automatico per l'archivio entità.

Per abilitare l'aggiornamento automatico per l'archivio entità, attenersi alla seguente procedura.

1. Cercare **Archivio entità**.
1. Nell'elenco a sinistra, selezionare la voce **RetailSales** e selezionare **Modifica**.
1. Assicurarsi che **Aggiornamento automatico attivato** sia impostato su **Sì**, selezionare **Aggiorna**, quindi selezionare **Salva**.

L'immagine seguente mostra un esempio di archivio entità con aggiornamento automatico abilitato.

![Esempio di archivio entità con aggiornamento automatico abilitato](./media/exampleADLSConfig2.png)

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
